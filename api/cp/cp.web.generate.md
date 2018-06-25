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
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Generates a HTML Button                                                                                         |
| **Parameters**                                       | <ul><br /><li>data - Table containing the data you want to display on the Checkbox * customTrigger - Custom label used for JavaScript Callback * customWidth - Number to set the width of the button to * customID - Overrides the random HTML ID</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>String containing the HTML</li><br /></ul>                                           |

#### [checkbox](#checkbox)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.generate.checkbox() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Generates a HTML Checkbox                                                                                         |
| **Parameters**                                       | <ul><br /><li>data - Table containing the data you want to display on the Checkbox * customTrigger - Custom label used for JavaScript Callback * customID - Custom ID used for the HTML objects</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>String containing the HTML</li><br /></ul>                                           |

#### [dropdown](#dropdown)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.generate.dropdown() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Generates a HTML Dropdown                                                                                         |
| **Parameters**                                       | <ul><br /><li>title - Title to put in front of the Dropdown. Can be "". * data - Table containing the data you want to display on the Checkbox * customTrigger - Custom label used for JavaScript Callback</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>String containing the HTML</li><br /></ul>                                           |

#### [heading](#heading)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.generate.heading() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Generates a HTML Heading                                                                                         |
| **Parameters**                                       | <ul><br /><li>data - Table containing the data you want to display on the Checkbox</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>String containing the HTML</li><br /></ul>                                           |

#### [javascript](#javascript)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.generate.javascript(script, context) -> cp.web.html` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Generates a HTML Heading                                                                                         |
| **Parameters**                                       | <ul><br /><li>data - Table containing the data you want to display on the Checkbox</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>String containing the HTML</li><br /></ul>                                           |

#### [setWebviewLabel](#setwebviewlabel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.generate.setWebviewLabel() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the WebView Label                                                                                         |
| **Parameters**                                       | <ul><br /><li>value - WebView Label as string</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [text](#text)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.generate.text() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Generates a blank HTML                                                                                         |
| **Parameters**                                       | <ul><br /><li>data - Table containing the data you want to display.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>String containing the HTML</li><br /></ul>                                           |

