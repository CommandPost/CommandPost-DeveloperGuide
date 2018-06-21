# [docs](index.md) » cp.apple.finalcutpro.inspector.Inspector
---

Inspector

## API Overview
* Constants - Useful values which cannot be changed
 * [INSPECTOR_TABS](#inspector_tabs)
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [bottomBarUI](#bottombarui)
 * [isFullHeight](#isfullheight)
 * [isShowing](#isshowing)
 * [labelUI](#labelui)
 * [panelUI](#panelui)
 * [propertiesUI](#propertiesui)
 * [topBarUI](#topbarui)
 * [UI](#ui)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [audio](#audio)
 * [color](#color)
 * [effect](#effect)
 * [generator](#generator)
 * [hide](#hide)
 * [info](#info)
 * [parent](#parent)
 * [selectedTab](#selectedtab)
 * [selectTab](#selecttab)
 * [share](#share)
 * [show](#show)
 * [tabAvailable](#tabavailable)
 * [text](#text)
 * [title](#title)
 * [transition](#transition)
 * [video](#video)

## API Documentation

### Constants

#### [INSPECTOR_TABS](#inspector_tabs)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector.INSPECTOR_TABS -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Table of supported Inspector Tabs                                                                                         |

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if an element matches what we think it should be.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">element - axuielementObject</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`true` if matches otherwise `false`</li></ul>          |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector.new(parent) -> Inspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new Inspector.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">parent - The parent object.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The Inspector object.</li></ul>          |

### Fields

#### [bottomBarUI](#bottombarui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector.bottomBarUI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns the bottom bar `axuielement` for the Inspector.                                                                                         |

#### [isFullHeight](#isfullheight)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector.isFullHeight <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns `true` if the Inspector is full height.                                                                                         |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector.isShowing <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns `true` if the Inspector is showing otherwise `false`                                                                                         |

#### [labelUI](#labelui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector.labelUI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns the `axuielement` for text label at the top of the Inspector.                                                                                         |

#### [panelUI](#panelui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector.panelUI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns the central panel `axuielement` for the Inspector.                                                                                         |

#### [propertiesUI](#propertiesui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector.propertiesUI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns the properties `axuielement` for the Inspector. This contains the rows of property values.                                                                                         |

#### [topBarUI](#topbarui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector.topBarUI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns the "top bar" `axuielement` for the Inspector.                                                                                         |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector.UI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns the `axuielement` for the Inspector.                                                                                         |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:app() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the app instance representing Final Cut Pro.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">App</li></ul>          |

#### [audio](#audio)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:audio() -> AudioInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the AudioInspector object.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">AudioInspector</li></ul>          |

#### [color](#color)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:color() -> ColorInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the ColorInspector object.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">ColorInspector</li></ul>          |

#### [effect](#effect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:effect() -> EffectInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the EffectInspector object.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">EffectInspector</li></ul>          |

#### [generator](#generator)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:generator() -> GeneratorInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the GeneratorInspector object.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">GeneratorInspector</li></ul>          |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:hide() -> Inspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides the inspector.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The `Inspector` instance.</li></ul>          |

#### [info](#info)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:info() -> InfoInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the InfoInspector object.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">InfoInspector</li></ul>          |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:parent() -> Parent` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the parent of the Inspector.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">App</li></ul>          |

#### [selectedTab](#selectedtab)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:selectedTab() -> string or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the name of the selected inspector tab otherwise `nil`.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A string of the selected tab, otherwise `nil` if the Inspector is closed or an error occurred.</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">The tab strings can be:</li><li markdown="1">  Audio</li><li markdown="1">  Color</li><li markdown="1">  Effect</li><li markdown="1">  Generator</li><li markdown="1">  Info</li><li markdown="1">  Share</li><li markdown="1">  Text</li><li markdown="1">  Title</li><li markdown="1">  Transition</li><li markdown="1">  Video</li></ul>                |

#### [selectTab](#selecttab)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:selectTab(tab) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Selects a tab in the inspector.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">tab - A string from the `cp.apple.finalcutpro.inspector.Inspector.INSPECTOR_TABS` table</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A string of the selected tab, otherwise `nil` if an error occurred.</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">This method will open the Inspector if it's closed, and leave it open.</li><li markdown="1">Valid strings for `value` are as follows:</li><li markdown="1">  Audio</li><li markdown="1">  Color</li><li markdown="1">  Effect</li><li markdown="1">  Generator</li><li markdown="1">  Info</li><li markdown="1">  Share</li><li markdown="1">  Text</li><li markdown="1">  Title</li><li markdown="1">  Transition</li><li markdown="1">  Video</li></ul>                |

#### [share](#share)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:share() -> ShareInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the ShareInspector object.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">ShareInspector</li></ul>          |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:show([tab]) -> Inspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows the inspector.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">[tab] - A string from the `cp.apple.finalcutpro.inspector.Inspector.INSPECTOR_TABS` table</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The `Inspector` instance.</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">Valid strings for `value` are as follows:</li><li markdown="1">  Audio</li><li markdown="1">  Color</li><li markdown="1">  Effect</li><li markdown="1">  Generator</li><li markdown="1">  Info</li><li markdown="1">  Share</li><li markdown="1">  Text</li><li markdown="1">  Title</li><li markdown="1">  Transition</li><li markdown="1">  Video</li></ul>                |

#### [tabAvailable](#tabavailable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:tabAvailable(tab) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Checks to see if a tab is currently available in the Inspector.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">tab - A string from the `cp.apple.finalcutpro.inspector.Inspector.INSPECTOR_TABS` table</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`true` if available otherwise `false`.</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">Valid strings for `value` are as follows:</li><li markdown="1">  Audio</li><li markdown="1">  Color</li><li markdown="1">  Effect</li><li markdown="1">  Generator</li><li markdown="1">  Info</li><li markdown="1">  Share</li><li markdown="1">  Text</li><li markdown="1">  Title</li><li markdown="1">  Transition</li><li markdown="1">  Video</li></ul>                |

#### [text](#text)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:text() -> TextInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the TextInspector object.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">TextInspector</li></ul>          |

#### [title](#title)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:title() -> TitleInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the TitleInspector object.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">TitleInspector</li></ul>          |

#### [transition](#transition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:transition() -> TransitionInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the TransitionInspector object.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">TransitionInspector</li></ul>          |

#### [video](#video)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:video() -> VideoInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the VideoInspector object.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">ColorInspector</li></ul>          |

