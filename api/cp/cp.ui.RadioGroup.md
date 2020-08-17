# [docs](index.md) » cp.ui.RadioGroup
---

Represents an `AXRadioGroup`, providing utility methods.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [RadioGroup](#radiogroup)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [optionCount](#optioncount)
 * [options](#options)
 * [optionsUI](#optionsui)
 * [selectedOption](#selectedoption)
* Methods - API calls which can only be made on an object returned by a constructor
 * [doNextOption](#donextoption)
 * [doPreviousOption](#dopreviousoption)
 * [doSelectOption](#doselectoption)
 * [nextOption](#nextoption)
 * [previousOption](#previousoption)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.RadioGroup.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the provided `axuielement` is a RadioGroup. |
| **Parameters**                                       | <ul><li>element   - The element to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the element is a RadioGroup.</li></ul> |

### Constructors

#### [RadioGroup](#radiogroup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.RadioGroup(parent, uiFinder[, createOptionFn]) -> cp.ui.RadioGroup` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new RadioGroup. |
| **Parameters**                                       | <ul><li>parent           - The parent table.</li><li>uiFinder         - The function which will find the <code>axuielement</code> representing the RadioGroup.</li><li>createOptionFn   - If provided a function that receives the <code>RadioGroup</code> and an <code>axuielement</code> for a given option within the group.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>RadioGroup</code> instance.</li></ul> |

### Fields

#### [optionCount](#optioncount)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.RadioGroup.optionCount <cp.prop: number; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The number of options in the group. |

#### [options](#options)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.RadioGroup.options <table: cp.ui.Element; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A `table` containing `cp.ui.Element` available in the radio group. |
| **Returns**                                          | <ul><li>The <code>cp.prop</code> of options.</li></ul> |

#### [optionsUI](#optionsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.RadioGroup.optionsUI <cp.prop: axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A `cp.prop` containing `table` of `axuielement` options available in the radio group. |
| **Returns**                                          | <ul><li>The <code>cp.prop</code> of options.</li></ul> |

#### [selectedOption](#selectedoption)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.RadioGroup.selectedOption <cp.prop: number>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The currently selected option number. |

### Methods

#### [doNextOption](#donextoption)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.RadioGroup:doNextOption() -> cp.rx.go.Statement<boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that selects the next option in the group. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code>, that resolves to <code>true</code> if successful or sends an error if not.</li></ul> |

#### [doPreviousOption](#dopreviousoption)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.RadioGroup:doPreviousOption() -> cp.rx.go.Statement<boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that selects the previous option in the group. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code>, which resolves to <code>true</code> if successful or sends an error if not..</li></ul> |

#### [doSelectOption](#doselectoption)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.RadioGroup:doSelectOption(index) -> cp.rx.go.Statement<boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) which will attempt to select the option at the specified `index`. |
| **Parameters**                                       | <ul><li>index     - The index to select. Must be between 1 and <a href="#optionCount">optionCount</a>.</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code>, which will resolve to <code>true</code> if successful or send an error if not.</li></ul> |

#### [nextOption](#nextoption)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.RadioGroup:nextOption() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Selects the next option in the group. Cycles from the last to the first option. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>RadioGroup</code>.</li></ul> |

#### [previousOption](#previousoption)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.RadioGroup:previousOption() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Selects the previous option in the group. Cycles from the first to the last item. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>RadioGroup</code>.</li></ul> |

