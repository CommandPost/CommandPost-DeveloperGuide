# [docs](index.md) » cp.web.generate
---

Functions for Generating HTML UI Items

## API Overview
* Functions - API calls offered directly by the extension
 * [button](#button)
 * [checkbox](#checkbox)
 * [dropdown](#dropdown)
 * [heading](#heading)
 * [javascript](#javascript)
 * [setWebviewLabel](#setwebviewlabel)
 * [text](#text)

## API Documentation

### Functions

#### [button](#button)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.generate.button() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Generates a HTML Button |
| **Parameters**                                       | <ul><li>data - Table containing the data you want to display on the Checkbox * customTrigger - Custom label used for JavaScript Callback * customWidth - Number to set the width of the button to * customID - Overrides the random HTML ID</li></ul> |
| **Returns**                                          | <ul><li>String containing the HTML</li></ul> |

#### [checkbox](#checkbox)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.generate.checkbox() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Generates a HTML Checkbox |
| **Parameters**                                       | <ul><li>data - Table containing the data you want to display on the Checkbox * customTrigger - Custom label used for JavaScript Callback * customID - Custom ID used for the HTML objects</li></ul> |
| **Returns**                                          | <ul><li>String containing the HTML</li></ul> |

#### [dropdown](#dropdown)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.generate.dropdown() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Generates a HTML Dropdown |
| **Parameters**                                       | <ul><li>title - Title to put in front of the Dropdown. Can be "". * data - Table containing the data you want to display on the Checkbox * customTrigger - Custom label used for JavaScript Callback</li></ul> |
| **Returns**                                          | <ul><li>String containing the HTML</li></ul> |

#### [heading](#heading)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.generate.heading() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Generates a HTML Heading |
| **Parameters**                                       | <ul><li>data - Table containing the data you want to display on the Checkbox</li></ul> |
| **Returns**                                          | <ul><li>String containing the HTML</li></ul> |

#### [javascript](#javascript)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.generate.javascript(script, context) -> cp.web.html` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Generates a HTML Heading |
| **Parameters**                                       | <ul><li>data - Table containing the data you want to display on the Checkbox</li></ul> |
| **Returns**                                          | <ul><li>String containing the HTML</li></ul> |

#### [setWebviewLabel](#setwebviewlabel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.generate.setWebviewLabel() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sets the WebView Label |
| **Parameters**                                       | <ul><li>value - WebView Label as string</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [text](#text)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.generate.text() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Generates a blank HTML |
| **Parameters**                                       | <ul><li>data - Table containing the data you want to display.</li></ul> |
| **Returns**                                          | <ul><li>String containing the HTML</li></ul> |

