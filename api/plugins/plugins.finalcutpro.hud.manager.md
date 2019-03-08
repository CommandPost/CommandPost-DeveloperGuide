# [docs](index.md) » plugins.finalcutpro.hud.manager
---

Manager for the Final Cut Pro HUD.

## API Overview
* Constants - Useful values which cannot be changed
 * [DEFAULT_HEIGHT](#default_height)
 * [DEFAULT_WIDTH](#default_width)
 * [lastTab](#lasttab)
 * [position](#position)
* Variables - Configurable values
 * [_handlers](#_handlers)
 * [_panels](#_panels)
* Functions - API calls offered directly by the extension
 * [addHandler](#addhandler)
 * [addPanel](#addpanel)
 * [currentPanelID](#currentpanelid)
 * [delete](#delete)
 * [focus](#focus)
 * [getHandler](#gethandler)
 * [getLabel](#getlabel)
 * [getWebview](#getwebview)
 * [hide](#hide)
 * [injectScript](#injectscript)
 * [maxPanelHeight](#maxpanelheight)
 * [new](#new)
 * [refresh](#refresh)
 * [resize](#resize)
 * [selectPanel](#selectpanel)
 * [show](#show)
 * [update](#update)
 * [updatePosition](#updateposition)
 * [updateVisibility](#updatevisibility)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [enabled](#enabled)

## API Documentation

### Constants

#### [DEFAULT_HEIGHT](#default_height)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.manager.DEFAULT_HEIGHT -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Default Height of HUD |

#### [DEFAULT_WIDTH](#default_width)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.manager.DEFAULT_WIDTH -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Default Width of HUD |

#### [lastTab](#lasttab)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.manager.lastTab` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Returns the last tab saved in settings. |

#### [position](#position)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.manager.position` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Returns the last frame saved in settings. |

### Variables

#### [_handlers](#_handlers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.manager._handlers -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Table containing handlers. |

#### [_panels](#_panels)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.manager._panels -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Table containing panels. |

### Functions

#### [addHandler](#addhandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.manager.addHandler(id, handlerFn) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Adds a Handler |
| **Parameters**                                       | <ul><li>id - The ID</li><li>handlerFn - the handler function</li></ul> |
| **Returns**                                          | <ul><li>Nothing</li></ul> |

#### [addPanel](#addpanel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.manager.addPanel(params) -> plugins.finalcutpro.hud.manager.panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Adds a new panel with the specified `params` to the HUD manager. |
| **Parameters**                                       | <ul><li><code>params</code> - The parameters table. Details below.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>panel</code> instance.</li></ul> |
| **Notes**                                            | <ul><li>The <code>params</code> can have the following properties. The <code>priority</code> and <code>id</code> and properties are <strong>required</strong>. <strong> <code>priority</code>      - An integer value specifying the priority of the panel compared to others. </strong> <code>id</code>            - A string containing the unique ID of the panel. <strong> <code>label</code>         - The human-readable label for the panel icon. </strong> <code>image</code>         - The <code>hs.image</code> for the panel icon. <strong> <code>tooltip</code>       - The human-readable details for the toolbar icon when the mouse is hovering over it. </strong> <code>openFn</code>        - A callback function that's triggered when the panel is opened. <strong> <code>closeFn</code>       - A callback function that's triggered when the panel is closed. </strong> <code>loadedFn</code>      - A callback function that's triggered when the panel is loaded.</li></ul> |

#### [currentPanelID](#currentpanelid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.manager.currentPanelID() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the panel ID with the highest priority. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The panel ID as a string</li></ul> |

#### [delete](#delete)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.manager.delete()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Deletes the existing HUD if it exists |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [focus](#focus)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.manager.focus() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Puts focus on the HUD. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful or otherwise <code>false</code>.</li></ul> |

#### [getHandler](#gethandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.manager.getHandler(id) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the handler for a given ID. |
| **Parameters**                                       | <ul><li>id - The ID</li></ul> |
| **Returns**                                          | <ul><li>Table</li></ul> |

#### [getLabel](#getlabel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.manager.getLabel() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the Webview label. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The Webview label as a string.</li></ul> |

#### [getWebview](#getwebview)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.manager.getWebview() -> hs.webview` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the Webview of the HUD. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A <code>hs.webview</code></li></ul> |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.manager.hide() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Hides the HUD. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [injectScript](#injectscript)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.manager.injectScript(script) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Injects JavaScript into the HUD Webview. |
| **Parameters**                                       | <ul><li>script - The JavaScript code you want to inject in the form of a string.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [maxPanelHeight](#maxpanelheight)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.manager.maxPanelHeight() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the maximum size defined by a panel. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The maximum panel height.</li></ul> |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.manager.new() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Creates a new HUD. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [refresh](#refresh)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.manager.refresh() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Refreshes the HUD. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [resize](#resize)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.manager.resize()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Resizes the HUD. |
| **Parameters**                                       | <ul><li>height - The new height of the HUD as number.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [selectPanel](#selectpanel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.manager.selectPanel([id]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Selects a HUD Panel. |
| **Parameters**                                       | <ul><li>id - the optional ID of the panel you want to select. If no ID is supplied then        the current panel ID will be used.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.manager.show() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Shows the HUD |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>True if successful or nil if an error occurred</li></ul> |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.manager.update() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Enables or Disables the HUD. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [updatePosition](#updateposition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.manager.updatePosition() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Updates the HUD position. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [updateVisibility](#updatevisibility)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.manager.updateVisibility() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Update the visibility of the HUD. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

### Fields

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.manager.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Is the HUD enabled in the settings? |

