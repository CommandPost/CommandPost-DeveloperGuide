# [docs](index.md) » cp.ui.TextArea
---

UI Text Area.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [TextArea](#textarea)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [focused](#focused)
 * [value](#value)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextArea.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks to see if an element matches what we think it should be. |
| **Parameters**                                       | <ul><li>element - An <code>axuielementObject</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if matches otherwise <code>false</code></li></ul> |

### Constructors

#### [TextArea](#textarea)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextArea(parent, uiFinder) -> TextArea` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `TextArea` instance. |
| **Parameters**                                       | <ul><li>parent - The parent object.</li><li>uiFinder - A function which will return the <code>hs._asm.axuielement</code> when available.</li></ul> |
| **Returns**                                          | <ul><li>A new <code>TextArea</code> object.</li></ul> |

### Fields

#### [focused](#focused)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextArea.focused <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Whether or not the Text Area if focused. |

#### [value](#value)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextArea.value <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The current value of the text field. |

