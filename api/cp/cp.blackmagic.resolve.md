# [docs](index.md) » cp.blackmagic.resolve
---

The Blackmagic DaVinci Resolve Extension.

## Submodules
 * [cp.blackmagic.resolve.app](cp.blackmagic.resolve.app.md)
 * [cp.blackmagic.resolve.color](cp.blackmagic.resolve.color.md)
 * [cp.blackmagic.resolve.main](cp.blackmagic.resolve.main.md)

## API Overview
* Constants - Useful values which cannot be changed
 * [EARLIEST_SUPPORTED_VERSION](#earliest_supported_version)
 * [preferences](#preferences)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [Color](#color)
 * [currentLocale](#currentlocale)
 * [isFrontmost](#isfrontmost)
 * [isInstalled](#isinstalled)
 * [isModalDialogOpen](#ismodaldialogopen)
 * [isRunning](#isrunning)
 * [isShowing](#isshowing)
 * [isSupported](#issupported)
 * [isUnsupported](#isunsupported)
 * [primaryWindow](#primarywindow)
 * [supportedLocales](#supportedlocales)
 * [UI](#ui)
 * [version](#version)
 * [versionString](#versionstring)
 * [windowsUI](#windowsui)
* Methods - API calls which can only be made on an object returned by a constructor
 * [bundleID](#bundleid)
 * [doHide](#dohide)
 * [doLaunch](#dolaunch)
 * [doQuit](#doquit)
 * [doRestart](#dorestart)
 * [doShow](#doshow)
 * [getPath](#getpath)
 * [hide](#hide)
 * [launch](#launch)
 * [notifier](#notifier)
 * [quit](#quit)
 * [show](#show)

## API Documentation

### Constants

#### [EARLIEST_SUPPORTED_VERSION](#earliest_supported_version)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.blackmagic.resolve.EARLIEST_SUPPORTED_VERSION <semver>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The earliest version this API supports. |

#### [preferences](#preferences)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.blackmagic.resolve.preferences <cp.app.prefs>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The `cp.app.prefs` for DaVinci Resolve. |

### Fields

#### [Color](#color)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.blackmagic.resolve.Color <cp.blackmagic.resolve.Color>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The Color Workspace. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the Browser</li></ul> |

#### [currentLocale](#currentlocale)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.blackmagic.resolve.currentLocale <cp.prop: cp.i18n.localeID; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Gets and sets the current locale for FCPX. |

#### [isFrontmost](#isfrontmost)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.blackmagic.resolve:isFrontmost <cp.prop: boolean; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Is DaVinci Resolve Frontmost? |

#### [isInstalled](#isinstalled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.blackmagic.resolve.isInstalled <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Is any version of DaVinci Resolve Installed? |

#### [isModalDialogOpen](#ismodaldialogopen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.blackmagic.resolve:isModalDialogOpen <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Is a modal dialog currently open? |

#### [isRunning](#isrunning)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.blackmagic.resolve.isRunning <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Is DaVinci Resolve Running? |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.blackmagic.resolve.isShowing <cp.prop: boolean; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Is Final Cut visible on screen? |

#### [isSupported](#issupported)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.blackmagic.resolve.isSupported <cp.prop: boolean; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Is a supported version of DaVinci Resolve installed? |

#### [isUnsupported](#isunsupported)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.blackmagic.resolve.isUnsupported <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Is an unsupported version of DaVinci Resolve installed? |

#### [primaryWindow](#primarywindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.blackmagic.resolve.primaryWindow <PrimaryWindow>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The DaVinci Resolve Primary Window. |

#### [supportedLocales](#supportedlocales)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.blackmagic.resolve.supportedLocales <cp.prop: table of cp.i18n.localeID; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The list of supported locales for this version of FCPX. |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.blackmagic.resolve.UI <cp.prop: hs._asm.axuielement; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The DaVinci Resolve `axuielement`, if available. |

#### [version](#version)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.blackmagic.resolve.version <cp.prop: semver; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The version number of the running or default installation of FCPX as a `semver`. |

#### [versionString](#versionstring)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.blackmagic.resolve.versionString <cp.prop: string; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The version number of the running or default installation of FCPX as a `string`. |

#### [windowsUI](#windowsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.blackmagic.resolve.windowsUI <cp.prop: hs._asm.axuielement; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns the UI containing the list of windows in the app. |

### Methods

#### [bundleID](#bundleid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.blackmagic.resolve:bundleID() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the Bundle ID for the app. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The Bundle ID</li></ul> |

#### [doHide](#dohide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.blackmagic.resolve:doHide() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will hide the FCP. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code> to execute.</li></ul> |

#### [doLaunch](#dolaunch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.blackmagic.resolve:doLaunch() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will launch, or focus it if already running FCP. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code> to execute.</li></ul> |

#### [doQuit](#doquit)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.blackmagic.resolve:doQuit() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will quit FCP. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code> to execute.</li></ul> |

#### [doRestart](#dorestart)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.blackmagic.resolve:doRestart() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.cp) that will restart DaVinci Resolve, if it is running. If not, nothing happens. |
| **Parameters**                                       | <ul><li>None.</li></ul> |
| **Returns**                                          | <ul><li>The FCP instance.</li></ul> |

#### [doShow](#doshow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.blackmagic.resolve:doShow() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will show FCP on-screen. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code> to execute.</li></ul> |

#### [getPath](#getpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.blackmagic.resolve:getPath() -> string or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Path to DaVinci Resolve Application |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string containing DaVinci Resolve's filesystem path, or nil if DaVinci Resolve's path could not be determined.</li></ul> |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.blackmagic.resolve:hide() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Hides DaVinci Resolve |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The FCP instance.</li></ul> |

#### [launch](#launch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.blackmagic.resolve:launch([waitSeconds], [path]) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Launches DaVinci Resolve, or brings it to the front if it was already running. |
| **Parameters**                                       | <ul><li><code>waitSeconds</code> - If provided, the number of seconds to wait until the launch                   completes. If <code>nil</code>, it will return immediately.</li><li><code>path</code>        - An optional full path to an application without an extension                   (i.e <code>/Applications/DaVinci Resolve 10.3.4</code>). This allows you to                   load previous versions of the application.</li></ul> |
| **Returns**                                          | <ul><li>The FCP instance.</li></ul> |

#### [notifier](#notifier)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.blackmagic.resolve:notifier() -> cp.ui.notifier` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a notifier that is tracking the application UI element. It has already been started. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The notifier.</li></ul> |

#### [quit](#quit)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.blackmagic.resolve:quit([waitSeconds]) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Quits DaVinci Resolve, if it's running. |
| **Parameters**                                       | <ul><li>waitSeconds      - The number of seconds to wait for the quit to complete.</li></ul> |
| **Returns**                                          | <ul><li>The FCP instance.</li></ul> |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.blackmagic.resolve:show() -> cp.blackmagic.resolve` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Activate DaVinci Resolve, if it is running. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The FCP instance.</li></ul> |

