# [docs](index.md) » cp.ui.StaticText
---

Static Text Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [new](#new)
 * [parent](#parent)
 * [snapshot](#snapshot)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.StaticText.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the element is a Static Text element.                                                                                         |
| **Parameters**                                       | <ul><li>* element		- The `axuielement` to check.</li></ul> |
| **Returns**                                          | <ul><li>* If `true`, the element is a Static Text element.</li></ul>          |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.StaticText:app() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the app object.                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* The app.</li></ul>          |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.StaticText.new(parent, finderFn[, convertFn]) -> StaticText` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a new StaticText. They have a parent and a finder function.                                                                                         |
| **Parameters**                                       | <ul><li>* parent	- The parent object.</li><li>* finderFn	- The function will return the `axuielement` for the StaticText.</li><li>* convertFn	- (optional) If provided, will be passed the `string` value when returning.</li></ul> |
| **Returns**                                          | <ul><li>* The new `StaticText`.</li></ul>          |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.StaticText:parent() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the parent object.                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* The parent.</li></ul>          |

#### [snapshot](#snapshot)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.StaticText:snapshot([path]) -> hs.image | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Takes a snapshot of the UI in its current state as a PNG and returns it.                                                                                         |
| **Parameters**                                       | <ul><li>* path		- (optional) The path to save the file. Should include the extension (should be `.png`).</li></ul> |

