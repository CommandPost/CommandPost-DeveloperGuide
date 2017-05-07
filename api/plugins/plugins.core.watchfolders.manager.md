# [docs](index.md) » plugins.core.watchfolders.manager
---

Manager for the CommandPost Watch Folders Panel.

## Submodules
 * [plugins.core.watchfolders.manager.panel](plugins.core.watchfolders.manager.panel.md)

## API Overview
* Constants - Useful values which cannot be changed
 * [position](#position)
* Functions - API calls offered directly by the extension
 * [addPanel](#addpanel)
 * [init](#init)
 * [showPreferences](#showpreferences)

## API Documentation

### Constants

#### [position](#position)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.position <cp.prop: table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Returns the last frame saved in settings.                                                                                         |

### Functions

#### [addPanel](#addpanel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.addPanel(params) -> plugins.core.watchfolders.manager.panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Adds a new panel with the specified `params` to the preferences manager.                                                                                         |
| **Parameters**                                       | <ul><li>`params`	- The parameters table. Details below.</li></ul> |
| **Returns**                                          | <ul><li>The new `panel` instance.</li></ul>          |
| **Notes**                                            | <ul><li>The `params` can have the following properties. The `priority` and `id` and properties are **required**.</li><li> ** `priority`		- An integer value specifying the priority of the panel compared to others.</li><li> ** `id`			- A string containing the unique ID of the panel.</li><li> ** `label`			- The human-readable label for the panel icon.</li><li>	 ** `image`			- The `hs.image` for the panel icon.</li><li> ** `tooltip`		- The human-readable details for the toolbar icon when the mouse is hovering over it.</li></ul>                |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.init() -> nothing` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialises the preferences panel.                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* Nothing</li></ul>          |

#### [showPreferences](#showpreferences)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.watchfolders.manager.showPreferences() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Shows the Preferences Window                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>True if successful or nil if an error occurred</li></ul>          |

