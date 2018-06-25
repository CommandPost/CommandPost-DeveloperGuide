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
| **Type**                                             | Constant |
| **Description**                                      | Effects. |

#### [TRANSITIONS](#transitions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser.TRANSITIONS -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Transitions. |

### Variables

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser.isShowing <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Is the Effects Browser showing? |

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks to see if an element matches what we think it should be. |
| **Parameters**                                       | <ul><li>element - An <code>axuielementObject</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if matches otherwise <code>false</code></li></ul> |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser.new(parent, type) -> EffectsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `EffectsBrowser` instance. |
| **Parameters**                                       | <ul><li>parent - The parent object. * type - A string determining whether the Effects Browser is for Effects (<code>cp.apple.finalcutpro.main.EffectsBrowser.EFFECTS</code>) or Transitions (<code>cp.apple.finalcutpro.main.EffectsBrowser.TRANSITIONS</code>).</li></ul> |
| **Returns**                                          | <ul><li>A new <code>EffectsBrowser</code> object.</li></ul> |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:app() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the app instance representing Final Cut Pro. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>App</li></ul> |

#### [applyItem](#applyitem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:applyItem(itemUI) -> EffectsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Applies an item by double clicking on it. |
| **Parameters**                                       | <ul><li>itemUI - The <code>axuielementObject</code> of the item you want to apply.</li></ul> |
| **Returns**                                          | <ul><li>The <code>EffectsBrowser</code> object.</li></ul> |

#### [audioCategoryRowsUI](#audiocategoryrowsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:audioCategoryRowsUI() -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the Audio Category Rows UI. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>axuielementObject</code> object.</li></ul> |

#### [currentItemsUI](#currentitemsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:currentItemsUI() -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the current items UI. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>axuielementObject</code> object.</li></ul> |

#### [getCurrentTitles](#getcurrenttitles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:getCurrentTitles() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the list of titles for all effects/transitions currently visible. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table</li></ul> |

#### [group](#group)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:group() -> PopUpButton` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the group. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A <code>PopUpButton</code> object.</li></ul> |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:hide() -> EffectsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Hide the Effects Browser. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>EffectsBrowser</code> object.</li></ul> |

#### [hideSidebar](#hidesidebar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:hideSidebar() -> EffectsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Hide Sidebar. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>EffectsBrowser</code> object.</li></ul> |

#### [itemIsSelected](#itemisselected)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:itemIsSelected(itemUI) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Checks to see if an item is selected. |
| **Parameters**                                       | <ul><li>itemUI - A <code>axuielementObject</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the item is selected, otherwise <code>false</code>.</li></ul> |

#### [loadLayout](#loadlayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:loadLayout(layout) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Loads a Effects Browser layout. |
| **Parameters**                                       | <ul><li>layout - A table containing the Effects Browser layout settings - created using <code>cp.apple.finalcutpro.main.Browser:saveLayout()</code>.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [mainGroupUI](#maingroupui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:mainGroupUI() -> ScrollArea` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the Effects Browser Contents. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A <code>ScrollArea</code> object.</li></ul> |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:parent() -> parent` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the parent object. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>parent</li></ul> |

#### [saveLayout](#savelayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:saveLayout() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Saves the current Effects Browser layout to a table. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table containing the current Effects Browser Layout.</li></ul> |

#### [search](#search)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:search() -> PopUpButton` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the Search Popup Button object. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A <code>PopUpButton</code> object.</li></ul> |

#### [selectedItemsUI](#selecteditemsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:selectedItemsUI() -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the selected items UI. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>axuielementObject</code> object.</li></ul> |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:show() -> EffectsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Show the Effects Browser. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>EffectsBrowser</code> object.</li></ul> |

#### [showAllAudioEffects](#showallaudioeffects)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:showAllAudioEffects() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Show All Audio Effects. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful otherwise <code>false</code>.</li></ul> |

#### [showAllEffects](#showalleffects)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:showAllEffects() -> EffectsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Show All Effects. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>EffectsBrowser</code> object.</li></ul> |

#### [showAllTransitions](#showalltransitions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:showAllTransitions() -> EffectsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Show All Transitions. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>EffectsBrowser</code> object.</li></ul> |

#### [showAllVideoEffects](#showallvideoeffects)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:showAllVideoEffects() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Show All Video Effects. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful otherwise <code>false</code>.</li></ul> |

#### [showAudioCategory](#showaudiocategory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:showAudioCategory(name) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Ensures the sidebar is showing and that the selected 'Audio' category is selected, if available. |
| **Parameters**                                       | <ul><li><code>name</code>        - The category name, in the current language.</li></ul> |
| **Returns**                                          | <ul><li>The browser.</li></ul> |

#### [showInstalledEffects](#showinstalledeffects)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:showInstalledEffects() -> EffectsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Show Installed Effects. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>EffectsBrowser</code> object.</li></ul> |

#### [showInstalledTransitions](#showinstalledtransitions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:showInstalledTransitions() -> EffectsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Show Installed Transitions. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>EffectsBrowser</code> object.</li></ul> |

#### [showSidebar](#showsidebar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:showSidebar() -> EffectsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Show Sidebar. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>EffectsBrowser</code> object.</li></ul> |

#### [showTransitionsCategory](#showtransitionscategory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:showTransitionsCategory(name) -> EffectsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Ensures the sidebar is showing and that the selected 'Transitions' category is selected, if available. |
| **Parameters**                                       | <ul><li>name - The category name, in the current language.</li></ul> |
| **Returns**                                          | <ul><li>The <code>EffectsBrowser</code> object.</li></ul> |

#### [showVideoCategory](#showvideocategory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:showVideoCategory(name) -> EffectsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Ensures the sidebar is showing and that the selected 'Video' category is selected, if available. |
| **Parameters**                                       | <ul><li>name - The category name, in the current language.</li></ul> |
| **Returns**                                          | <ul><li>The <code>EffectsBrowser</code> object.</li></ul> |

#### [sidebar](#sidebar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:sidebar() -> Table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the sidebar object. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A <code>Table</code> object.</li></ul> |

#### [sidebarToggle](#sidebartoggle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:sidebarToggle() -> CheckBox` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the Sidebar Toggle. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A <code>CheckBox</code> object.</li></ul> |

#### [toggleButton](#togglebutton)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:toggleButton() -> RadioButton` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the Effects Browser Toggle Button. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A <code>RadioButton</code> object.</li></ul> |

#### [toggleSidebar](#togglesidebar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:toggleSidebar() -> EffectsBrowser` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Toggle Sidebar. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>EffectsBrowser</code> object.</li></ul> |

#### [type](#type)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:type() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Type of Effects Browser. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>App</li></ul> |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:UI() -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The Effects Browser UI. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>axuielementObject</li></ul> |

#### [videoCategoryRowsUI](#videocategoryrowsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.EffectsBrowser:videoCategoryRowsUI() -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the Video Category Rows UI. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>axuielementObject</code> object.</li></ul> |

