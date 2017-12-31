# [docs](index.md) » cp.apple.finalcutpro.main.Inspector
---

Inspector

## Submodules
 * [cp.apple.finalcutpro.main.Inspector.AudioInspector](cp.apple.finalcutpro.main.Inspector.AudioInspector.md)
 * [cp.apple.finalcutpro.main.Inspector.ColorInspector](cp.apple.finalcutpro.main.Inspector.ColorInspector.md)
 * [cp.apple.finalcutpro.main.Inspector.EffectInspector](cp.apple.finalcutpro.main.Inspector.EffectInspector.md)
 * [cp.apple.finalcutpro.main.Inspector.GeneratorInspector](cp.apple.finalcutpro.main.Inspector.GeneratorInspector.md)
 * [cp.apple.finalcutpro.main.Inspector.InfoInspector](cp.apple.finalcutpro.main.Inspector.InfoInspector.md)
 * [cp.apple.finalcutpro.main.Inspector.ShareInspector](cp.apple.finalcutpro.main.Inspector.ShareInspector.md)
 * [cp.apple.finalcutpro.main.Inspector.TextInspector](cp.apple.finalcutpro.main.Inspector.TextInspector.md)
 * [cp.apple.finalcutpro.main.Inspector.TitleInspector](cp.apple.finalcutpro.main.Inspector.TitleInspector.md)
 * [cp.apple.finalcutpro.main.Inspector.TransitionInspector](cp.apple.finalcutpro.main.Inspector.TransitionInspector.md)
 * [cp.apple.finalcutpro.main.Inspector.VideoInspector](cp.apple.finalcutpro.main.Inspector.VideoInspector.md)

## API Overview
* Constants - Useful values which cannot be changed
 * [INSPECTOR_TABS](#inspector_tabs)
* Functions - API calls offered directly by the extension
 * [isShowing](#isshowing)
 * [matches](#matches)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [audioInspector](#audioinspector)
 * [colorInspector](#colorinspector)
 * [effectInspector](#effectinspector)
 * [generatorInspector](#generatorinspector)
 * [hide](#hide)
 * [infoInspector](#infoinspector)
 * [new](#new)
 * [parent](#parent)
 * [selectedTab](#selectedtab)
 * [selectTab](#selecttab)
 * [shareInspector](#shareinspector)
 * [show](#show)
 * [textInspector](#textinspector)
 * [titleInspector](#titleinspector)
 * [transitionInspector](#transitioninspector)
 * [UI](#ui)
 * [videoInspector](#videoinspector)

## API Documentation

### Constants

#### [INSPECTOR_TABS](#inspector_tabs)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Inspector.INSPECTOR_TABS -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Table of supported Inspector Tabs                                                                                         |

### Functions

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Inspector.isShowing() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns `true` if the Inspector is showing otherwise `false`                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>`true` if showing, otherwise `false`</li></ul>          |

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Inspector.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if an element matches what we think it should be.                                                                                         |
| **Parameters**                                       | <ul><li>element - axuielementObject</li></ul> |
| **Returns**                                          | <ul><li>`true` if matches otherwise `false`</li></ul>          |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Inspector:app() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the app instance representing Final Cut Pro.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>App</li></ul>          |

#### [audioInspector](#audioinspector)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Inspector:audioInspector() -> AudioInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the AudioInspector object.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>AudioInspector</li></ul>          |

#### [colorInspector](#colorinspector)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Inspector:colorInspector() -> ColorInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the ColorInspector object.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>ColorInspector</li></ul>          |

#### [effectInspector](#effectinspector)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Inspector:effectInspector() -> EffectInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the EffectInspector object.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>EffectInspector</li></ul>          |

#### [generatorInspector](#generatorinspector)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Inspector:generatorInspector() -> GeneratorInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the GeneratorInspector object.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>GeneratorInspector</li></ul>          |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Inspector:hide() -> Inspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides the inspector.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The `Inspector` instance.</li></ul>          |

#### [infoInspector](#infoinspector)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Inspector:infoInspector() -> InfoInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the InfoInspector object.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>InfoInspector</li></ul>          |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Inspector:new(parent) -> Inspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a new Inspector.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>App</li></ul>          |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Inspector:parent() -> Parent` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the parent of the Inspector.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>App</li></ul>          |

#### [selectedTab](#selectedtab)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Inspector:selectedTab() -> string or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the name of the selected inspector tab otherwise `nil`.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string of the selected tab, otherwise `nil` if the Inspector is closed or an error occurred.</li></ul>          |
| **Notes**                                            | <ul><li>The tab strings can be:</li><li>  Audio</li><li>  Color</li><li>  Effect</li><li>  Generator</li><li>  Info</li><li>  Share</li><li>  Text</li><li>  Title</li><li>  Transition</li><li>  Video</li></ul>                |

#### [selectTab](#selecttab)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Inspector:selectTab([tab]) -> boolean or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Selects a tab in the inspector.                                                                                         |
| **Parameters**                                       | <ul><li>[tab] - A string from the `cp.apple.finalcutpro.main.Inspector.INSPECTOR_TABS` table</li></ul> |
| **Returns**                                          | <ul><li>A string of the selected tab, otherwise `nil` if an error occurred.</li></ul>          |
| **Notes**                                            | <ul><li>This method will open the Inspector if it's closed, and leave it open.</li><li>Valid strings for `value` are as follows:</li><li>  Audio</li><li>  Color</li><li>  Effect</li><li>  Generator</li><li>  Info</li><li>  Share</li><li>  Text</li><li>  Title</li><li>  Transition</li><li>  Video</li></ul>                |

#### [shareInspector](#shareinspector)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Inspector:shareInspector() -> ShareInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the ShareInspector object.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>ShareInspector</li></ul>          |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Inspector:show([tab]) -> Inspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows the inspector.                                                                                         |
| **Parameters**                                       | <ul><li>[tab] - A string from the `cp.apple.finalcutpro.main.Inspector.INSPECTOR_TABS` table</li></ul> |
| **Returns**                                          | <ul><li>The `Inspector` instance.</li></ul>          |
| **Notes**                                            | <ul><li>Valid strings for `value` are as follows:</li><li>  Audio</li><li>  Color</li><li>  Effect</li><li>  Generator</li><li>  Info</li><li>  Share</li><li>  Text</li><li>  Title</li><li>  Transition</li><li>  Video</li></ul>                |

#### [textInspector](#textinspector)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Inspector:textInspector() -> TextInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the TextInspector object.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>TextInspector</li></ul>          |

#### [titleInspector](#titleinspector)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Inspector:titleInspector() -> TitleInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the TitleInspector object.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>TitleInspector</li></ul>          |

#### [transitionInspector](#transitioninspector)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Inspector:transitionInspector() -> TransitionInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the TransitionInspector object.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>TransitionInspector</li></ul>          |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Inspector:UI() -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Inspectors Accessibility Object                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>An `axuielementObject` on `nil`</li></ul>          |

#### [videoInspector](#videoinspector)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Inspector:videoInspector() -> VideoInspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the VideoInspector object.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>ColorInspector</li></ul>          |

