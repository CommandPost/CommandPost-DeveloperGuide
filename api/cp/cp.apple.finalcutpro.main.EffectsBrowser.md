# [docs](index.md) » cp.apple.finalcutpro.main.EffectsBrowser
---

Effects Browser Module.

## API Overview
* Constants - Useful values which cannot be changed
 * [EFFECTS](#effects)
 * [TRANSITIONS](#transitions)
* Variables - Configurable values
 * [isShowing](#isshowing)
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [applyItem](#applyitem)
 * [audioCategoryRowsUI](#audiocategoryrowsui)
 * [currentItemsUI](#currentitemsui)
 * [getCurrentTitles](#getcurrenttitles)
 * [group](#group)
 * [hide](#hide)
 * [hideSidebar](#hidesidebar)
 * [itemIsSelected](#itemisselected)
 * [loadLayout](#loadlayout)
 * [mainGroupUI](#maingroupui)
 * [parent](#parent)
 * [saveLayout](#savelayout)
 * [search](#search)
 * [selectedItemsUI](#selecteditemsui)
 * [show](#show)
 * [showAllAudioEffects](#showallaudioeffects)
 * [showAllEffects](#showalleffects)
 * [showAllTransitions](#showalltransitions)
 * [showAllVideoEffects](#showallvideoeffects)
 * [showAudioCategory](#showaudiocategory)
 * [showInstalledEffects](#showinstalledeffects)
 * [showInstalledTransitions](#showinstalledtransitions)
 * [showSidebar](#showsidebar)
 * [showTransitionsCategory](#showtransitionscategory)
 * [showVideoCategory](#showvideocategory)
 * [sidebar](#sidebar)
 * [sidebarToggle](#sidebartoggle)
 * [toggleButton](#togglebutton)
 * [toggleSidebar](#togglesidebar)
 * [type](#type)
 * [UI](#ui)
 * [videoCategoryRowsUI](#videocategoryrowsui)

## API Documentation

### Constants

#### [EFFECTS](#effects)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser.EFFECTS -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Effects.                                                                                         |

#### [TRANSITIONS](#transitions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser.TRANSITIONS -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Transitions.                                                                                         |

### Variables

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser.isShowing <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Is the Effects Browser showing?                                                                                         |

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if an element matches what we think it should be.                                                                                         |
| **Parameters**                                       |  * element - An `axuielementObject` to check.                                       |
| **Returns**                                          |  * `true` if matches otherwise `false`                                                |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser.new(parent, type) -> EffectsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `EffectsBrowser` instance.                                                                                         |
| **Parameters**                                       |  * parent - The parent object. * type - A string determining whether the Effects Browser is for Effects (`cp.apple.finalcutpro.main.EffectsBrowser.EFFECTS`) or Transitions (`cp.apple.finalcutpro.main.EffectsBrowser.TRANSITIONS`).                                       |
| **Returns**                                          |  * A new `EffectsBrowser` object.                                                |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:app() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the app instance representing Final Cut Pro.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * App                                                |

#### [applyItem](#applyitem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:applyItem(itemUI) -> EffectsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Applies an item by double clicking on it.                                                                                         |
| **Parameters**                                       |  * itemUI - The `axuielementObject` of the item you want to apply.                                       |
| **Returns**                                          |  * The `EffectsBrowser` object.                                                |

#### [audioCategoryRowsUI](#audiocategoryrowsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:audioCategoryRowsUI() -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the Audio Category Rows UI.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `axuielementObject` object.                                                |

#### [currentItemsUI](#currentitemsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:currentItemsUI() -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the current items UI.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `axuielementObject` object.                                                |

#### [getCurrentTitles](#getcurrenttitles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:getCurrentTitles() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the list of titles for all effects/transitions currently visible.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A table                                                |

#### [group](#group)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:group() -> PopUpButton` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the group.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A `PopUpButton` object.                                                |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:hide() -> EffectsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hide the Effects Browser.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `EffectsBrowser` object.                                                |

#### [hideSidebar](#hidesidebar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:hideSidebar() -> EffectsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hide Sidebar.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `EffectsBrowser` object.                                                |

#### [itemIsSelected](#itemisselected)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:itemIsSelected(itemUI) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Checks to see if an item is selected.                                                                                         |
| **Parameters**                                       |  * itemUI - A `axuielementObject` to check.                                       |
| **Returns**                                          |  * `true` if the item is selected, otherwise `false`.                                                |

#### [loadLayout](#loadlayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:loadLayout(layout) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Loads a Effects Browser layout.                                                                                         |
| **Parameters**                                       |  * layout - A table containing the Effects Browser layout settings - created using `cp.apple.finalcutpro.main.Browser:saveLayout()`.                                       |
| **Returns**                                          |  * None                                                |

#### [mainGroupUI](#maingroupui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:mainGroupUI() -> ScrollArea` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the Effects Browser Contents.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A `ScrollArea` object.                                                |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:parent() -> parent` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the parent object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * parent                                                |

#### [saveLayout](#savelayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:saveLayout() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Saves the current Effects Browser layout to a table.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A table containing the current Effects Browser Layout.                                                |

#### [search](#search)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:search() -> PopUpButton` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the Search Popup Button object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A `PopUpButton` object.                                                |

#### [selectedItemsUI](#selecteditemsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:selectedItemsUI() -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the selected items UI.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `axuielementObject` object.                                                |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:show() -> EffectsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Show the Effects Browser.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `EffectsBrowser` object.                                                |

#### [showAllAudioEffects](#showallaudioeffects)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:showAllAudioEffects() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Show All Audio Effects.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `true` if successful otherwise `false`.                                                |

#### [showAllEffects](#showalleffects)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:showAllEffects() -> EffectsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Show All Effects.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `EffectsBrowser` object.                                                |

#### [showAllTransitions](#showalltransitions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:showAllTransitions() -> EffectsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Show All Transitions.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `EffectsBrowser` object.                                                |

#### [showAllVideoEffects](#showallvideoeffects)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:showAllVideoEffects() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Show All Video Effects.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `true` if successful otherwise `false`.                                                |

#### [showAudioCategory](#showaudiocategory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:showAudioCategory(name) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Ensures the sidebar is showing and that the selected 'Audio' category is selected, if available.                                                                                         |
| **Parameters**                                       | * `name`		- The category name, in the current language.                                       |
| **Returns**                                          | * The browser.                                                |

#### [showInstalledEffects](#showinstalledeffects)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:showInstalledEffects() -> EffectsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Show Installed Effects.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `EffectsBrowser` object.                                                |

#### [showInstalledTransitions](#showinstalledtransitions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:showInstalledTransitions() -> EffectsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Show Installed Transitions.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `EffectsBrowser` object.                                                |

#### [showSidebar](#showsidebar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:showSidebar() -> EffectsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Show Sidebar.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `EffectsBrowser` object.                                                |

#### [showTransitionsCategory](#showtransitionscategory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:showTransitionsCategory(name) -> EffectsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Ensures the sidebar is showing and that the selected 'Transitions' category is selected, if available.                                                                                         |
| **Parameters**                                       |  * name - The category name, in the current language.                                       |
| **Returns**                                          |  * The `EffectsBrowser` object.                                                |

#### [showVideoCategory](#showvideocategory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:showVideoCategory(name) -> EffectsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Ensures the sidebar is showing and that the selected 'Video' category is selected, if available.                                                                                         |
| **Parameters**                                       |  * name - The category name, in the current language.                                       |
| **Returns**                                          |  * The `EffectsBrowser` object.                                                |

#### [sidebar](#sidebar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:sidebar() -> Table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the sidebar object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A `Table` object.                                                |

#### [sidebarToggle](#sidebartoggle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:sidebarToggle() -> CheckBox` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the Sidebar Toggle.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A `CheckBox` object.                                                |

#### [toggleButton](#togglebutton)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:toggleButton() -> RadioButton` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Effects Browser Toggle Button.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A `RadioButton` object.                                                |

#### [toggleSidebar](#togglesidebar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:toggleSidebar() -> EffectsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Toggle Sidebar.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `EffectsBrowser` object.                                                |

#### [type](#type)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:type() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Type of Effects Browser.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * App                                                |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:UI() -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | The Effects Browser UI.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * axuielementObject                                                |

#### [videoCategoryRowsUI](#videocategoryrowsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:videoCategoryRowsUI() -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the Video Category Rows UI.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `axuielementObject` object.                                                |

