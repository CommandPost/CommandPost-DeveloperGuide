# [docs](index.md) » cp.ui.StaticText
---

Static Text Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [value](#value)
* Methods - API calls which can only be made on an object returned by a constructor
 * [clear](#clear)
 * [loadLayout](#loadlayout)
 * [saveLayout](#savelayout)
 * [StaticText](#statictext)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.StaticText.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the element is a Static Text element. |
| **Parameters**                                       | <ul><li>element      - The <code>axuielement</code> to check.</li></ul> |
| **Returns**                                          | <ul><li>If <code>true</code>, the element is a Static Text element.</li></ul> |

### Fields

#### [value](#value)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.StaticText.value <cp.prop: anything>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The current value of the text field. |

### Methods

#### [clear](#clear)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.StaticText:clear() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Clears the value of a Static Text box. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Self</li></ul> |

#### [loadLayout](#loadlayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.StaticText:loadLayout(layout) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Loads a Static Text layout. |
| **Parameters**                                       | <ul><li>layout - A table containing the Static Text layout settings - created using <code>cp.ui.StaticText:saveLayout()</code>.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [saveLayout](#savelayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.StaticText:saveLayout() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Saves the current Static Text layout to a table. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table containing the current Static Text Layout.</li></ul> |

#### [StaticText](#statictext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.StaticText(parent, uiFinder[, convertFn]) -> StaticText` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Creates a new StaticText. They have a parent and a finder function. |
| **Parameters**                                       | <ul><li>parent   - The parent object.</li><li>uiFinder - The function will return the <code>axuielement</code> for the StaticText.</li><li>convertFn    - (optional) If provided, will be passed the <code>string</code> value when returning.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>StaticText</code>.</li></ul> |

