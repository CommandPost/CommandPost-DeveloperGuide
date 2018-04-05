# [docs](index.md) » cp.ui.PropertyRow
---

Represents a single property row, typically in a Property Inspector.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [isShowing](#isshowing)
 * [label](#label)
 * [labelUI](#labelui)
 * [propertiesUI](#propertiesui)
 * [reset](#reset)
 * [UI](#ui)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PropertyRow.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the provided `axuielement` could be a property row.                                                                                         |
| **Parameters**                                       | <ul><li>* element   - The element to check.</li></ul> |
| **Returns**                                          | <ul><li>* `true` if the element could be a property row.</li></ul>          |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PropertyRow.new(parent, labelKey[, propertiesUI[, index]]) -> cp.ui.PropertyRow` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `PropertyRow` with the specified parent and label key.                                                                                         |
| **Parameters**                                       | <ul><li>* parent        - The parent object.</li><li>* labelKey      - The key of the label that the row will map to.</li><li>* propertiesUI  - The name of the key in the parent to find the properties in. Defaults to `UI`.</li><li>* index         - The row number with the same label to get. Defaults to `1`.</li></ul> |
| **Returns**                                          | <ul><li>* The new `PropertyRow` instance.</li></ul>          |

### Fields

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PropertyRow.isShowing <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Checks if the row is showing.                                                                                         |

#### [label](#label)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PropertyRow.label <cp.prop: string; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The label of the property row, in the current langauge.                                                                                         |

#### [labelUI](#labelui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PropertyRow.labelUI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The `axuielement` containing the row label.                                                                                         |

#### [propertiesUI](#propertiesui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PropertyRow.propertiesUI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The `axuielement` from the parent that contains the properties.                                                                                         |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PropertyRow.reset <cp.ui.Button>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The `reset` button for the row, which may or may not actually exist.                                                                                         |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PropertyRow.UI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns the `axuielement` for the row.                                                                                         |

