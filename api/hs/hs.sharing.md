# [docs](index.md) » hs.sharing
---

Share items with the macOS Sharing Services under the control of Hammerspoon.

This module will allow you to share Hammerspoon items with registered Sharing Services.  Some of the built-in sharing services include sharing through mail, Facebook, AirDrop, etc.  Other applications can add additional services as well.

For most sharing services (this has not been tested with all), the user will be prompted with the standard sharing dialog showing what is to be shared and offered a chance to submit or cancel.

This example prepares an email with a screenshot:
~~~lua
mailer = hs.sharing.newShare("com.apple.share.Mail.compose")
mailer:subject("Screenshot generated at " .. os.date()):recipients({ "user@address.com" })
mailer:shareItems({ [[
    Add any notes that you wish to add describing the screenshot here and click the Send icon when you are ready to send this

]], hs.screen.mainScreen():snapshot() })
~~~

Common item data types that can be shared with Sharing Services include (but are not necessarily limited to):
 * basic data types like strings and numbers
 * hs.image objects
 * hs.styledtext objects
 * web sites and other URLs through the use of the [hs.sharing.URL](#URL) function
 * local files through the use of file URLs created with the [hs.sharing.fileURL](#fileURL) function

## API Overview
* Constants - Useful values which cannot be changed
 * [builtinSharingServices](#builtinsharingservices)
* Functions - API calls offered directly by the extension
 * [fileURL](#fileurl)
 * [shareTypesFor](#sharetypesfor)
 * [URL](#url)
* Constructors - API calls which return an object, typically one that offers API methods
 * [newShare](#newshare)
* Methods - API calls which can only be made on an object returned by a constructor
 * [accountName](#accountname)
 * [alternateImage](#alternateimage)
 * [attachments](#attachments)
 * [callback](#callback)
 * [canShareItems](#canshareitems)
 * [image](#image)
 * [messageBody](#messagebody)
 * [permanentLink](#permanentlink)
 * [recipients](#recipients)
 * [serviceName](#servicename)
 * [shareItems](#shareitems)
 * [subject](#subject)
 * [title](#title)

## API Documentation

### Constants

#### [builtinSharingServices](#builtinsharingservices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.sharing.builtinSharingServices[]` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | A table containing the predefined sharing service labels defined by Apple. |

### Functions

#### [fileURL](#fileurl)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.sharing.fileURL(path) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a table representing a file URL for the path specified. |
| **Parameters**                                       | <ul><li>path - a string specifying a path to represent as a file URL.</li></ul> |
| **Returns**                                          | <ul><li>a table containing the necessary labels for converting the specified path into a URL as required by the macOS APIs.</li></ul> |
| **Notes**                                            | <ul><li>this function is a wrapper to <a href="#URL">hs.sharing.URL</a> which sets the second argument to <code>true</code> for you.</li><li>see <a href="#URL">hs.sharing.URL</a> for more information about the table format returned by this function.</li></ul> |

#### [shareTypesFor](#sharetypesfor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.sharing.shareTypesFor(items) -> identifiersTable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a table containing the sharing service identifiers which can share the items specified. |
| **Parameters**                                       | <ul><li>items - an array (table) or list of items separated by commas which you wish to share with this module.</li></ul> |
| **Returns**                                          | <ul><li>an array (table) containing strings which identify sharing service identifiers which may be used by the <a href="#newShare">hs.sharing.newShare</a> constructor to share the specified data.</li></ul> |
| **Notes**                                            | <ul><li>this function is intended to be used to determine the identifiers for sharing services available on your computer and that may not be included in the <a href="#builtinSharingServices">hs.sharing.builtinSharingServices</a> table.</li></ul> |

#### [URL](#url)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.sharing.URL(URL, [fileURL]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a table representing the URL specified. |
| **Parameters**                                       | <ul><li>URL     - a string or table specifying the URL.</li><li>fileURL - an optional boolean, default <code>false</code>, specifying whether or not the URL is supposed to represent a file on the local computer.</li></ul> |
| **Returns**                                          | <ul><li>a table containing the necessary labels for representing the specified URL as required by the macOS APIs.</li></ul> |
| **Notes**                                            | <ul><li>If the URL is specified as a table, it is expected to contain a <code>url</code> key with a string value specifying a proper schema and resource locator.</li></ul> |

### Constructors

#### [newShare](#newshare)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.sharing.newShare(type) -> sharingObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new sharing object of the type specified by the identifier provided. |
| **Parameters**                                       | <ul><li>type - a string specifying a sharing type identifier as listed in the <a href="#builtinSharingServices">hs.sharing.builtinSharingServices</a> table or returned by the <a href="#shareTypesFor">hs.sharing.shareTypesFor</a>.</li></ul> |
| **Returns**                                          | <ul><li>a sharingObject or nil if the type identifier cannot be created on this system</li></ul> |

### Methods

#### [accountName](#accountname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.sharing:accountName() -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The account name used by the sharing service when posting on Twitter or Sina Weibo. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a string containing the account name used by the sharing service, or nil if the sharing service does not provide this.</li></ul> |
| **Notes**                                            | <ul><li>According to the Apple API documentation, only the Twitter and Sina Weibo sharing services will set this property, but this has not been fully tested.</li></ul> |

#### [alternateImage](#alternateimage)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.sharing:alternateImage() -> hs.image object | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns an alternate image, if one exists, representing the sharing service provided by this sharing object. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>an hs.image object or nil, if no alternate image representation for the sharing service is defined.</li></ul> |

#### [attachments](#attachments)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.sharing:attachments() -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | If the sharing service provides an array of the attachments included when the data was posted, this method will return an array of file URL tables of the attachments. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>an array (table) containing the attachment file URLs, or nil if the sharing service selected does not provide this.</li></ul> |
| **Notes**                                            | <ul><li>not all sharing services will set a value for this property.</li></ul> |

#### [callback](#callback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.sharing:callback(fn) -> sharingObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Set or clear the callback for the sharingObject. |
| **Parameters**                                       | <ul><li>fn - A function, or nil, to set or remove the callback for the sharingObject</li></ul> |
| **Returns**                                          | <ul><li>the sharingObject</li></ul> |
| **Notes**                                            | <ul><li>the callback should expect 3 or 4 arguments and return no results.  The arguments will be as follows:</li><li>the sharingObject itself</li><li>the callback message, which will be a string equal to one of the following:<ul><li>"didFail"   - an error occurred while attempting to share the items</li><li>"didShare"  - the sharing service has finished sharing the items</li><li>"willShare" - the sharing service is about to start sharing the items; occurs before sharing actually begins</li></ul></li><li>an array (table) containing the items being shared; if the message is "didFail" or "didShare", the items may be in a different order or converted to a different internal type to facilitate sharing.</li><li>if the message is "didFail", the fourth argument will be a localized description of the error that occurred.</li></ul> |

#### [canShareItems](#canshareitems)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.sharing:canShareItems(items) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a boolean specifying whether or not all of the items specified can be shared with the sharing service represented by the sharingObject. |
| **Parameters**                                       | <ul><li>items - an array (table) or list of items separated by commas which are to be shared by the sharing service</li></ul> |
| **Returns**                                          | <ul><li>a boolean value indicating whether or not all of the specified items can be shared with the sharing service represented by the sharingObject.</li></ul> |

#### [image](#image)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.sharing:image() -> hs.image object | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns an image, if one exists, representing the sharing service provided by this sharing object. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>an hs.image object or nil, if no image representation for the sharing service is defined.</li></ul> |

#### [messageBody](#messagebody)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.sharing:messageBody() -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | If the sharing service provides the message body that was posted when sharing has completed, this method will return the message body as a string. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a string containing the message body, or nil if the sharing service selected does not provide this.</li></ul> |
| **Notes**                                            | <ul><li>not all sharing services will set a value for this property.</li></ul> |

#### [permanentLink](#permanentlink)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.sharing:permanentLink() -> URL table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | If the sharing service provides a permanent link to the post when sharing has completed, this method will return the corresponding URL. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the URL for the permanent link, or nil if the sharing service selected does not provide this.</li></ul> |
| **Notes**                                            | <ul><li>not all sharing services will set a value for this property.</li></ul> |

#### [recipients](#recipients)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.sharing:recipients([recipients]) -> current value | sharingObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Get or set the subject to be used when the sharing service performs its sharing method. |
| **Parameters**                                       | <ul><li>recipients - an optional array (table) or list of recipient strings separated by commas which specify the recipients of the shared items.</li></ul> |
| **Returns**                                          | <ul><li>if an argument is provided, returns the sharingObject; otherwise returns the current value.</li></ul> |
| **Notes**                                            | <ul><li>not all sharing services will make use of the value set by this method.</li><li>the individual recipients should be specified as strings in the format expected by the sharing service; e.g. for items being shared in an email, the recipients should be email address, etc.</li></ul> |

#### [serviceName](#servicename)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.sharing:serviceName() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The service identifier for the sharing service represented by the sharingObject. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a string containing the identifier for the sharing service.</li></ul> |
| **Notes**                                            | <ul><li>this string will match the identifier used to create the sharing service object with <a href="#newShare">hs.sharing.newShare</a></li></ul> |

#### [shareItems](#shareitems)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.sharing:shareItems(items) -> sharingObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Shares the items specified with the sharing service represented by the sharingObject. |
| **Parameters**                                       | <ul><li>items - an array (table) or list of items separated by commas which are to be shared by the sharing service</li></ul> |
| **Returns**                                          | <ul><li>the sharingObject, or nil if one or more of the items cannot be shared with the sharing service represented by the sharingObject.</li></ul> |
| **Notes**                                            | <ul><li>You can check to see if all of your items can be shared with the <a href="#canShareItems">hs.sharing:canShareItems</a> method.</li></ul> |

#### [subject](#subject)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.sharing:subject([subject]) -> current value | sharingObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Get or set the subject to be used when the sharing service performs its sharing method. |
| **Parameters**                                       | <ul><li>subject - an optional string specifying the subject for the posting of the shared content</li></ul> |
| **Returns**                                          | <ul><li>if an argument is provided, returns the sharingObject; otherwise returns the current value.</li></ul> |
| **Notes**                                            | <ul><li>not all sharing services will make use of the value set by this method.</li></ul> |

#### [title](#title)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.sharing:title() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The title for the sharing service represented by the sharingObject. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a string containing the title of the sharing service.</li></ul> |
| **Notes**                                            | <ul><li>this string differs from the identifier used to create the sharing service object with <a href="#newShare">hs.sharing.newShare</a> and is intended to provide a more friendly label for the service if you need to list or refer to it elsewhere.</li></ul> |

