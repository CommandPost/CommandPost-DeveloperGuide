# [docs](index.md) » cp.apple.finalcutpro.timeline.IndexCaptions
---

Provides access to the 'Captions' section of the [Timeline Index](cp.apple.finalcutpro.timeline.Index.md)

## API Overview
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [activate](#activate)
 * [list](#list)
 * [viewErrors](#viewerrors)
* Methods - API calls which can only be made on an object returned by a constructor
 * [doLayout](#dolayout)
 * [saveLayout](#savelayout)

## API Documentation

### Fields

#### [activate](#activate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexCaptions.activate <cp.ui.RadioButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [RadioButton](cp.ui.RadioButton.md) that activates the 'Captions' section. |

#### [list](#list)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexCaptions.list <cp.ui.Table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The list of captions as a [Table](cp.ui.Table.md). |

#### [viewErrors](#viewerrors)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexCaptions.viewErrors <cp.ui.Button>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [Button](cp.ui.Button.md) that will allow viewing errors in the Captions list. |

### Methods

#### [doLayout](#dolayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexCaptions:doLayout(layout) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that will apply the layout provided, if possible. |
| **Parameters**                                       | <ul><li>layout - the <code>table</code> containing the layout configuration. Usually created via the [#saveLayout] method.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.go.Statement.md">Statement</a>.</li></ul> |

#### [saveLayout](#savelayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.IndexCaptions:saveLayout() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `table` containing the layout configuration for this class. |
| **Returns**                                          | <ul><li>The layout configuration <code>table</code>.</li></ul> |

