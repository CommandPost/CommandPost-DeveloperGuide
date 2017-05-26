# [docs](index.md) » plugins.finalcutpro.hacks.shortcuts
---

Plugin that allows the user to customise the CommandPost shortcuts
via the Final Cut Pro Command Editor.

## API Overview
* Constants - Useful values which cannot be changed
 * [active](#active)
 * [installed](#installed)
 * [onboardingRequired](#onboardingrequired)
 * [requiresActivation](#requiresactivation)
 * [requiresDeactivation](#requiresdeactivation)
 * [setupRequired](#setuprequired)
 * [supported](#supported)
 * [uninstalled](#uninstalled)
* Functions - API calls offered directly by the extension
 * [editCommands](#editcommands)
 * [init](#init)
 * [install](#install)
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

#### [onboardingRequired](#onboardingrequired)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hacks.shortcuts.onboardingRequired <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | If `true`, the initial setup has been completed.                                                                                         |

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

#### [setupRequired](#setuprequired)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hacks.shortcuts.setupRequired <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | If `true`, the user needs to configure Hacks Shortcuts.                                                                                         |

#### [supported](#supported)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hacks.shortcuts.supported <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A property that returns `true` if the a supported version of FCPX is installed.                                                                                         |

#### [uninstalled](#uninstalled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hacks.shortcuts.uninstalled <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A property that returns `true` if the shortcuts are neither original or installed correctly.                                                                                         |

### Functions

#### [editCommands](#editcommands)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hacks.shortcuts.editCommands() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Launch the Final Cut Pro Command Editor                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hacks.shortcuts.init() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialises the module.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [install](#install)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hacks.shortcuts.install(silently) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Installs the Hacks Shortcuts.                                                                                         |
| **Parameters**                                       | <ul><li>`silently`	- (optional) If `true`, the user will not be prompted first.</li></ul> |
| **Returns**                                          | <ul><li>`true` if successful.</li></ul>          |

#### [uninstall](#uninstall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hacks.shortcuts.uninstall(silently) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Uninstalls the Hacks Shortcuts, if they have been installed                                                                                         |
| **Parameters**                                       | <ul><li>`silently`	- (optional) If `true`, the user will not be prompted first.</li></ul> |
| **Returns**                                          | <ul><li>`true` if successful.</li></ul>          |
| **Notes**                                            | <ul><li>Used by Trash Preferences menubar command.</li></ul>                |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hacks.shortcuts.update() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Read shortcut keys from the Final Cut Pro Preferences.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

