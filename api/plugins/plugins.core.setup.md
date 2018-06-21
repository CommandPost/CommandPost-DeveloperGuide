# [docs](index.md) » plugins.core.setup
---

Manager for the CommandPost Setup Screen.

## Submodules
 * [plugins.core.setup.panel](plugins.core.setup.panel.md)

## API Overview
* Constants - Useful values which cannot be changed
 * [DEFAULT_HEIGHT](#default_height)
 * [DEFAULT_TITLE](#default_title)
 * [DEFAULT_WIDTH](#default_width)
 * [enabled](#enabled)
 * [FIRST_PRIORITY](#first_priority)
 * [LAST_PRIORITY](#last_priority)
 * [visible](#visible)
* Variables - Configurable values
 * [onboardingRequired](#onboardingrequired)
 * [position](#position)
* Functions - API calls offered directly by the extension
 * [addPanel](#addpanel)
 * [currentPanel](#currentpanel)
 * [delete](#delete)
 * [focus](#focus)
 * [getLabel](#getlabel)
 * [init](#init)
 * [injectScript](#injectscript)
 * [new](#new)
 * [nextPanel](#nextpanel)
 * [setPanelRenderer](#setpanelrenderer)
 * [show](#show)
 * [update](#update)

## API Documentation

### Constants

#### [DEFAULT_HEIGHT](#default_height)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.DEFAULT_HEIGHT -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The default panel height.                                                                                         |

#### [DEFAULT_TITLE](#default_title)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.DEFAULT_TITLE -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The default panel title.                                                                                         |

#### [DEFAULT_WIDTH](#default_width)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.DEFAULT_WIDTH -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The default panel width.                                                                                         |

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Set to `true` if the manager is enabled. Defaults to `false`.                                                                                         |

#### [FIRST_PRIORITY](#first_priority)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.FIRST_PRIORITY -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The first panel priority.                                                                                         |

#### [LAST_PRIORITY](#last_priority)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.LAST_PRIORITY -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The last panel priority.                                                                                         |

#### [visible](#visible)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.visible <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A property indicating if the welcome window is visible on screen.                                                                                         |

### Variables

#### [onboardingRequired](#onboardingrequired)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.onboardingRequired <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Set to `true` if on-boarding is required otherwise `false`. Defaults to `true`.                                                                                         |

#### [position](#position)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.position <cp.prop: table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | The last known position of the Setup Window as a frame.                                                                                         |

### Functions

#### [addPanel](#addpanel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.addPanel(newPanel) -> panel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Adds the new panel to the manager. Panels are created via the                                                                                         |
| **Parameters**                                       | <ul><li><code>newPanel</code>   - The panel to add.</li></ul>   |
| **Returns**                                          | <ul><li>The manager.</li></ul>            |

#### [currentPanel](#currentpanel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.currentPanel() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | The Current Panel                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The current panel as a string</li></ul>            |

#### [delete](#delete)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.delete() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Deletes the Setup Panels.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [focus](#focus)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.focus() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Focuses on the Setup Panels window.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [getLabel](#getlabel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.getLabel() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the Webview label.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The Webview label as a string.</li></ul>            |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.init(env) -> module` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialises the module.                                                                                         |
| **Parameters**                                       | <ul><li>env - The plugin environment table</li></ul>   |
| **Returns**                                          | <ul><li>The Module</li></ul>            |

#### [injectScript](#injectscript)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.injectScript(script) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Injects JavaScript into the Setup Panels.                                                                                         |
| **Parameters**                                       | <ul><li>script - The JavaScript you want to inject as a string.</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.new() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates the Setup Panels.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [nextPanel](#nextpanel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.nextPanel() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Moves to the next panel. If the window is visible, the panel will be updated.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li><code>true</code> if there was another panel to move to, or <code>false</code> if no panels remain.</li></ul>            |

#### [setPanelRenderer](#setpanelrenderer)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.setPanelRenderer(renderer) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets a Panel Renderer                                                                                         |
| **Parameters**                                       | <ul><li>renderer - The renderer</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.show() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Shows the Setup Panels.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.setup.update() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Updates the Setup Panels.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

