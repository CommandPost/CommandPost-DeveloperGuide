# [docs](index.md) » plugins.core.watchfolders.manager
---

Manager for the CommandPost Watch Folders Panel.

## Submodules
 * [plugins.core.watchfolders.manager.panel](plugins.core.watchfolders.manager.panel.md)

## API Overview
* Constants - Useful values which cannot be changed
 * [DEFAULT_HEIGHT](#default_height)
 * [DEFAULT_TITLE](#default_title)
 * [DEFAULT_WIDTH](#default_width)
 * [DEFAULT_WINDOW_STYLE](#default_window_style)
 * [position](#position)
 * [WEBVIEW_LABEL](#webview_label)
* Functions - API calls offered directly by the extension
 * [addHandler](#addhandler)
 * [addPanel](#addpanel)
 * [getHandler](#gethandler)
 * [getLabel](#getlabel)
 * [hide](#hide)
 * [init](#init)
 * [injectScript](#injectscript)
 * [maxPanelHeight](#maxpanelheight)
 * [selectPanel](#selectpanel)
 * [setPanelRenderer](#setpanelrenderer)
 * [show](#show)

## API Documentation

### Constants

#### [DEFAULT_HEIGHT](#default_height)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.DEFAULT_HEIGHT -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Default Height of the Watch Folder Window                                                                                         |

#### [DEFAULT_TITLE](#default_title)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.DEFAULT_TITLE -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Default Title of the Watch Folder Window                                                                                         |

#### [DEFAULT_WIDTH](#default_width)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.DEFAULT_WIDTH -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Default Width of the Watch Folder Window                                                                                         |

#### [DEFAULT_WINDOW_STYLE](#default_window_style)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.DEFAULT_WINDOW_STYLE -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Table of Default Window Style                                                                                         |

#### [position](#position)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.position <cp.prop: table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Returns the last frame saved in settings.                                                                                         |

#### [WEBVIEW_LABEL](#webview_label)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.WEBVIEW_LABEL -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | WebView Label                                                                                         |

### Functions

#### [addHandler](#addhandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.addHandler(id, handlerFn) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Adds a Handler                                                                                         |
| **Parameters**                                       |  * id - The ID * handlerFn - the handler function                                       |
| **Returns**                                          |  * Nothing                                                |

#### [addPanel](#addpanel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.addPanel(params) -> plugins.core.watchfolders.manager.panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Adds a new panel with the specified `params` to the preferences manager.                                                                                         |
| **Parameters**                                       |  * `params` - The parameters table. Details below.                                       |
| **Returns**                                          |  * The new `panel` instance.                                                |
| **Notes**                                            |  * The `params` can have the following properties. The `priority` and `id` and properties are **required**. ** `priority`      - An integer value specifying the priority of the panel compared to others. ** `id`            - A string containing the unique ID of the panel. ** `label`         - The human-readable label for the panel icon. ** `image`         - The `hs.image` for the panel icon. ** `tooltip`       - The human-readable details for the toolbar icon when the mouse is hovering over it.                                                      |

#### [getHandler](#gethandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.getHandler(id) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the handler for a given ID.                                                                                         |
| **Parameters**                                       |  * id - The ID                                       |
| **Returns**                                          |  * Table                                                |

#### [getLabel](#getlabel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.getLabel() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the Webview label.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The Webview label as a string.                                                |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.hide() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Hides the Watch Folders Window                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * True if successful or nil if an error occurred                                                |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.init() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialises the Watch Folder Manager.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * Nothing                                                |

#### [injectScript](#injectscript)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.injectScript(script) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Injects JavaScript into the Watch Folders Webview.                                                                                         |
| **Parameters**                                       |  * script - The JavaScript code you want to inject in the form of a string.                                       |
| **Returns**                                          |  * None                                                |

#### [maxPanelHeight](#maxpanelheight)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.maxPanelHeight() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the maximum panel height as a number                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * A number                                                |

#### [selectPanel](#selectpanel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.selectPanel(id) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Selects a Preferences Panel.                                                                                         |
| **Parameters**                                       |  * id - the ID of the panel you want to select.                                       |
| **Returns**                                          |  * None                                                |

#### [setPanelRenderer](#setpanelrenderer)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.setPanelRenderer(renderer) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets a Panel Renderer                                                                                         |
| **Parameters**                                       |  * renderer - The renderer                                       |
| **Returns**                                          |  * None                                                |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.show() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Shows the Watch Folders Window                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * True if successful or nil if an error occurred                                                |

