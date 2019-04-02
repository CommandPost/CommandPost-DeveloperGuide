# [docs](index.md) » cp.apple.finalcutpro.inspector.Inspector
---

Inspector

## API Overview
* Constants - Useful values which cannot be changed
 * [INSPECTOR_TABS](#inspector_tabs)
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [Inspector](#inspector)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [audio](#audio)
 * [bottomBarUI](#bottombarui)
 * [color](#color)
 * [generator](#generator)
 * [info](#info)
 * [isFullHeight](#isfullheight)
 * [isShowing](#isshowing)
 * [labelUI](#labelui)
 * [panelUI](#panelui)
 * [propertiesUI](#propertiesui)
 * [share](#share)
 * [text](#text)
 * [title](#title)
 * [topBarUI](#topbarui)
 * [transition](#transition)
 * [video](#video)
* Methods - API calls which can only be made on an object returned by a constructor
 * [doFindTabButton](#dofindtabbutton)
 * [doHide](#dohide)
 * [doSelectTab](#doselecttab)
 * [doShow](#doshow)
 * [hide](#hide)
 * [selectedTab](#selectedtab)
 * [selectTab](#selecttab)
 * [show](#show)
 * [tabAvailable](#tabavailable)

## API Documentation

### Constants

#### [INSPECTOR_TABS](#inspector_tabs)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector.INSPECTOR_TABS -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Table of supported Inspector Tabs |

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks to see if an element matches what we think it should be. |
| **Parameters**                                       | <ul><li>element - axuielementObject</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if matches otherwise <code>false</code></li></ul> |

### Constructors

#### [Inspector](#inspector)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector(parent) -> Inspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new Inspector. |
| **Parameters**                                       | <ul><li>parent - The parent object.</li></ul> |
| **Returns**                                          | <ul><li>The Inspector object.</li></ul> |

### Fields

#### [audio](#audio)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector.audio <cp.apple.finalcutpro.inspector.AudioInspector>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [AudioInspector](cp.apple.finalcutpro.inspector.AudioInspector.md). |

#### [bottomBarUI](#bottombarui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector.bottomBarUI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns the bottom bar `axuielement` for the Inspector. |

#### [color](#color)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector.color <cp.apple.finalcutpro.inspector.ColorInspector>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [ColorInspector](cp.apple.finalcutpro.inspector.ColorInspector.md). |

#### [generator](#generator)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector.generator <cp.apple.finalcutpro.inspector.GeneratorInspector>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [GeneratorInspector](package.GeneratorInspector.md) |

#### [info](#info)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector.info <cp.apple.finalcutpro.inspector.InfoInspector>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The  [InfoInspector](cp.apple.finalcutpro.inspector.InfoInspector.md). |

#### [isFullHeight](#isfullheight)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector.isFullHeight <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns `true` if the Inspector is full height. |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector.isShowing <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns `true` if the Inspector is showing otherwise `false` |

#### [labelUI](#labelui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector.labelUI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns the `axuielement` for text label at the top of the Inspector. |

#### [panelUI](#panelui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector.panelUI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns the central panel `axuielement` for the Inspector. |

#### [propertiesUI](#propertiesui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector.propertiesUI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns the properties `axuielement` for the Inspector. This contains the rows of property values. |

#### [share](#share)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector.share <cp.apple.finalcutpro.inspector.ShareInspector>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [ShareInspector](cp.apple.finalcutpro.inspector.ShareInspector.md). |

#### [text](#text)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector.text <cp.apple.finalcutpro.inspector.TextInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [TextzInspector](cp.apple.finalcutpro.inspector.TextzInspector.md). |

#### [title](#title)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector.title <cp.apple.finalcutpro.inspector.TitleInspector>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [TitleInspector](cp.apple.finalcutpro.inspector.TitleInspector.md). |

#### [topBarUI](#topbarui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector.topBarUI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns the "top bar" `axuielement` for the Inspector. |

#### [transition](#transition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector.transition <cp.apple.finalcutpro.inspector.TransitionInspector>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [TransitionInspector](cp.apple.finalcutpro.inspector.TransitionInspector.md). |

#### [video](#video)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector.video <cp.apple.finalcutpro.inspector.VideoInspector>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [VideoInspector](cp.apple.finalcutpro.inspector.VideoInspector.md). |

### Methods

#### [doFindTabButton](#dofindtabbutton)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:doFindTabButton(type) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Finds the named Inspector tab button, or sends an error if the type is unsupported. |
| **Parameters**                                       | <ul><li>type - the type of the button to return. (e.g. "Video")</li></ul> |
| **Returns**                                          | <ul><li>A <a href="cp.rx.go.Statement.md">Statement</a> to execute.</li></ul> |
| **Notes**                                            | <ul><li>Valid strings for <code>type</code> are as follows:</li><li>Audio</li><li>Color</li><li>Effect</li><li>Generator</li><li>Info</li><li>Share</li><li>Text</li><li>Title</li><li>Transition</li><li>Video</li><li>Not all button types are available in all contexts.</li></ul> |

#### [doHide](#dohide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:doHide() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that attempts to hide the `Inspector`. |
| **Returns**                                          | <ul><li>The <code>Statement</code>, resolving to <code>true</code> if the Inspector was hidden successfully, or an error if not.</li></ul> |

#### [doSelectTab](#doselecttab)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:doSelectTab(title) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A Statement that selects the specified tab title. |
| **Parameters**                                       | <ul><li>title     - The title of the tab to select.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.go.Statement.md">Statement</a></li></ul> |

#### [doShow](#doshow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:doShow() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that attempts to show the `Inspector`. |
| **Returns**                                          | <ul><li>The <code>Statement</code>, resolving to <code>true</code> if the Inspector was shown successfully, or an error if not.</li></ul> |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:hide() -> Inspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Hides the inspector. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Inspector</code> instance.</li></ul> |

#### [selectedTab](#selectedtab)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:selectedTab() -> string or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the name of the selected inspector tab otherwise `nil`. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string of the selected tab, otherwise <code>nil</code> if the Inspector is closed or an error occurred.</li></ul> |
| **Notes**                                            | <ul><li>The tab strings can be:</li><li>Audio</li><li>Color</li><li>Effect</li><li>Generator</li><li>Info</li><li>Share</li><li>Text</li><li>Title</li><li>Transition</li><li>Video</li></ul> |

#### [selectTab](#selecttab)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:selectTab(tab) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Selects a tab in the inspector. |
| **Parameters**                                       | <ul><li>tab - A string from the <code>cp.apple.finalcutpro.inspector.Inspector.INSPECTOR_TABS</code> table</li></ul> |
| **Returns**                                          | <ul><li>A string of the selected tab, otherwise <code>nil</code> if an error occurred.</li></ul> |
| **Notes**                                            | <ul><li>This method will open the Inspector if it's closed, and leave it open.</li><li>Valid strings for <code>value</code> are as follows:</li><li>Audio</li><li>Color</li><li>Effect</li><li>Generator</li><li>Info</li><li>Share</li><li>Text</li><li>Title</li><li>Transition</li><li>Video</li></ul> |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:show([tab]) -> Inspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Shows the inspector. |
| **Parameters**                                       | <ul><li>[tab] - A string from the <code>cp.apple.finalcutpro.inspector.Inspector.INSPECTOR_TABS</code> table</li></ul> |
| **Returns**                                          | <ul><li>The <code>Inspector</code> instance.</li></ul> |
| **Notes**                                            | <ul><li>Valid strings for <code>value</code> are as follows:</li><li>Audio</li><li>Color</li><li>Effect</li><li>Generator</li><li>Info</li><li>Share</li><li>Text</li><li>Title</li><li>Transition</li><li>Video</li></ul> |

#### [tabAvailable](#tabavailable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:tabAvailable(tab) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Checks to see if a tab is currently available in the Inspector. |
| **Parameters**                                       | <ul><li>tab - A string from the <code>cp.apple.finalcutpro.inspector.Inspector.INSPECTOR_TABS</code> table</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if available otherwise <code>false</code>.</li></ul> |
| **Notes**                                            | <ul><li>Valid strings for <code>value</code> are as follows:</li><li>Audio</li><li>Color</li><li>Effect</li><li>Generator</li><li>Info</li><li>Share</li><li>Text</li><li>Title</li><li>Transition</li><li>Video</li></ul> |

