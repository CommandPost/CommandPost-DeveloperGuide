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
| **Parameters**                                       |  * element - axuielementObject                                       |
| **Returns**                                          |  * `true` if matches otherwise `false`                                                |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector.new(parent) -> Inspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new Inspector.                                                                                         |
| **Parameters**                                       |  * parent - The parent object.                                       |
| **Returns**                                          |  * The Inspector object.                                                |

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
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * App                                                |

#### [audio](#audio)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:audio() -> AudioInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the AudioInspector object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * AudioInspector                                                |

#### [color](#color)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:color() -> ColorInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the ColorInspector object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * ColorInspector                                                |

#### [effect](#effect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:effect() -> EffectInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the EffectInspector object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * EffectInspector                                                |

#### [generator](#generator)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:generator() -> GeneratorInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the GeneratorInspector object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * GeneratorInspector                                                |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:hide() -> Inspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides the inspector.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `Inspector` instance.                                                |

#### [info](#info)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:info() -> InfoInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the InfoInspector object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * InfoInspector                                                |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:parent() -> Parent` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the parent of the Inspector.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * App                                                |

#### [selectedTab](#selectedtab)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:selectedTab() -> string or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the name of the selected inspector tab otherwise `nil`.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A string of the selected tab, otherwise `nil` if the Inspector is closed or an error occurred.                                                |
| **Notes**                                            |  * The tab strings can be:   * Audio   * Color   * Effect   * Generator   * Info   * Share   * Text   * Title   * Transition   * Video                                                      |

#### [selectTab](#selecttab)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:selectTab(tab) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Selects a tab in the inspector.                                                                                         |
| **Parameters**                                       |  * tab - A string from the `cp.apple.finalcutpro.inspector.Inspector.INSPECTOR_TABS` table                                       |
| **Returns**                                          |  * A string of the selected tab, otherwise `nil` if an error occurred.                                                |
| **Notes**                                            |  * This method will open the Inspector if it's closed, and leave it open. * Valid strings for `value` are as follows:   * Audio   * Color   * Effect   * Generator   * Info   * Share   * Text   * Title   * Transition   * Video                                                      |

#### [share](#share)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:share() -> ShareInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the ShareInspector object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * ShareInspector                                                |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:show([tab]) -> Inspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows the inspector.                                                                                         |
| **Parameters**                                       |  * [tab] - A string from the `cp.apple.finalcutpro.inspector.Inspector.INSPECTOR_TABS` table                                       |
| **Returns**                                          |  * The `Inspector` instance.                                                |
| **Notes**                                            |  * Valid strings for `value` are as follows:   * Audio   * Color   * Effect   * Generator   * Info   * Share   * Text   * Title   * Transition   * Video                                                      |

#### [tabAvailable](#tabavailable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:tabAvailable(tab) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Checks to see if a tab is currently available in the Inspector.                                                                                         |
| **Parameters**                                       |  * tab - A string from the `cp.apple.finalcutpro.inspector.Inspector.INSPECTOR_TABS` table                                       |
| **Returns**                                          |  * `true` if available otherwise `false`.                                                |
| **Notes**                                            |  * Valid strings for `value` are as follows:   * Audio   * Color   * Effect   * Generator   * Info   * Share   * Text   * Title   * Transition   * Video                                                      |

#### [text](#text)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:text() -> TextInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the TextInspector object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * TextInspector                                                |

#### [title](#title)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:title() -> TitleInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the TitleInspector object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * TitleInspector                                                |

#### [transition](#transition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:transition() -> TransitionInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the TransitionInspector object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * TransitionInspector                                                |

#### [video](#video)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.Inspector:video() -> VideoInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the VideoInspector object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * ColorInspector                                                |

