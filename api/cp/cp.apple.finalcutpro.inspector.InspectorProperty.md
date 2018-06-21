# [docs](index.md) » cp.apple.finalcutpro.inspector.InspectorProperty
---

`InspectorProperty` contains helper functions for handling common property
types that occur in various `Inspectors` in FCP.

In addition to specific property row types like `textField`, `slider`, etc.,
there is also a `section`, which is for rows which expand/collapse to reveal
other properties.

## API Overview
* Functions - API calls offered directly by the extension
 * [checkBox](#checkbox)
 * [hasProperties](#hasproperties)
 * [menuButton](#menubutton)
 * [numberField](#numberfield)
 * [popUpButton](#popupbutton)
 * [section](#section)
 * [simple](#simple)
 * [slider](#slider)
 * [staticText](#statictext)
 * [textField](#textfield)
 * [xy](#xy)

## API Documentation

### Functions

#### [checkBox](#checkbox)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.InspectorProperty.checkBox(labelKey[, index]) -> cp.prop <cp.ui.PropertyRow; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates a new `cp.prop` that contains a `PropertyRow`  matching the `labelKey`.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* labelKey      - The I18N key that the row lable matches.</li><li markdown="1">* index         - The instance number of that label (defaults to `1`).</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The `cp.prop` that returns the `PropertyRow`.</li></ul>          |

#### [hasProperties](#hasproperties)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.InspectorProperty.hasProperties(parent, uiFinder) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | This will prepare the `parent` to handle containing `PropertyRow` children, and returns                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* parent    - The parent table.</li><li markdown="1">* uiFinder  - The function or cp.prop which will be called to find the parent UI element. Functions will be passed the `parent` when being executed.</li></ul> |
| **Returns**                                          | <ul markdown="1"></ul>          |

#### [menuButton](#menubutton)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.InspectorProperty.menuButton(labelKey[, index]) -> cp.prop <cp.ui.PropertyRow; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates a new `cp.prop` that contains a `PropertyRow`  matching the `labelKey`.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* labelKey      - The I18N key that the row lable matches.</li><li markdown="1">* index         - The instance number of that label (defaults to `1`).</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The `cp.prop` that returns the `PropertyRow`.</li></ul>          |

#### [numberField](#numberfield)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.InspectorProperty.numberField(labelKey[, index]) -> cp.prop <cp.ui.PropertyRow; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates a new `cp.prop` that contains a `PropertyRow`  matching the `labelKey`.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* labelKey      - The I18N key that the row lable matches.</li><li markdown="1">* index         - The instance number of that label (defaults to `1`).</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The `cp.prop` that returns the `PropertyRow`.</li></ul>          |

#### [popUpButton](#popupbutton)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.InspectorProperty.popUpButton(labelKey[, index]) -> cp.prop <cp.ui.PropertyRow; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates a new `cp.prop` that contains a `PropertyRow`  matching the `labelKey`.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* labelKey      - The I18N key that the row lable matches.</li><li markdown="1">* index         - The instance number of that label (defaults to `1`).</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The `cp.prop` that returns the `PropertyRow`.</li></ul>          |

#### [section](#section)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.InspectorProperty.section(labelKey[, index]) -> function` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a 'section row' factory function that can be called to create a section row that contains other `PropertyRow' `cp.prop`s.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* labelKey      - The I18N lookup key to find the row with.</li><li markdown="1">* index         - (optional) The occurrence of the key value in the parent. Sometimes multiple rows have the same title. Defaults to `1`.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* A function which will create the section row when called.</li></ul>          |

#### [simple](#simple)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.InspectorProperty.simple(labelKey[, prepareFn][, index]]) -> cp.prop <cp.ui.PropertyRow; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates a new `cp.prop` that contains a `PropertyRow`  matching the `labelKey`.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* labelKey      - The I18N key that the row lable matches.</li><li markdown="1">* prepareFn     - The function to call to perform additional preparations on the row.</li><li markdown="1">* index         - The instance number of that label (defaults to `1`).</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The `cp.prop` that returns the `PropertyRow`.</li></ul>          |

#### [slider](#slider)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.InspectorProperty.slider(labelKey[, index]) -> cp.prop <cp.ui.PropertyRow; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates a new `cp.prop` that contains a `PropertyRow`  matching the `labelKey`.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* labelKey      - The I18N key that the row lable matches.</li><li markdown="1">* index         - The instance number of that label (defaults to `1`).</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The `cp.prop` that returns the `PropertyRow`.</li></ul>          |

#### [staticText](#statictext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.InspectorProperty.staticText(labelKey[, index]) -> cp.prop <cp.ui.PropertyRow; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates a new `cp.prop` that contains a `PropertyRow`  matching the `labelKey`.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* labelKey      - The I18N key that the row lable matches.</li><li markdown="1">* index         - The instance number of that label (defaults to `1`).</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The `cp.prop` that returns the `PropertyRow`.</li></ul>          |

#### [textField](#textfield)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.InspectorProperty.textField(labelKey[, index]) -> cp.prop <cp.ui.PropertyRow; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates a new `cp.prop` that contains a `PropertyRow`  matching the `labelKey`.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* labelKey      - The I18N key that the row lable matches.</li><li markdown="1">* index         - The instance number of that label (defaults to `1`).</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The `cp.prop` that returns the `PropertyRow`.</li></ul>          |

#### [xy](#xy)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.InspectorProperty.xy(labelKey[, index]) -> cp.prop <cp.ui.PropertyRow; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates a new `cp.prop` that contains a `PropertyRow`  matching the `labelKey`.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* labelKey      - The I18N key that the row lable matches.</li><li markdown="1">* index         - The instance number of that label (defaults to `1`).</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The `cp.prop` that returns the `PropertyRow`.</li></ul>          |

