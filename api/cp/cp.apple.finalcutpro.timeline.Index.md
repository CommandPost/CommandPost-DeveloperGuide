# [docs](index.md) » cp.apple.finalcutpro.timeline.Index
---

Timeline Index Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [Index](#index)
* Methods - API calls which can only be made on an object returned by a constructor
 * [activeTab](#activetab)
 * [captions](#captions)
 * [clips](#clips)
 * [doHide](#dohide)
 * [doLayout](#dolayout)
 * [doShow](#doshow)
 * [mode](#mode)
 * [roles](#roles)
 * [saveLayout](#savelayout)
 * [search](#search)
 * [tags](#tags)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Index.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks to see if an element matches what we think it should be. |
| **Parameters**                                       | <ul><li>element - An <code>axuielementObject</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if matches otherwise <code>false</code></li></ul> |

### Constructors

#### [Index](#index)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Index(parent, uiFinder) -> cp.apple.finalcutpro.timeline.Index` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new Timeline Index. |
| **Parameters**                                       | <ul><li>timeline     - <a href="cp.apple.finalcutpro.timeline.Timeline.md">Timeline</a>.</li></ul> |
| **Returns**                                          | <ul><li>A new <code>Index</code> instance.</li></ul> |

### Methods

#### [activeTab](#activetab)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Index:activeTab() -> object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the active tab. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The active tab or <code>nil</code>.</li></ul> |

#### [captions](#captions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Index:captions() -> cp.apple.finalcutpro.timeline.IndexCaptions` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The [IndexCaptions](cp.apple.finalcutpro.timeline.IndexCaptions.md). |

#### [clips](#clips)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Index:clips() -> cp.apple.finalcutpro.timeline.IndexClips` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The [IndexClips](cp.apple.finalcutpro.timeline.IndexClips.md). |

#### [doHide](#dohide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Index:doHide() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) which will hide the Index if possible. |

#### [doLayout](#dolayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Index:doLayout(layout) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that will apply the layout provided, if possible. |
| **Parameters**                                       | <ul><li>layout - the <code>table</code> containing the layout configuration. Usually created via the [#saveLayout] method.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.go.Statement.md">Statement</a>.</li></ul> |

#### [doShow](#doshow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Index:doShow() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) which will show the Index if possible. |

#### [mode](#mode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Index:mode() -> cp.apple.finalcutpro.timeline.IndexMode` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The [IndexMode](cp.apple.finalcutpro.timeline.IndexMode.md) for the Index. |
| **Returns**                                          | <ul><li>The <code>IndexMode</code>.</li></ul> |

#### [roles](#roles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Index:roles() -> cp.apple.finalcutpro.timeline.IndexRoles` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The [IndexRoles](cp.apple.finalcutpro.timeline.IndexRoles.md). |

#### [saveLayout](#savelayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Index:saveLayout() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `table` containing the layout configuration for this class. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The layout configuration <code>table</code>.</li></ul> |

#### [search](#search)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Index:search() -> cp.ui.SearchField` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The [SearchField](cp.ui.SearchField.md) for the Timeline Index. |
| **Returns**                                          | <ul><li>The SearchField.</li></ul> |

#### [tags](#tags)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Index:tags() -> cp.apple.finalcutpro.timeline.IndexTags` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The [IndexTags](cp.apple.finalcutpro.timeline.IndexTags.md). |

