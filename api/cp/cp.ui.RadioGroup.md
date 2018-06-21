# [docs](index.md) » cp.ui.RadioGroup
---

Represents an `AXRadioGroup`, providing utility methods.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [optionCount](#optioncount)
 * [selectedOption](#selectedoption)
* Methods - API calls which can only be made on an object returned by a constructor
 * [isEnabled](#isenabled)
 * [isShowing](#isshowing)
 * [new](#new)
 * [nextOption](#nextoption)
 * [parent](#parent)
 * [previousOption](#previousoption)
 * [snapshot](#snapshot)
 * [UI](#ui)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.RadioGroup.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the provided `axuielement` is a RadioGroup.                                                                                         |
| **Parameters**                                       | * element	- The element to check.                                       |
| **Returns**                                          | * `true` if the element is a RadioGroup.                                                |

### Fields

#### [optionCount](#optioncount)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.RadioGroup.optionCount <cp.prop: number; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The number of options in the group.                                                                                         |

#### [selectedOption](#selectedoption)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.RadioGroup.selectedOption <cp.prop: number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The currently selected option number.                                                                                         |

### Methods

#### [isEnabled](#isenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.RadioGroup:isEnabled()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Checks if the RadioGroup is enabled.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * `true` if the RadioGroup is showing and enabled.                                                |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.RadioGroup:isShowing() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Checks if the RadioGroup is visible.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * `true` if the RadioGroup is visible.                                                |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.RadioGroup.new(parent, finderFn[, cached]) -> RadioGroup` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a new RadioGroup.                                                                                         |
| **Parameters**                                       | * parent	- The parent table.* finderFn	- The function which will find the `axuielement` representing the RadioGroup.* cached	- If set to `false`, the `axuielement` will not be cached. Defaults to `true`.                                       |
| **Returns**                                          | * The new `RadioGroup` instance.                                                |

#### [nextOption](#nextoption)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.RadioGroup:nextOption() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Selects the next option in the group. Cycles from the last to the first option.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The `RadioGroup`.                                                |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.RadioGroup:parent() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the parent object.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The parent object.                                                |

#### [previousOption](#previousoption)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.RadioGroup:previousOption() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Selects the previous option in the group. Cycles from the first to the last item.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The `RadioGroup`.                                                |

#### [snapshot](#snapshot)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.RadioGroup:snapshot([path]) -> hs.image | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Takes a snapshot of the UI in its current state as a PNG and returns it.                                                                                         |
| **Parameters**                                       | * path		- (optional) The path to save the file. Should include the extension (should be `.png`).                                       |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.RadioGroup:UI() -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `axuielement` for the RadioGroup, or `nil` if not currently visible.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The `asuielement` or `nil`.                                                |

