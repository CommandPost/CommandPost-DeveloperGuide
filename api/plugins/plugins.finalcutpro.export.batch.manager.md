# [docs](index.md) » plugins.finalcutpro.export.batch.manager
---

Manager for the Batch Export Window.

## Submodules
 * [plugins.finalcutpro.export.batch.manager.panel](plugins.finalcutpro.export.batch.manager.panel.md)

## API Overview
* Constants - Useful values which cannot be changed
 * [DEFAULT_HEIGHT](#default_height)
 * [DEFAULT_TITLE](#default_title)
 * [DEFAULT_WIDTH](#default_width)
 * [DEFAULT_WINDOW_STYLE](#default_window_style)
 * [lastTab](#lasttab)
 * [position](#position)
 * [WEBVIEW_LABEL](#webview_label)
* Variables - Configurable values
 * [_handlers](#_handlers)
 * [_panels](#_panels)
* Functions - API calls offered directly by the extension
 * [addHandler](#addhandler)
 * [addPanel](#addpanel)
 * [disabledPanels](#disabledpanels)
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
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.DEFAULT_HEIGHT -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Default Height of Preferences Window                                                                                         |

#### [DEFAULT_TITLE](#default_title)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.DEFAULT_TITLE -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Default Title of Preferences Window                                                                                         |

#### [DEFAULT_WIDTH](#default_width)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.DEFAULT_WIDTH -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Default Width of Preferences Window                                                                                         |

#### [DEFAULT_WINDOW_STYLE](#default_window_style)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.DEFAULT_WINDOW_STYLE -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Default Webview Window Style of Preferences Window                                                                                         |

#### [lastTab](#lasttab)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.lastTab` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Returns the last tab saved in settings.                                                                                         |

#### [position](#position)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.position` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Returns the last frame saved in settings.                                                                                         |

#### [WEBVIEW_LABEL](#webview_label)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.WEBVIEW_LABEL -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The WebView Label                                                                                         |

### Variables

#### [_handlers](#_handlers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager._handlers -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Table containing handlers.                                                                                         |

#### [_panels](#_panels)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager._panels -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Table containing panels.                                                                                         |

### Functions

#### [addHandler](#addhandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.addHandler(id, handlerFn) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Adds a Handler                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">id - The ID</li><li markdown="1">handlerFn - the handler function</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">Nothing</li></ul>          |

#### [addPanel](#addpanel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.addPanel(params) -> plugins.finalcutpro.export.batch.manager.panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Adds a new panel with the specified `params` to the Batch Export manager.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">`params` - The parameters table. Details below.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The new `panel` instance.</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">The `params` can have the following properties. The `priority` and `id` and properties are **required**.</li><li markdown="1"> ** `priority`      - An integer value specifying the priority of the panel compared to others.</li><li markdown="1"> ** `id`            - A string containing the unique ID of the panel.</li><li markdown="1"> ** `label`         - The human-readable label for the panel icon.</li><li markdown="1"> ** `image`         - The `hs.image` for the panel icon.</li><li markdown="1"> ** `tooltip`       - The human-readable details for the toolbar icon when the mouse is hovering over it.</li><li markdown="1"> ** `closeFn`       - A callback function that's triggered when the Preferences window is closed.</li></ul>                |

#### [disabledPanels](#disabledpanels)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.disabledPanels(ids) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets which panels are disabled.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">ids - A table of panel ID's to disable</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [focus](#focus)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.focus() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Puts focus on the Batch Export Window.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`true` if successful or otherwise `false`.</li></ul>          |

#### [getHandler](#gethandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.getHandler(id) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the handler for a given ID.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">id - The ID</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">Table</li></ul>          |

#### [getLabel](#getlabel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.getLabel() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the Webview label.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The Webview label as a string.</li></ul>          |

#### [getWebview](#getwebview)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.getWebview() -> hs.webview` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the Webview of the Preferences Window.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A `hs.webview`</li></ul>          |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.hide() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Hides the Batch Export Window.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.init() -> nothing` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialises the preferences panel.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">Nothing</li></ul>          |

#### [injectScript](#injectscript)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.injectScript(script) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Injects JavaScript into the Batch Export Webview.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">script - The JavaScript code you want to inject in the form of a string.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [maxPanelHeight](#maxpanelheight)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.maxPanelHeight() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the maximum size defined by a panel.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The maximum panel height.</li></ul>          |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.new() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates a new Preferences Window.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [refresh](#refresh)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.refresh() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Refreshes the Batch Export Window.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [selectPanel](#selectpanel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.selectPanel(id) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Selects a Batch Export Panel.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">id - the ID of the panel you want to select.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [setPanelRenderer](#setpanelrenderer)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.setPanelRenderer(renderer) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets a Panel Renderer                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">renderer - The renderer</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.manager.show() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Shows the Preferences Window                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">True if successful or nil if an error occurred</li></ul>          |

