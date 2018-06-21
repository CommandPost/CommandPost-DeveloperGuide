# [docs](index.md) » plugins.finalcutpro.hacks.shortcuts
---

Plugin that allows the user to customise the CommandPost shortcuts
via the Final Cut Pro Command Editor.

## API Overview
* Constants - Useful values which cannot be changed
 * [active](#active)
 * [installed](#installed)
 * [requiresActivation](#requiresactivation)
 * [requiresDeactivation](#requiresdeactivation)
 * [supported](#supported)
 * [uninstalled](#uninstalled)
* Functions - API calls offered directly by the extension
 * [init](#init)
 * [install](#install)
 * [refresh](#refresh)
 * [uninstall](#uninstall)
 * [update](#update)

## API Documentation

### Constants

#### [active](#active)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hacks.shortcuts.active <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A property that returns `true` if the FCPX shortcuts are active.                                                                                         |

#### [installed](#installed)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hacks.shortcuts.installed <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A property that returns `true` if the FCPX Hacks Shortcuts are currently installed in FCPX.                                                                                         |

#### [requiresActivation](#requiresactivation)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hacks.shortcuts.requiresActivation <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A property that returns `true` if the custom shortcuts are installed in FCPX but not active.                                                                                         |

#### [requiresDeactivation](#requiresdeactivation)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hacks.shortcuts.requiresDeactivation <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A property that returns `true` if the FCPX shortcuts are active but shortcuts are not installed.                                                                                         |

#### [supported](#supported)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hacks.shortcuts.supported <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A property that returns `true` if the a supported version of FCPX is installed.                                                                                         |

#### [uninstalled](#uninstalled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hacks.shortcuts.uninstalled <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A property that returns `true` if shortcuts is working on something.                                                                                         |

### Functions

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hacks.shortcuts.init() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialises the module.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [install](#install)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hacks.shortcuts.install(silently) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Installs the Hacks Shortcuts.                                                                                         |
| **Parameters**                                       |  * `silently`   - (optional) If `true`, the user will not be prompted first.                                       |
| **Returns**                                          |  * `true` if successful.                                                |

#### [refresh](#refresh)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hacks.shortcuts.refresh() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Refresh Hacks Shortcuts if they're enabled.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [uninstall](#uninstall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hacks.shortcuts.uninstall(silently) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Uninstalls the Hacks Shortcuts, if they have been installed                                                                                         |
| **Parameters**                                       |  * `silently`   - (optional) If `true`, the user will not be prompted first.                                       |
| **Returns**                                          |  * `true` if successful.                                                |
| **Notes**                                            |  * Used by Trash Preferences menubar command.                                                      |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hacks.shortcuts.update() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Read shortcut keys from the Final Cut Pro Preferences.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

