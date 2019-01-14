# [docs](index.md) » cp.apple.finalcutpro.timeline.IndexSection
---

An abstract base class for sections inside the [Index](cp.apple.finalcutpro.timeline.Index.md).
This contains common methods and other definitions that apply for all sections.

This will generally not be created directly, but will be created via subclass such as
[IndexClips](cp.apple.finalcutpro.timeline.IndexClips.md).

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [IndexSection](#indexsection)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [isShowing](#isshowing)
 * [UI](#ui)
* Methods - API calls which can only be made on an object returned by a constructor
 * [activate](#activate)
 * [app](#app)
 * [doActivateSearch](#doactivatesearch)
 * [doShow](#doshow)
 * [index](#index)
 * [parent](#parent)
 * [search](#search)

## API Documentation

### Constructors

#### [IndexSection](#indexsection)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexSection(index) -> IndexSection` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates the `IndexSection` instance. |
| **Parameters**                                       | <ul><li>index - The <a href="cp.apple.finalcutpro.timeline.Index.md">Index</a> instance.</li></ul> |

### Fields

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexSection.isShowing <cp.prop: boolean; read-only; live?>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Indicates if the section is currently showing. |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexSection.UI <cp.prop: axuielement; read-only; live?>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `axuielement` that represents the item. |

### Methods

#### [activate](#activate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexSection:activate() -> cp.ui.RadioButton` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The [RadioButton](cp.ui.RadioButton.md) that activates the section. |
| **Notes**                                            | <ul><li>Must be overridden in subclasses to provide the actual RadioButton.</li></ul> |

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexSection:app() -> cp.apple.finalcutpro` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The [Final Cut Pro](cp.apple.finalcutpro.md) instance. |

#### [doActivateSearch](#doactivatesearch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexSection:doActivateSearch() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that will show the Clips in the Timeline Index and focus on the Search field. |

#### [doShow](#doshow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexSection:doShow() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will show the Clips section in the Timeline Index, if possible. |
| **Returns**                                          | <ul><li>The <a href="cp.rx.go.Statement.md">Statement</a></li></ul> |

#### [index](#index)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexSection:index() -> cp.apple.finalcutpro.timeline.Index` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The parent [Index](cp.apple.finalcutpro.timeline.Index.md). |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexSection:parent() -> cp.apple.finalcutpro.timeline.Index` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The parent index. |

#### [search](#search)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexSection:search() -> cp.ui.SearchField` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The shared [SearchField](cp.ui.SearchField.md) for the [Index](cp.apple.finalcutpro.timeline.Index.md) |

