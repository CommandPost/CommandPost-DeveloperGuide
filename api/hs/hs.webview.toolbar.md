# [docs](index.md) » hs.webview.toolbar
---

Create and manipulate toolbars which can be attached to the Hammerspoon console or hs.webview objects.

Toolbars are attached to titled windows and provide buttons which can be used to perform various actions within the application. Hammerspoon can use this module to add toolbars to the console or `hs.webview` objects which have a title bar (see `hs.webview.windowMasks` and `hs.webview:windowStyle`). Toolbars are identified by a unique identifier which is used by OS X to identify information which can be auto saved in the application's user defaults to reflect changes the user has made to the toolbar button order or active button list (this requires setting [hs.webview.toolbar:autosaves](#autosaves) and [hs.webview.toolbar:canCustomize](#canCustomize) both to true).

Multiple copies of the same toolbar can be made with the [hs.webview.toolbar:copy](#copy) method so that multiple webview windows use the same toolbar, for example. If the user customizes a copied toolbar, changes to the active buttons or their order will be reflected in all copies of the toolbar.

Example:
~~~lua
t = require("hs.webview.toolbar")
a = t.new("myConsole", {
        { id = "select1", selectable = true, image = hs.image.imageFromName("NSStatusAvailable") },
        { id = "NSToolbarSpaceItem" },
        { id = "select2", selectable = true, image = hs.image.imageFromName("NSStatusUnavailable") },
        { id = "notShown", default = false, image = hs.image.imageFromName("NSBonjour") },
        { id = "NSToolbarFlexibleSpaceItem" },
        { id = "navGroup", label = "Navigation", groupMembers = { "navLeft", "navRight" }},
        { id = "navLeft", image = hs.image.imageFromName("NSGoLeftTemplate"), allowedAlone = false },
        { id = "navRight", image = hs.image.imageFromName("NSGoRightTemplate"), allowedAlone = false },
        { id = "NSToolbarFlexibleSpaceItem" },
        { id = "cust", label = "customize", fn = function(t, w, i) t:customizePanel() end, image = hs.image.imageFromName("NSAdvanced") }
    }):canCustomize(true)
      :autosaves(true)
      :selectedItem("select2")
      :setCallback(function(...)
                        print("a", inspect(table.pack(...)))
                   end)

t.attachToolbar(a)
~~~

Notes:
 * This module is supported in OS X versions prior to 10.10 (for the Hammerspoon console only), even though its parent `hs.webview` is not. To load this module directly, use `require("hs.webview.toolbar")` instead of relying on module auto-loading.
 * Toolbar items are rendered in the order they are supplied, although if the toolbar is marked as customizable, the user may have changed the order.

## API Overview
* Constants - Useful values which cannot be changed
 * [itemPriorities](#itempriorities)
 * [systemToolbarItems](#systemtoolbaritems)
* Functions - API calls offered directly by the extension
 * [attachToolbar](#attachtoolbar)
 * [inTitleBar](#intitlebar)
 * [uniqueName](#uniquename)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [addItems](#additems)
 * [allowedItems](#alloweditems)
 * [autosaves](#autosaves)
 * [canCustomize](#cancustomize)
 * [copy](#copy)
 * [customizePanel](#customizepanel)
 * [delete](#delete)
 * [deleteItem](#deleteitem)
 * [displayMode](#displaymode)
 * [identifier](#identifier)
 * [insertItem](#insertitem)
 * [isAttached](#isattached)
 * [isCustomizing](#iscustomizing)
 * [itemDetails](#itemdetails)
 * [items](#items)
 * [modifyItem](#modifyitem)
 * [notifyOnChange](#notifyonchange)
 * [removeItem](#removeitem)
 * [savedSettings](#savedsettings)
 * [selectedItem](#selecteditem)
 * [selectSearchField](#selectsearchfield)
 * [separator](#separator)
 * [setCallback](#setcallback)
 * [sizeMode](#sizemode)
 * [visible](#visible)
 * [visibleItems](#visibleitems)

## API Documentation

### Constants

#### [itemPriorities](#itempriorities)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.toolbar.itemPriorities` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | A table containing some pre-defined toolbar item priority values for use when determining item order in the toolbar. |

#### [systemToolbarItems](#systemtoolbaritems)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.toolbar.systemToolbarItems` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | An array containing string identifiers for supported system defined toolbar items. |

### Functions

#### [attachToolbar](#attachtoolbar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.toolbar.attachToolbar([obj1], [obj2]) -> obj1` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Get or attach/detach a toolbar to the webview, chooser, or console. |
| **Parameters**                                       | <ul><li>obj1 - An optional toolbarObject</li><li>obj2 - An optional toolbarObject</li><li>if no arguments are present, this function returns the current toolbarObject for the Hammerspoon console, or nil if one is not attached.</li><li>if one argument is provided and it is a toolbarObject or nil, this function will attach or detach a toolbarObject to/from the Hammerspoon console.</li><li>if one argument is provided and it is an hs.webview or hs.chooser object, this function will return the current toolbarObject for the object, or nil if one is not attached.</li><li>if two arguments are provided and the first is an hs.webview or hs.chooser object and the second is a toolbarObject or nil, this function will attach or detach a toolbarObject to/from the object.</li></ul> |
| **Returns**                                          | <ul><li>if the function is used to attach/detach a toolbar, then the first object provided (the target) will be returned ; if this function is used to get the current toolbar object for a webview, chooser, or console, then the toolbarObject or nil will be returned.</li></ul> |
| **Notes**                                            | <ul><li>This function is not expected to be used directly (though it can be) -- it is added to the <code>hs.webview</code> and <code>hs.chooser</code> object metatables so that it may be invoked as <code>hs.webview:attachedToolbar([toolbarObject | nil])</code>/<code>hs.chooser:attachedToolbar([toolbarObject | nil])</code> and to the <code>hs.console</code> module so that it may be invoked as <code>hs.console.toolbar([toolbarObject | nil])</code>.</li></ul> |

#### [inTitleBar](#intitlebar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.toolbar:inTitleBar([state]) -> toolbarObject | boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Get or set whether or not the toolbar appears in the containing window's titlebar, similar to Safari. |
| **Parameters**                                       | <ul><li><code>state</code> - an optional boolean specifying whether or not the toolbar should appear in the window's titlebar.</li></ul> |
| **Returns**                                          | <ul><li>if a parameter is specified, returns the toolbar object, otherwise the current value.</li></ul> |
| **Notes**                                            | <ul><li>When this value is true, the toolbar, when visible, will appear in the window's title bar similar to the toolbar as seen in applications like Safari.  In this state, the toolbar will set the display of the toolbar items to icons without labels, ignoring changes made with <a href="#displayMode">hs.webview.toolbar:displayMode</a>.</li></ul> |

#### [uniqueName](#uniquename)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.toolbar.uniqueName(toolbarName) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks to see is a toolbar name is already in use |
| **Parameters**                                       | <ul><li>toolbarName  - a string specifying the name of a toolbar</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the name is unique otherwise <code>false</code></li></ul> |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.toolbar.new(toolbarName, [toolbarTable]) -> toolbarObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new toolbar for a webview, chooser, or the console. |
| **Parameters**                                       | <ul><li>toolbarName  - a string specifying the name for this toolbar</li><li>toolbarTable - an optional table describing possible items for the toolbar</li></ul> |
| **Returns**                                          | <ul><li>a toolbarObject</li></ul> |
| **Notes**                                            | <ul><li>Toolbar names must be unique, but a toolbar may be copied with <a href="#copy">hs.webview.toolbar:copy</a> if you wish to attach it to multiple windows (webview, chooser, or console).</li><li>See <a href="#addItems">hs.webview.toolbar:addItems</a> for a description of the format for <code>toolbarTable</code></li></ul> |

### Methods

#### [addItems](#additems)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.toolbar:addItems(toolbarTable) -> toolbarObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Add one or more toolbar items to the toolbar |
| **Parameters**                                       | <ul><li><code>toolbarTable</code> - a table describing a single toolbar item, or an array of tables, each describing a separate toolbar item, to be added to the toolbar.</li></ul> |
| **Returns**                                          | <ul><li>the toolbarObject</li></ul> |
| **Notes**                                            | <ul><li>Each toolbar item is defined as a table of key-value pairs.  The following list describes the valid keys used when describing a toolbar item for this method, the constructor <a href="#new">hs.webview.toolbar.new</a>, and the <a href="#modifyItem">hs.webview.toolbar:modifyItem</a> method.  Note that the <code>id</code> field is <strong>required</strong> for all three uses.</li><li><code>id</code>           - A unique string identifier required for each toolbar item and group.  This key cannot be changed after an item has been created.</li><li><code>allowedAlone</code> - a boolean value, default true, specifying whether or not the toolbar item can be added to the toolbar, programmatically or through the customization panel, (true) or whether it can only be added as a member of a group (false).</li><li><code>default</code>      - a boolean value, default matching the value of <code>allowedAlone</code> for this item, indicating whether or not this toolbar item or group should be displayed in the toolbar by default, unless overridden by user customization or a saved configuration (when such options are enabled).</li><li><code>enable</code>       - a boolean value, default true, indicating whether or not the toolbar item is active (and can be clicked on) or inactive and greyed out.  This field is ignored when applied to a toolbar group; apply it to the group members instead.</li><li><code>fn</code>           - a callback function, or false to remove, specific to the toolbar item. This property is ignored if assigned to the button group. This function will override the toolbar callback defined with <a href="#setCallback">hs.webview.toolbar:setCallback</a> for this specific item. The function should expect three (four, if the item is a <code>searchfield</code>) arguments and return none.  See <a href="#setCallback">hs.webview.toolbar:setCallback</a> for information about the callback's arguments.</li><li><code>groupMembers</code> - an array (table) of strings specifying the toolbar item ids that are members of this toolbar item group.  If set to false, this field is removed and the item is reset back to being a regular toolbar item.  Note that you cannot change a currently visible toolbar item to or from being a group; it must first be removed from active toolbar with <a href="#removeItem">hs.webview.toolbar:removeItem</a>.</li><li><code>image</code>        - an <code>hs.image</code> object, or false to remove, specifying the image to use as the toolbar item's icon when icon's are displayed in the toolbar or customization panel. This key is ignored for a toolbar item group, but not for it's individual members.</li><li><code>label</code>        - a string label, or false to remove, for the toolbar item or group when text is displayed in the toolbar or in the customization panel. For a toolbar item, the default is the <code>id</code> string; for a group, the default is <code>false</code>. If a group has a label assigned to it, the group label will be displayed for the group of items it contains. If a group does not have a label, the individual items which make up the group will each display their individual labels.</li><li><code>priority</code>     - an integer value used to determine toolbar item order and which items are displayed or put into the overflow menu when the number of items in the toolbar exceed the width of the window in which the toolbar is attached. Some example values are provided in the <a href="#itemPriorities">hs.webview.toolbar.itemPriorities</a> table. If a toolbar item is in a group, it's priority is ignored and the item group is ordered by the item group's priority.</li><li><code>searchfield</code>  - a boolean (default false) specifying whether or not this toolbar item is a search field. If true, the following additional keys are allowed:<ul><li><code>searchHistory</code>                - an array (table) of strings, specifying previous searches to automatically include in the search field menu, if <code>searchPredefinedMenuTitle</code> is not false</li><li><code>searchHistoryAutosaveName</code>    - a string specifying the key name to save search history with in the application deafults (accessible through <code>hs.settings</code>). If this value is set, search history will be maintained through restarts of Hammerspoon.</li><li><code>searchHistoryLimit</code>           - the maximum number of items to store in the search field history.</li><li><code>searchPredefinedMenuTitle</code>    - a string or boolean specifying how a predefined list of search field "response" should be included in the search field menu. If this item is <code>true</code>, this list of items specified for <code>searchPredefinedSearches</code> will be displayed in a submenu with the title "Predefined Searches". If this item is a string, the list of items will be displayed in a submenu with the title specified by this string value. If this item is <code>false</code>, then the search field menu will only contain the items specified in <code>searchPredefinedSearches</code> and no search history will be included in the menu.</li><li><code>searchPredefinedSearches</code>     - an array (table) of strings specifying the items to be listed in the predefined search submenu. If set to false, any existing menu will be removed and the search field menu will be reset to the default.</li><li><code>searchReleaseFocusOnCallback</code> - a boolean, default false, specifying whether or not focus leaves the search field text box when the callback is invoked. Setting this to true can be useful if you want subsequent keypresses to be caught by the webview after reacting to the value entered into the search field by the user.</li><li><code>searchText</code>                   - a string specifying the text to display in the search field.</li><li><code>searchWidth</code>                  - the width of the search field text entry box.</li></ul></li><li><code>selectable</code>   - a boolean value, default false, indicating whether or not this toolbar item is selectable (i.e. highlights, like a selected tab) when clicked on. Only one selectable toolbar item can be highlighted at a time, and you can get or set/reset the selected item with <a href="#selectedItem">hs.webview.toolbar:selectedItem</a>.</li><li><code>tag</code>          - an integer value which can be used for own purposes; has no affect on the visual aspect of the item or its behavior.</li><li><code>tooltip</code>      - a string label, or false to remove, which is displayed as a tool tip when the user hovers the mouse over the button or button group. If a button is in a group, it's tooltip is ignored in favor of the group tooltip.</li></ul> |

#### [allowedItems](#alloweditems)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.toolbar:allowedItems() -> array` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns an array of all toolbar item identifiers defined for this toolbar. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a table as an array of all toolbar item identifiers defined for this toolbar.  See also <a href="#items">hs.webview.toolbar:items</a> and <a href="#visibleItems">hs.webview.toolbar:visibleItems</a>.</li></ul> |

#### [autosaves](#autosaves)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.toolbar:autosaves([bool]) -> toolbarObject | bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Get or set whether or not the toolbar autosaves changes made to the toolbar. |
| **Parameters**                                       | <ul><li>an optional boolean value indicating whether or not changes made to the visible toolbar items or their order is automatically saved.</li></ul> |
| **Returns**                                          | <ul><li>if an argument is provided, returns the toolbar object; otherwise returns the current value</li></ul> |
| **Notes**                                            | <ul><li>If the toolbar is set to autosave, then a user-defaults entry is created in org.hammerspoon.Hammerspoon domain with the key "NSToolbar Configuration XXX" where XXX is the toolbar identifier specified when the toolbar was created.</li><li>The information saved for the toolbar consists of the following:</li><li>the default item identifiers that are displayed when the toolbar is first created or when the user drags the default set from the customization panel.</li><li>the current display mode (icon, text, both)</li><li>the current size mode (regular, small)</li><li>whether or not the toolbar is currently visible</li><li>the currently shown identifiers and their order</li><li>Note that the labels, icons, callback functions, etc. are not saved -- these are determined at toolbar creation time, by the <a href="#addItems">hs.webview.toolbar:addItems</a>, or by the <a href="#modifyItem">hs.webview.toolbar:modifyItem</a> method and can differ between invocations of toolbars with the same identifier and button identifiers.</li></ul> |

#### [canCustomize](#cancustomize)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.toolbar:canCustomize([bool]) -> toolbarObject | bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Get or set whether or not the user is allowed to customize the toolbar with the Customization Panel. |
| **Parameters**                                       | <ul><li>an optional boolean value indicating whether or not the user is allowed to customize the toolbar.</li></ul> |
| **Returns**                                          | <ul><li>if an argument is provided, returns the toolbar object; otherwise returns the current value</li></ul> |
| **Notes**                                            | <ul><li>the customization panel can be pulled up by right-clicking on the toolbar or by invoking <a href="#customizePanel">hs.webview.toolbar:customizePanel</a>.</li></ul> |

#### [copy](#copy)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.toolbar:copy() -> toolbarObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a copy of the toolbar object. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a copy of the toolbar which can be attached to another window (webview, chooser, or console).</li></ul> |

#### [customizePanel](#customizepanel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.toolbar:customizePanel() -> toolbarObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Opens the toolbar customization panel. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the toolbar object</li></ul> |

#### [delete](#delete)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.toolbar:delete() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Deletes the toolbar, removing it from its window if it is currently attached. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [deleteItem](#deleteitem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.toolbar:deleteItem(identifier) -> toolbarObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Deletes the toolbar item specified completely from the toolbar, removing it first, if the toolbar item is currently active. |
| **Parameters**                                       | <ul><li><code>identifier</code> - the toolbar item's identifier</li></ul> |
| **Returns**                                          | <ul><li>the toolbar object</li></ul> |
| **Notes**                                            | <ul><li>This method completely removes the toolbar item from the toolbar's definition dictionary, thus removing it from active use in the toolbar as well as removing it from the customization panel, if supported.  If you only want to remove a toolbar item from the active toolbar, consider <a href="#removeItem">hs.webview.toolbar:removeItem</a>.</li></ul> |

#### [displayMode](#displaymode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.toolbar:displayMode([mode]) -> toolbarObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Get or set the toolbar's display mode. |
| **Parameters**                                       | <ul><li>mode - an optional string to set the size of the toolbar to "default", "label", "icon", or "both".</li></ul> |
| **Returns**                                          | <ul><li>if an argument is provided, returns the toolbar object; otherwise returns the current value</li></ul> |

#### [identifier](#identifier)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.toolbar:identifier() -> identifier` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The identifier for this toolbar. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The identifier for this toolbar.</li></ul> |

#### [insertItem](#insertitem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.toolbar:insertItem(id, index) -> toolbarObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Insert or move the toolbar item to the index position specified |
| **Parameters**                                       | <ul><li>id    - the string identifier of the toolbar item</li><li>index - the numerical position where the toolbar item should be inserted/moved to.</li></ul> |
| **Returns**                                          | <ul><li>the toolbar object</li></ul> |
| **Notes**                                            | <ul><li>the toolbar position must be between 1 and the number of currently active toolbar items.</li></ul> |

#### [isAttached](#isattached)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.toolbar:isAttached() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a boolean indicating whether or not the toolbar is currently attached to a window. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a boolean indicating whether or not the toolbar is currently attached to a window.</li></ul> |

#### [isCustomizing](#iscustomizing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.toolbar:isCustomizing() -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Indicates whether or not the customization panel is currently open for the toolbar. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>true or false indicating whether or not the customization panel is open for the toolbar</li></ul> |

#### [itemDetails](#itemdetails)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.toolbar:itemDetails(id) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a table containing details about the specified toolbar item |
| **Parameters**                                       | <ul><li>id - a string identifier specifying the toolbar item</li></ul> |
| **Returns**                                          | <ul><li>a table containing the toolbar item definition</li></ul> |
| **Notes**                                            | <ul><li>For a list of the most of the possible toolbar item attribute keys, see <a href="#addItems">hs.webview.toolbar:addItems</a>.</li><li>The table will also include <code>privateCallback</code> which will be a boolean indicating whether or not this toolbar item has a private callback function assigned (true) or uses the toolbar's general callback function (false).</li><li>The returned table may also contain the following keys, if the item is currently assigned to a toolbar:</li><li><code>toolbar</code>  - the toolbar object the item belongs to</li><li><code>subItems</code> - if the toolbar item is actually a group, this will contain a table with basic information about the members of the group.  If you wish to get the full details for each sub-member, you may iterate on the identifiers provided in <code>groupMembers</code>.</li></ul> |

#### [items](#items)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.toolbar:items() -> array` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns an array of the toolbar item identifiers currently assigned to the toolbar. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a table as an array of the currently active (assigned) toolbar item identifiers.  Toolbar items which are in the overflow menu <em>are</em> included in this array.  See also <a href="#visibleItems">hs.webview.toolbar:visibleItems</a> and <a href="#allowedItems">hs.webview.toolbar:allowedItems</a>.</li></ul> |

#### [modifyItem](#modifyitem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.toolbar:modifyItem(table) -> toolbarObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Modify the toolbar item specified by the "id" key in the table argument. |
| **Parameters**                                       | <ul><li>a table containing an "id" key and the attributes to change for the toolbar item.</li></ul> |
| **Returns**                                          | <ul><li>the toolbarObject</li></ul> |
| **Notes**                                            | <ul><li>You cannot change a toolbar item's <code>id</code></li><li>For a list of the possible toolbar item attribute keys, see <a href="#addItems">hs.webview.toolbar:addItems</a>.</li></ul> |

#### [notifyOnChange](#notifyonchange)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.toolbar:notifyOnChange([bool]) -> toolbarObject | bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Get or set whether or not the global callback function is invoked when a toolbar item is added or removed from the toolbar. |
| **Parameters**                                       | <ul><li>an optional boolean value to enable or disable invoking the global callback for toolbar changes.</li></ul> |
| **Returns**                                          | <ul><li>if an argument is provided, returns the toolbar object; otherwise returns the current value</li></ul> |

#### [removeItem](#removeitem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.toolbar:removeItem(index | identifier) -> toolbarObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Remove the toolbar item at the index position specified, or with the specified identifier, if currently present in the toolbar. |
| **Parameters**                                       | <ul><li><code>index</code> - the numerical position of the toolbar item to remove.</li><li><code>identifier</code> - the identifier of the toolbar item to remove, if currently active in the toolbar</li></ul> |
| **Returns**                                          | <ul><li>the toolbar object</li></ul> |
| **Notes**                                            | <ul><li>the toolbar position must be between 1 and the number of currently active toolbar items.</li></ul> |

#### [savedSettings](#savedsettings)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.toolbar:savedSettings() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a table containing the settings which will be saved for the toolbar if [hs.webview.toolbar:autosaves](#autosaves) is true. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a table containing the toolbar settings</li></ul> |
| **Notes**                                            | <ul><li>If the toolbar is set to autosave, then a user-defaults entry is created in org.hammerspoon.Hammerspoon domain with the key "NSToolbar Configuration XXX" where XXX is the toolbar identifier specified when the toolbar was created.</li><li>This method is provided if you do not wish for changes to the toolbar to be autosaved for every change, but may wish to save it programmatically under specific conditions.</li></ul> |

#### [selectedItem](#selecteditem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.toolbar:selectedItem([item]) -> toolbarObject | item` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Get or set the selected toolbar item |
| **Parameters**                                       | <ul><li>item - an optional id for the toolbar item to show as selected, or an explicit nil if you wish for no toolbar item to be selected.</li></ul> |
| **Returns**                                          | <ul><li>if an argument is provided, returns the toolbar object; otherwise returns the current value</li></ul> |
| **Notes**                                            | <ul><li>Only toolbar items which were defined as <code>selectable</code> when created with <a href="#new">hs.webview.toolbar.new</a> can be selected with this method.</li></ul> |

#### [selectSearchField](#selectsearchfield)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.toolbar:selectSearchField([identifier]) -> toolbarObject | false` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Programmatically focus the search field for keyboard input. |
| **Parameters**                                       | <ul><li>identifier - an optional string specifying the id of the specific search field to focus.  If this parameter is not provided, this method attempts to focus the first active searchfield found in the toolbar</li></ul> |
| **Returns**                                          | <ul><li>if the searchfield can be found and is currently in the toolbar, returns the toolbarObject; otherwise returns false.</li></ul> |
| **Notes**                                            | <ul><li>if there is current text in the searchfield, it will be selected so that any subsequent typing by the user will replace the current value in the searchfield.</li></ul> |

#### [separator](#separator)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.toolbar:separator([bool]) -> toolbarObject | bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Get or set whether or not the toolbar shows a separator between the toolbar and the main window contents. |
| **Parameters**                                       | <ul><li>an optional boolean value to enable or disable the separator.</li></ul> |
| **Returns**                                          | <ul><li>if an argument is provided, returns the toolbar object; otherwise returns the current value</li></ul> |

#### [setCallback](#setcallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.toolbar:setCallback(fn) -> toolbarObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets or removes the global callback function for the toolbar. |
| **Parameters**                                       | <ul><li>fn - a function to set as the global callback for the toolbar, or nil to remove the global callback.</li></ul> |
| **Returns**                                          | <ul><li>the toolbar object.</li></ul> |
| **Notes**                                            | <ul><li>the global callback function is invoked for a toolbar button item that does not have a specific function assigned directly to it.</li><li>if <a href="#notifyOnChange">hs.webview.toolbar:notifyOnChange</a> is set to true, then this callback function will also be invoked when a toolbar item is added or removed from the toolbar either programmatically with <a href="#insertItem">hs.webview.toolbar:insertItem</a> and <a href="#removeItem">hs.webview.toolbar:removeItem</a> or under user control with <a href="#customizePanel">hs.webview.toolbar:customizePanel</a> and the callback function will receive a string of "add" or "remove" as a fourth argument.</li></ul> |

#### [sizeMode](#sizemode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.toolbar:sizeMode([size]) -> toolbarObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Get or set the toolbar's size. |
| **Parameters**                                       | <ul><li>size - an optional string to set the size of the toolbar to "default", "regular", or "small".</li></ul> |
| **Returns**                                          | <ul><li>if an argument is provided, returns the toolbar object; otherwise returns the current value</li></ul> |

#### [visible](#visible)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.toolbar:visible([bool]) -> toolbarObject | bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Get or set whether or not the toolbar is currently visible in the window it is attached to. |
| **Parameters**                                       | <ul><li>an optional boolean value to show or hide the toolbar.</li></ul> |
| **Returns**                                          | <ul><li>if an argument is provided, returns the toolbar object; otherwise returns the current value</li></ul> |

#### [visibleItems](#visibleitems)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.webview.toolbar:visibleItems() -> array` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns an array of the currently visible toolbar item identifiers. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a table as an array of the currently visible toolbar item identifiers.  Toolbar items which are in the overflow menu are <em>not</em> included in this array.  See also <a href="#items">hs.webview.toolbar:items</a> and <a href="#allowedItems">hs.webview.toolbar:allowedItems</a>.</li></ul> |

