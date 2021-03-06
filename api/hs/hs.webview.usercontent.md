# [docs](index.md) » hs.webview.usercontent
---

This module provides support for injecting custom JavaScript user content into your webviews and for JavaScript to post messages back to Hammerspoon.

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [injectScript](#injectscript)
 * [removeAllScripts](#removeallscripts)
 * [setCallback](#setcallback)
 * [userScripts](#userscripts)

## API Documentation

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.usercontent.new(name) -> usercontentControllerObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Create a new user content controller for a webview and create the message port with the specified name for JavaScript message support. |
| **Parameters**                                       | <ul><li>name - the name of the message port which JavaScript in the webview can use to post messages to Hammerspoon.</li></ul> |
| **Returns**                                          | <ul><li>the usercontentControllerObject</li></ul> |
| **Notes**                                            | <ul><li>This object should be provided as the final argument to the <code>hs.webview.new</code> constructor in order to tie the webview to this content controller.  All new windows which are created from this parent webview will also use this controller.</li><li>See <code>hs.webview.usercontent:setCallback</code> for more information about the message port.</li></ul> |

### Methods

#### [injectScript](#injectscript)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.usercontent:injectScript(scriptTable) -> usercontentControllerObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Add a script to be injected into webviews which use this user content controller. |
| **Parameters**                                       | <ul><li>scriptTable - a table containing the following keys which define the script and how it is to be injected:</li><li>source        - the javascript which is injected (required)</li><li>mainFrame     - a boolean value which indicates whether this script is only injected for the main webview frame (true) or for all frames within the webview (false).  Defaults to true.</li><li>injectionTime - a string which indicates whether the script is injected at "documentStart" or "documentEnd". Defaults to "documentStart".</li></ul> |
| **Returns**                                          | <ul><li>the usercontentControllerObject or nil if the script table was malformed in some way.</li></ul> |

#### [removeAllScripts](#removeallscripts)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.usercontent:removeAllScripts() -> usercontentControllerObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Removes all user scripts currently defined for this user content controller. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the usercontentControllerObjectNotes:</li><li>The WKUserContentController class only allows for removing all scripts.  If you need finer control, make a copy of the current scripts with <code>hs.webview.usercontent.userScripts()</code> first so you can recreate the scripts you want to keep.</li></ul> |
| **Notes**                                            | <ul><li>The WKUserContentController class only allows for removing all scripts.  If you need finer control, make a copy of the current scripts with <code>hs.webview.usercontent.userScripts()</code> first so you can recreate the scripts you want to keep.</li></ul> |

#### [setCallback](#setcallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.usercontent:setCallback(fn) -> usercontentControllerObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Set or remove the callback function to handle message posted to this user content's message port. |
| **Parameters**                                       | <ul><li>fn - The function which should receive messages posted to this user content's message port.  Specify an explicit nil to disable the callback.  The function should take one argument which will be the message posted and any returned value will be ignored.</li></ul> |
| **Returns**                                          | <ul><li>the usercontentControllerObject</li></ul> |
| **Notes**                                            | <ul><li>Within your (injected or served) JavaScript, you can post messages via the message port created with the constructor like this:</li></ul> |

#### [userScripts](#userscripts)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.usercontent:userScripts() -> array` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Get a table containing all of the currently defined injection scripts for this user content controller |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>An array of injected user scripts.  Each entry in the array will be a table containing the following keys:</li><li>source        - the javascript which is injected</li><li>mainFrame     - a boolean value which indicates whether this script is only injected for the main webview frame (true) or for all frames within the webview (false)</li><li>injectionTime - a string which indicates whether the script is injected at "documentStart" or "documentEnd".</li></ul> |
| **Notes**                                            | <ul><li>Because the WKUserContentController class only allows for removing all scripts, you can use this method to generate a list of all scripts, modify it, and then use it in a loop to reapply the scripts if you need to remove just a few scripts.</li></ul> |

