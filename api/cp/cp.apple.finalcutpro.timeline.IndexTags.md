# [docs](index.md) » cp.apple.finalcutpro.timeline.IndexTags
---

Provides access to the 'Tags' section of the [Timeline Index](cp.apple.finalcutpro.timeline.Index.md)

## Submodules
 * [cp.apple.finalcutpro.timeline.IndexTags.Type](cp.apple.finalcutpro.timeline.IndexTags.Type.md)

## API Overview
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [activate](#activate)
 * [all](#all)
 * [analysisKeywords](#analysiskeywords)
 * [chapters](#chapters)
 * [completeTodos](#completetodos)
 * [incompleteTodos](#incompletetodos)
 * [keywords](#keywords)
 * [list](#list)
 * [standardMarkers](#standardmarkers)
 * [type](#type)
* Methods - API calls which can only be made on an object returned by a constructor
 * [doLayout](#dolayout)
 * [doShowAll](#doshowall)
 * [doShowAnalysisKeywords](#doshowanalysiskeywords)
 * [doShowChapters](#doshowchapters)
 * [doShowCompleteTodos](#doshowcompletetodos)
 * [doShowIncompleteTodos](#doshowincompletetodos)
 * [doShowKeywords](#doshowkeywords)
 * [doShowStandardMarkers](#doshowstandardmarkers)
 * [saveLayout](#savelayout)

## API Documentation

### Fields

#### [activate](#activate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexTags.activate <cp.ui.RadioButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [RadioButton](cp.ui.RadioButton.md) that activates the 'Tags' section. |

#### [all](#all)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexTags.all <cp.ui.RadioButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [RadioButton](cp.ui.RadioButton.md) that will show "All" types of media. |

#### [analysisKeywords](#analysiskeywords)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexTags.analysisKeywords <cp.ui.RadioButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [RadioButton](cp.ui.RadioButton.md) for the "Auto-analysis keywords" filter. |

#### [chapters](#chapters)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexTags.chapters <cp.ui.RadioButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [RadioButton](cp.ui.RadioButton.md) for the "Chapter markers" filter. |

#### [completeTodos](#completetodos)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexTags.completeTodos <cp.ui.RadioButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [RadioButton](cp.ui.RadioButton.md) for the "Complete todo marker" filter. |

#### [incompleteTodos](#incompletetodos)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexTags.incompleteTodos <cp.ui.RadioButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [RadioButton](cp.ui.RadioButton.md) for the "Incomplete todo marker" filter. |

#### [keywords](#keywords)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexTags.keywords <cp.ui.RadioButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [RadioButton](cp.ui.RadioButton.md) for the "Keywords" filter. |

#### [list](#list)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexTags.list <cp.ui.Table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The list of tags as a [Table](cp.ui.Table.md). |

#### [standardMarkers](#standardmarkers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexTags.standardMarkers <cp.ui.RadioButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [RadioButton](cp.ui.RadioButton.md) for the "Standard markers" filter. |

#### [type](#type)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexTags.type <cp.apple.finalcutpro.timeline.IndexTags.Type>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [IndexTags.Type](cp.apple.finalcutpro.timeline.IndexTags.Type.md). |

### Methods

#### [doLayout](#dolayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexTags:doLayout(layout) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that will apply the layout provided, if possible. |
| **Parameters**                                       | <ul><li>layout - the <code>table</code> containing the layout configuration. Usually created via the [#saveLayout] method.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.go.Statement.md">Statement</a>.</li></ul> |

#### [doShowAll](#doshowall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexTags:doShowAll() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that will set the tag index to "All" media types. |

#### [doShowAnalysisKeywords](#doshowanalysiskeywords)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexTags:doShowAnalysisKeywords() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that will set the tag index to "Analysis Keywords". |

#### [doShowChapters](#doshowchapters)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexTags:doShowChapters() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that will set the tag index to "Chapter" markers. |

#### [doShowCompleteTodos](#doshowcompletetodos)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexTags:doShowCompleteTodos() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that will set the tag index to "Complete Todos". |

#### [doShowIncompleteTodos](#doshowincompletetodos)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexTags:doShowIncompleteTodos() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that will set the tag index to "Incomplete Todo Markers". |

#### [doShowKeywords](#doshowkeywords)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexTags:doShowKeywords() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that will set the tag index to "Keywords". |

#### [doShowStandardMarkers](#doshowstandardmarkers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexTags:doShowStandardMarkers() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that will set the tag index to "Standard" markers. |

#### [saveLayout](#savelayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexTags:saveLayout() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `table` containing the layout configuration for this class. |
| **Returns**                                          | <ul><li>The layout configuration <code>table</code>.</li></ul> |

