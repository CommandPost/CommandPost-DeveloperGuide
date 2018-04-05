# [docs](index.md) » cp.ui.TextField
---

Text Field Module.

## API Overview
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [value](#value)
* Methods - API calls which can only be made on an object returned by a constructor
 * [new](#new)
 * [snapshot](#snapshot)

## API Documentation

### Fields

#### [value](#value)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextField.value <cp.prop: anything>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The current value of the text field.                                                                                         |

### Methods

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextField.new(parent, finderFn[, convertFn]) -> TextField` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a new TextField. They have a parent and a finder function.                                                                                         |
| **Parameters**                                       | <ul><li>* parent	- The parent object.</li><li>* finderFn	- The function will return the `axuielement` for the TextField.</li><li>* convertFn	- (optional) If provided, will be passed the `string` value when returning.</li></ul> |
| **Returns**                                          | <ul><li>* The new `TextField`.</li></ul>          |

#### [snapshot](#snapshot)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.TextField:snapshot([path]) -> hs.image | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Takes a snapshot of the UI in its current state as a PNG and returns it.                                                                                         |
| **Parameters**                                       | <ul><li>* path		- (optional) The path to save the file. Should include the extension (should be `.png`).</li></ul> |

