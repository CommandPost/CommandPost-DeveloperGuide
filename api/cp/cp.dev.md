# [docs](index.md) » cp.dev
---

A set of handy developer tools for CommandPost.

## API Overview
* Functions - API calls offered directly by the extension
 * [elementAtMouse](#elementatmouse)
 * [findUnusedLanguageStrings](#findunusedlanguagestrings)
 * [highlight](#highlight)
 * [highlightFrame](#highlightframe)
 * [highlightPoint](#highlightpoint)
 * [hotkey](#hotkey)
 * [inspect](#inspect)
 * [inspectAtMouse](#inspectatmouse)
 * [inspectElement](#inspectelement)
 * [inspectElementAtMousePath](#inspectelementatmousepath)
 * [test](#test)
 * [which](#which)

## API Documentation

### Functions

#### [elementAtMouse](#elementatmouse)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.dev.elementAtMouse() -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets the AX element under the current mouse position. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [findUnusedLanguageStrings](#findunusedlanguagestrings)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.dev.findUnusedLanguageStrings() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Searches for any unused language strings in English.json. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string with the results of the search.</li></ul> |

#### [highlight](#highlight)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.dev.highlight(element) -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Highlights an AX element on the screen. |
| **Parameters**                                       | <ul><li>element - The AX element to highlight.</li></ul> |
| **Returns**                                          | <ul><li>The element.</li></ul> |

#### [highlightFrame](#highlightframe)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.dev.highlightFrame(frame) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Highlights aa frame on the screen. |
| **Parameters**                                       | <ul><li>frame - A <code>hs.geometry</code> frame object.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [highlightPoint](#highlightpoint)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.dev.highlightPoint(point) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Highlights a point on the screen. |
| **Parameters**                                       | <ul><li>point - A <code>hs.geometry</code> point object.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [hotkey](#hotkey)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.dev.hotkey(fn) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Assigns a function to the CONTROL+OPTION+COMMAND+SHIFT+Q keyboard combination. |
| **Parameters**                                       | <ul><li>fn - A function to execute when the hotkey is triggered.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [inspect](#inspect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.dev.inspect(item, options) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Inspect an item. |
| **Parameters**                                       | <ul><li>item - The object to inspect.</li><li>options - Any additional options to pass along to <code>cp.dev.inspectElement</code>.</li></ul> |
| **Returns**                                          | <ul><li>A results as a string.</li></ul> |

#### [inspectAtMouse](#inspectatmouse)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.dev.inspectAtMouse(options) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Inspects an AX element under the current mouse position. |
| **Parameters**                                       | <ul><li>options - Any additional options to pass along to <code>cp.dev.inspectElement</code>.</li></ul> |
| **Returns**                                          | <ul><li>A string containing the results.</li></ul> |

#### [inspectElement](#inspectelement)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.dev.inspectElement() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Inspect an AX element. |
| **Parameters**                                       | <ul><li>element - The element to inspect.</li><li>options - A table containing any optional values.</li></ul> |
| **Returns**                                          | <ul><li>The results as a string.</li></ul> |
| **Notes**                                            | <ul><li>The options table accepts the following parameters:</li><li>depth - A number representing the maximum depth to recurse into variable.</li></ul> |

#### [inspectElementAtMousePath](#inspectelementatmousepath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.dev.inspectElementAtMousePath() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Inspects an AX element at the mouse path. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [test](#test)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.dev.test(id) -> cp.test` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | This function will return a [cp.test](cp.test.md) with either the |
| **Parameters**                                       | <ul><li>id - the <code>id</code> to test.</li></ul> |
| **Returns**                                          | <ul><li>A [cp.test] to execute.</li></ul> |

#### [which](#which)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.dev.which(cmd) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | The which utility takes a list of command names and searches the path for |
| **Parameters**                                       | <ul><li>cmd - The parameters to pass along to the <code>which</code> executable.</li></ul> |
| **Returns**                                          | <ul><li>The path or <code>nil</code> and the error message if an error occurs.</li></ul> |

