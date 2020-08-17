# [docs](index.md) » cp.apple.finalcutpro.timeline.IndexClips
---

*Extends [IndexSection](cp.apple.finalcutpro.timeline.IndexSection.md)*

Provides access to the 'Clips' section of the [Timeline Index](cp.apple.finalcutpro.timeline.Index.md)

## Submodules
 * [cp.apple.finalcutpro.timeline.IndexClips.Type](cp.apple.finalcutpro.timeline.IndexClips.Type.md)

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [IndexClips](#indexclips)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [activate](#activate)
 * [all](#all)
 * [audio](#audio)
 * [list](#list)
 * [titles](#titles)
 * [type](#type)
 * [video](#video)
* Methods - API calls which can only be made on an object returned by a constructor
 * [doFindAuditions](#dofindauditions)
 * [doFindClipsContaining](#dofindclipscontaining)
 * [doFindCompoundClips](#dofindcompoundclips)
 * [doFindMissingMedia](#dofindmissingmedia)
 * [doFindMulticams](#dofindmulticams)
 * [doFindSynchronized](#dofindsynchronized)
 * [doLayout](#dolayout)
 * [doShowAll](#doshowall)
 * [doShowAudio](#doshowaudio)
 * [doShowTitles](#doshowtitles)
 * [doShowVideo](#doshowvideo)
 * [saveLayout](#savelayout)

## API Documentation

### Constructors

#### [IndexClips](#indexclips)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexClips(index) -> IndexClips` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates the `IndexClips` instance. |
| **Parameters**                                       | <ul><li>index - The <a href="cp.apple.finalcutpro.timeline.Index.md">Index</a> instance.</li></ul> |

### Fields

#### [activate](#activate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexClips.activate <cp.ui.RadioButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [RadioButton](cp.ui.RadioButton.md) that activates the 'Clips' section. |

#### [all](#all)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexClips.all <cp.ui.RadioButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [RadioButton](cp.ui.RadioButton.md) that will show "All" types of media. |

#### [audio](#audio)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexClips.audio <cp.ui.RadioButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [RadioButton](cp.ui.RadioButton.md) for the "Audio" filter. |

#### [list](#list)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexClips.list <cp.ui.Table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The list of clips as a [Table](cp.ui.Table.md). |

#### [titles](#titles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexClips.titles <cp.ui.RadioButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [RadioButton](cp.ui.RadioButton.md) for the "Titles" filter. |

#### [type](#type)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexClips.type <cp.apple.finalcutpro.timeline.IndexClips.Type>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [IndexClips.Type](cp.apple.finalcutpro.timeline.IndexClips.Type.md). |

#### [video](#video)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexClips.video <cp.ui.RadioButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [RadioButton](cp.ui.RadioButton.md) for the "Video" filter. |

### Methods

#### [doFindAuditions](#dofindauditions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexClips:doFindAuditions() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that will use the index to search for all "Auditions". |

#### [doFindClipsContaining](#dofindclipscontaining)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexClips:doFindClipsContaining(text) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.go.rx.Statement.md) that will use the index to search for clips containing the specified text. |
| **Parameters**                                       | <ul><li>text - The text to search for.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.go.Statement.md">Statement</a></li></ul> |
| **Notes**                                            | <ul><li>Because the <code>text</code> can change each time, this result is not cached automatically. However as long as you are searching for the same text the result can be safely cached. The [#toFindMissingMedia] method does this, for example.</li></ul> |

#### [doFindCompoundClips](#dofindcompoundclips)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexClips:doFindCompoundClips() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that will use the index to search for all "Compound Clips". |

#### [doFindMissingMedia](#dofindmissingmedia)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexClips:doFindMissingMedia() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that will use the index to search for all "Missing Media". |

#### [doFindMulticams](#dofindmulticams)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexClips:doFindMulticams() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that will use the index to search for all "Multicam" clips. |

#### [doFindSynchronized](#dofindsynchronized)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexClips:doFindSynchronized() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that will use the index to search for all "Synchronized" Clips. |

#### [doLayout](#dolayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexClips:doLayout(layout) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that will apply the layout provided, if possible. |
| **Parameters**                                       | <ul><li>layout - the <code>table</code> containing the layout configuration. Usually created via the [#saveLayout] method.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.go.Statement.md">Statement</a>.</li></ul> |

#### [doShowAll](#doshowall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexClips:doShowAll() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that will set the clip index to "All" media types. |

#### [doShowAudio](#doshowaudio)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexClips:doShowAudio() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that will set the clip index to "Audio" media types. |

#### [doShowTitles](#doshowtitles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexClips:doShowTitles() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that will set the clip index to "Titles" media types. |

#### [doShowVideo](#doshowvideo)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexClips:doShowVideo() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that will set the clip index to "Video" media types. |

#### [saveLayout](#savelayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexClips:saveLayout() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `table` containing the layout configuration for this class. |
| **Returns**                                          | <ul><li>The layout configuration <code>table</code>.</li></ul> |

