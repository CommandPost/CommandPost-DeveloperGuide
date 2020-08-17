# [docs](index.md) » cp.apple.finalcutpro.timeline.IndexMode
---

Timeline Index Mode Radio Group Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [IndexMode](#indexmode)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [captions](#captions)
 * [clips](#clips)
 * [roles](#roles)
 * [tags](#tags)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexMode.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the element is the `IndexMode`. |
| **Parameters**                                       | <ul><li>element - The <code>axuielement</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if it matches, otherwise <code>false</code>.</li></ul> |

### Constructors

#### [IndexMode](#indexmode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexMode(index) -> cp.apple.finalcutpro.timeline.IndexMode` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `IndexMode` instance. |
| **Parameters**                                       | <ul><li>index - The <a href="cp.apple.finalcutpro.timeline.Index.md">Index</a> that contains the <code>mode</code>.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>IndexMode</code> instance.</li></ul> |

### Fields

#### [captions](#captions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexMode.captions <cp.ui.RadioButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [RadioButton](cp.ui.RadioButton.ui) for the "Captions" mode. |

#### [clips](#clips)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexMode.clips <cp.ui.RadioButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [RadioButton](cp.ui.RadioButton.ui) for the "Clips" mode. |

#### [roles](#roles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexMode.roles <cp.ui.RadioButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [RadioButton](cp.ui.RadioButton.ui) for the "Roles" mode. |

#### [tags](#tags)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexMode.tags <cp.ui.RadioButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [RadioButton](cp.ui.RadioButton.ui) for the "Tags" mode. |

