# [docs](index.md) » plugins.core.setup
---

Manager for the CommandPost Setup Screen.

## Submodules
 * [plugins.core.setup.panel](plugins.core.setup.panel.md)

## API Overview
* Constants - Useful values which cannot be changed
 * [enabled](#enabled)
 * [visible](#visible)
* Functions - API calls offered directly by the extension
 * [addPanel](#addpanel)
 * [nextPanel](#nextpanel)

## API Documentation

### Constants

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Set to `true` if the manager is enabled. Defaults to `false`.                                                                                         |

#### [visible](#visible)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.visible <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A property indicating if the welcome window is visible on screen.                                                                                         |

### Functions

#### [addPanel](#addpanel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.addPanel(newPanel) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Adds the new panel to the manager. Panels are created via the                                                                                         |
| **Parameters**                                       | <ul><li>`newPanel`	- The panel to add.</li></ul> |
| **Returns**                                          | <ul><li>The manager.</li></ul>          |

#### [nextPanel](#nextpanel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.nextPanel() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Moves to the next panel. If the window is visible, the panel will be updated.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>`true` if there was another panel to move to, or `false` if no panels remain.</li></ul>          |

