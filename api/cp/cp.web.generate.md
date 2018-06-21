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
| **Parameters**                                       |  * data - Table containing the data you want to display on the Checkbox * customTrigger - Custom label used for JavaScript Callback * customWidth - Number to set the width of the button to * customID - Overrides the random HTML ID                                       |
| **Returns**                                          |  * String containing the HTML                                                |

#### [checkbox](#checkbox)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.generate.checkbox() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Generates a HTML Checkbox                                                                                         |
| **Parameters**                                       |  * data - Table containing the data you want to display on the Checkbox * customTrigger - Custom label used for JavaScript Callback * customID - Custom ID used for the HTML objects                                       |
| **Returns**                                          |  * String containing the HTML                                                |

#### [dropdown](#dropdown)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.generate.dropdown() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Generates a HTML Dropdown                                                                                         |
| **Parameters**                                       |  * title - Title to put in front of the Dropdown. Can be "". * data - Table containing the data you want to display on the Checkbox * customTrigger - Custom label used for JavaScript Callback                                       |
| **Returns**                                          |  * String containing the HTML                                                |

#### [heading](#heading)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.generate.heading() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Generates a HTML Heading                                                                                         |
| **Parameters**                                       |  * data - Table containing the data you want to display on the Checkbox                                       |
| **Returns**                                          |  * String containing the HTML                                                |

#### [javascript](#javascript)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.generate.javascript(script, context) -> cp.web.html` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Generates a HTML Heading                                                                                         |
| **Parameters**                                       |  * data - Table containing the data you want to display on the Checkbox                                       |
| **Returns**                                          |  * String containing the HTML                                                |

#### [setWebviewLabel](#setwebviewlabel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.generate.setWebviewLabel() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the WebView Label                                                                                         |
| **Parameters**                                       |  * value - WebView Label as string                                       |
| **Returns**                                          |  * None                                                |

#### [text](#text)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.web.generate.text() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Generates a blank HTML                                                                                         |
| **Parameters**                                       |  * data - Table containing the data you want to display.                                       |
| **Returns**                                          |  * String containing the HTML                                                |

