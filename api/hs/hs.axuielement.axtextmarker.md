# [docs](index.md) » hs.axuielement.axtextmarker
---

This submodule allows hs.axuielement to support using AXTextMarker and AXTextMarkerRange objects as parameters for parameterized Accessibility attributes with applications that support them.

Most Accessibility object values correspond to the common data types found in most programming languages -- strings, numbers, tables (arrays and dictionaries), etc. AXTextMarker and AXTextMarkerRange types are application specific and do not have a direct mapping to a simple data type. The description I've found most apt comes from comments within the Chromium source for the Mac version of their browser:

> // A serialization of a position as POD. Not for sharing on disk or sharing
> // across thread or process boundaries, just for passing a position to an
> // API that works with positions as opaque objects.

This submodule allows Lua to represent these as userdata which can be passed in to parameterized attributes for the appliction from which they were retrieved. Examples are expected to be added to the Hammerspoon wiki soon.

As this submodule utilizes private and undocumented functions in the HIServices framework, if you receive an error using any of these functions or methods indicating an undefined CF function (the function or method will return nil and a string of the format "CF function AX... undefined"), please make sure to include the output of the following in any issue you submit to the Hammerspoon github page (enter these into the Hammerspoon console):

    hs.inspect(hs.axuielement.axtextmarker._functionCheck())
    hs.inspect(hs.processInfo)
    hs.host.operatingSystemVersionString()

## API Overview
* Functions - API calls offered directly by the extension
 * [_functionCheck](#_functioncheck)
 * [bytes](#bytes)
 * [endMarker](#endmarker)
 * [length](#length)
 * [startMarker](#startmarker)
* Constructors - API calls which return an object, typically one that offers API methods
 * [newMarker](#newmarker)
 * [newRange](#newrange)

## API Documentation

### Functions

#### [_functionCheck](#_functioncheck)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement.axtextmarker._functionCheck() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a table of the AXTextMarker and AXTextMarkerRange functions that have been discovered and are used within this module. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a table with key-value pairs where the keys correspond to the undocumented Core Foundation functions required by this module to support AXTextMarker and AXTextMarkerRange and the value will be a boolean indicating whether the function exists in the currently loaded frameworks.</li></ul> |
| **Notes**                                            | <ul><li>the functions are defined within the HIServices framework which is part of the ApplicationServices framework, so it is expected that the necessary functions will always be available; however, if you ever receive an error message from a function or method within this submodule of the form "CF function AX... undefined", please see the submodule heading documentation for a description of the information, including that which this function provides, that should be included in any error report you submit.</li></ul> |

#### [bytes](#bytes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement.axtextmarker:bytes() -> string | nil, errorString` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a string containing the opaque binary data contained within the axTextMarkerObject |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a string containing the opaque binary data contained within the axTextMarkerObject</li></ul> |
| **Notes**                                            | <ul><li>the string will likely contain invalid UTF8 code sequences or unprintable ascii values; to see the data in decimal or hexidecimal form you can use:</li></ul> |

#### [endMarker](#endmarker)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement.axtextmarker:endMarker() -> axTextMarkerObject | nil, errorString` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the ending marker for an axTextMarkerRangeObject |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the ending marker for an axTextMarkerRangeObject</li></ul> |

#### [length](#length)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement.axtextmarker:length() -> integer | nil, errorString` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns an integer specifying the number of bytes in the data portion of the axTextMarkerObject. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>an integer specifying the number of bytes in the data portion of the axTextMarkerObject</li></ul> |
| **Notes**                                            | <ul><li>As the data is application specific, it is unlikely that you will use this method often; it is included primarily for testing and debugging purposes.</li></ul> |

#### [startMarker](#startmarker)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement.axtextmarker:startMarker() -> axTextMarkerObject | nil, errorString` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the starting marker for an axTextMarkerRangeObject |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the starting marker for an axTextMarkerRangeObject</li></ul> |

### Constructors

#### [newMarker](#newmarker)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement.axtextmarker.newMarker(string) -> axTextMarkerObject | nil, errorString` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new AXTextMarker object from the string of binary data provided |
| **Parameters**                                       | <ul><li><code>string</code> - a string containing 1 or more bytes of data for the AXTextMarker object</li></ul> |
| **Returns**                                          | <ul><li>a new axTextMarkerObject or nil and a string description if there was an error</li></ul> |
| **Notes**                                            | <ul><li>This function is included primarily for testing and debugging purposes -- in general you will probably never use this constructor; AXTextMarker objects appear to be mostly application dependant and have no meaning external to the application from which it was created.</li></ul> |

#### [newRange](#newrange)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement.axtextmarker.newRange(startMarker, endMarker) -> axTextMarkerRangeObject | nil, errorString` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new AXTextMarkerRange object from the start and end markers provided |
| **Parameters**                                       | <ul><li><code>startMarker</code> - an axTextMarkerObject representing the start of the range to be created</li><li><code>endMarker</code>   - an axTextMarkerObject representing the end of the range to be created</li></ul> |
| **Returns**                                          | <ul><li>a new axTextMarkerRangeObject or nil and a string description if there was an error</li></ul> |
| **Notes**                                            | <ul><li>this constructor can be used to create a range from axTextMarkerObjects obtained from an application to specify a new range for a paramterized attribute. As a simple example (it is hoped that more will be added to the Hammerspoon wiki shortly):</li></ul> |

