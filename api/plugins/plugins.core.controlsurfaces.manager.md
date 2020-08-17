# [docs](index.md) » plugins.core.controlsurfaces.manager
---

Manager for the CommandPost Preferences Window.

## API Overview
* Constants - Useful values which cannot be changed
 * [DEFAULT_HEIGHT](#default_height)
 * [DEFAULT_WIDTH](#default_width)
 * [lastTab](#lasttab)
 * [NUMBER_OF_BANKS](#number_of_banks)
 * [NUMBER_OF_DEVICES](#number_of_devices)
 * [position](#position)
 * [WEBVIEW_LABEL](#webview_label)
* Variables - Configurable values
 * [_handlers](#_handlers)
 * [_panels](#_panels)
* Functions - API calls offered directly by the extension
 * [addHandler](#addhandler)
 * [addPanel](#addpanel)
 * [currentPanelID](#currentpanelid)
 * [focus](#focus)
 * [getHandler](#gethandler)
 * [getLabel](#getlabel)
 * [getWebview](#getwebview)
 * [hide](#hide)
 * [init](#init)
 * [injectScript](#injectscript)
 * [maxPanelHeight](#maxpanelheight)
 * [new](#new)
 * [refresh](#refresh)
 * [selectPanel](#selectpanel)
 * [setPanelRenderer](#setpanelrenderer)
 * [show](#show)

## API Documentation

### Constants

#### [DEFAULT_HEIGHT](#default_height)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.controlsurfaces.manager.DEFAULT_HEIGHT -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Default Height of Preferences Window |

#### [DEFAULT_WIDTH](#default_width)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.controlsurfaces.manager.DEFAULT_WIDTH -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Default Width of Preferences Window |

#### [lastTab](#lasttab)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.controlsurfaces.manager.lastTab` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Returns the last tab saved in settings. |

#### [NUMBER_OF_BANKS](#number_of_banks)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.controlsurfaces.manager.NUMBER_OF_BANKS -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Number of banks. |

#### [NUMBER_OF_DEVICES](#number_of_devices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.controlsurfaces.manager.NUMBER_OF_DEVICES -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Number of devices. |

#### [position](#position)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.controlsurfaces.manager.position` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Returns the last frame saved in settings. |

#### [WEBVIEW_LABEL](#webview_label)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.controlsurfaces.manager.WEBVIEW_LABEL -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The WebView Label |

### Variables

#### [_handlers](#_handlers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.controlsurfaces.manager._handlers -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Table containing handlers. |

#### [_panels](#_panels)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.controlsurfaces.manager._panels -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Table containing panels. |

### Functions

#### [addHandler](#addhandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.controlsurfaces.manager.addHandler(id, handlerFn) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Adds a Handler |
| **Parameters**                                       | <ul><li>id - The ID</li><li>handlerFn - the handler function</li></ul> |
| **Returns**                                          | <ul><li>Nothing</li></ul> |

#### [addPanel](#addpanel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.controlsurfaces.manager.addPanel(params) -> plugins.core.controlsurfaces.manager.panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Adds a new panel with the specified `params` to the preferences manager. |
| **Parameters**                                       | <ul><li><code>params</code> - The parameters table. Details below.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>panel</code> instance.</li></ul> |
| **Notes**                                            | <ul><li>The <code>params</code> can have the following properties. The <code>priority</code> and <code>id</code> and properties are <strong>required</strong>. <strong> <code>priority</code>      - An integer value specifying the priority of the panel compared to others. </strong> <code>id</code>            - A string containing the unique ID of the panel. <strong> <code>label</code>         - The human-readable label for the panel icon. </strong> <code>image</code>         - The <code>hs.image</code> for the panel icon. <strong> <code>tooltip</code>       - The human-readable details for the toolbar icon when the mouse is hovering over it. </strong> <code>closeFn</code>       - A callback function that's triggered when the Preferences window is closed.</li></ul> |

#### [currentPanelID](#currentpanelid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.controlsurfaces.manager.currentPanelID() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the panel ID with the highest priority. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The panel ID as a string</li></ul> |

#### [focus](#focus)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.controlsurfaces.manager.focus() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Puts focus on the Preferences Window. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful or otherwise <code>false</code>.</li></ul> |

#### [getHandler](#gethandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.controlsurfaces.manager.getHandler(id) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the handler for a given ID. |
| **Parameters**                                       | <ul><li>id - The ID</li></ul> |
| **Returns**                                          | <ul><li>Table</li></ul> |

#### [getLabel](#getlabel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.controlsurfaces.manager.getLabel() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the Webview label. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The Webview label as a string.</li></ul> |

#### [getWebview](#getwebview)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.controlsurfaces.manager.getWebview() -> hs.webview` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the Webview of the Preferences Window. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A <code>hs.webview</code></li></ul> |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.controlsurfaces.manager.hide() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Hides the Preferences Window. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.controlsurfaces.manager.init() -> nothing` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Initialises the preferences panel. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Nothing</li></ul> |

#### [injectScript](#injectscript)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.controlsurfaces.manager.injectScript(script) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Injects JavaScript into the Preferences Webview. |
| **Parameters**                                       | <ul><li>script - The JavaScript code you want to inject in the form of a string.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [maxPanelHeight](#maxpanelheight)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.controlsurfaces.manager.maxPanelHeight() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the maximum size defined by a panel. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The maximum panel height.</li></ul> |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.controlsurfaces.manager.new() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Creates a new Preferences Window. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [refresh](#refresh)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.controlsurfaces.manager.refresh() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Refreshes the Preferences Window. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [selectPanel](#selectpanel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.controlsurfaces.manager.selectPanel(id) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Selects a Preferences Panel. |
| **Parameters**                                       | <ul><li>id - the ID of the panel you want to select.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [setPanelRenderer](#setpanelrenderer)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.controlsurfaces.manager.setPanelRenderer(renderer) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sets a Panel Renderer |
| **Parameters**                                       | <ul><li>renderer - The renderer</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.controlsurfaces.manager.show() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Shows the Preferences Window |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>True if successful or nil if an error occurred</li></ul> |

