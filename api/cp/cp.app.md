# [docs](index.md) » cp.app
---

This class assists with working with macOS apps. It provides functions for
finding, checking the running status, version number, path, and many other
values related to an application. It also provides support for launching,
quitting, and other activities related to applications.

This extension differs from the `hs.application` extension in several ways:
 * `cp.app` instances are long-lived. You request it once and it will stay up-to-date even if the app quits.
 * It makes extensive use of `cp.prop`, so you can `watch` many most properties of the app and get live notifications when they change.

## Submodules
 * [cp.app.menu](cp.app.menu.md)
 * [cp.app.prefs](cp.app.prefs.md)

## API Overview
* Functions - API calls offered directly by the extension
 * [apps](#apps)
 * [bundleIDs](#bundleids)
 * [is](#is)
* Constructors - API calls which return an object, typically one that offers API methods
 * [forBundleID](#forbundleid)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [frontmostApp](#frontmostapp)
* Methods - API calls which can only be made on an object returned by a constructor
 * [bestSupportedLocale](#bestsupportedlocale)
 * [bundleID](#bundleid)
 * [doHide](#dohide)
 * [doLaunch](#dolaunch)
 * [doQuit](#doquit)
 * [doRestart](#dorestart)
 * [doShow](#doshow)
 * [hide](#hide)
 * [isSupportedLocale](#issupportedlocale)
 * [launch](#launch)
 * [menu](#menu)
 * [notifier](#notifier)
 * [quit](#quit)
 * [searchResources](#searchresources)
 * [show](#show)
 * [update](#update)

## API Documentation

### Functions

#### [apps](#apps)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.apps() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a list of all apps that have been requested via [forBundleID](#forBundleID), in no particular order. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A list of <code>cp.app</code> instances.</li></ul> |

#### [bundleIDs](#bundleids)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.bundleIDs() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a list of Bundle IDs which have been requested via [forBundleID](#forBundleID). |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A list of Bundle IDs.</li></ul> |

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.is(thing) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the provided `thing` is a `cp.app` instance. |
| **Parameters**                                       | <ul><li>thing        - The thing to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if it is a <code>cp.app</code> instance, otherwise <code>false</code>.</li></ul> |

### Constructors

#### [forBundleID](#forbundleid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.forBundleID(bundleID)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Returns the `cp.app` for the specified Bundle ID. If the app has already been created, |
| **Parameters**                                       | <ul><li>bundleID      - The application bundle ID to find the app for.</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.app</code> for the bundle.</li></ul> |

### Fields

#### [frontmostApp](#frontmostapp)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.frontmostApp <cp.prop: cp.app; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns the most recent 'registered' app that was active, other than CommandPost itself. |

### Methods

#### [bestSupportedLocale](#bestsupportedlocale)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app:bestSupportedLocale(locale) -> cp.i18n.localeID or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Finds the closest match for the specified locale. The returned locale |
| **Parameters**                                       | <ul><li>locale    - The local to match</li></ul> |
| **Returns**                                          | <ul><li>The closest supported locale or <code>nil</code> if none are available in the language.</li></ul> |

#### [bundleID](#bundleid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app:bundleID() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the Bundle ID for the app. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The Bundle ID.</li></ul> |

#### [doHide](#dohide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app:doHide() -> cp.rx.go.Statement <boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `Statement` which will hide the app if it's currently running. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A <code>Statement</code>, resolving to <code>true</code> if the app is running and was successfully hidden, or <code>false</code> otherwise.</li></ul> |

#### [doLaunch](#dolaunch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app:doLaunch() -> cp.rx.Statement <boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `Statement` that can be run to launch or focus the current app. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code>, resolving to <code>true</code> after the app is frontmost.</li></ul> |
| **Notes**                                            | <ul><li>By default the <code>Statement</code> will time out after 30 seconds, sending an error signal.</li></ul> |

#### [doQuit](#doquit)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app:doQuit() -> cp.rx.go.Statement <boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `Statement` that will attempt to quit the app when executed. |
| **Parameters**                                       | <ul><li>None.</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code>, resolving to <code>true</code> if the app was running and was quit successfully, otherwise <code>false</code>.</li></ul> |
| **Notes**                                            | <ul><li>The Statement will time out after 60 seconds by default. This can be changed by calling the <code>TimeoutAfter</code> method on the Statement before executing.</li></ul> |

#### [doRestart](#dorestart)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app:doRestart() -> cp.rx.go.Statement <boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `Statement` which will attempt to restart the app. If the app |
| **Parameters**                                       | <ul><li>None.</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code>, resolving to <code>true</code> if the app was running and was quit and restarted successfully, otherwise <code>false</code>.</li></ul> |
| **Notes**                                            | <ul><li>The Statement will time out after 60 seconds by default. This can be changed by calling the <code>TimeoutAfter</code> method on the Statement before executing.</li></ul> |

#### [doShow](#doshow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app:doShow() -> cp.rx.go.Statement <boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `Statement` which will show the app if it's currently running. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A <code>Statement</code>, resolving to <code>true</code> if the app is running and was successfully shown, or <code>false</code> otherwise.</li></ul> |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app:hide() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Hides the application, if it's currently running. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.app</code> instance.</li></ul> |

#### [isSupportedLocale](#issupportedlocale)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app:isSupportedLocale(locale) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Checks if the specified locale is supported. The `locale` can |
| **Parameters**                                       | <ul><li>locale    - The locale code string or <code>localeID</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if it is supported, otherwise <code>false</code>.</li></ul> |

#### [launch](#launch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app:launch([waitSeconds]) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Launches the application, or brings it to the front if it was already running. |
| **Parameters**                                       | <ul><li><code>waitSeconds</code>    - If povided, the number of seconds to wait until the launch completes. If <code>nil</code>, it will return immediately.</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.app</code> instance.</li></ul> |

#### [menu](#menu)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app:menu() -> cp.app.menu` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the main `menu` for the application. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.app.menu</code> for the <code>cp.app</code> instance.</li></ul> |

#### [notifier](#notifier)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app:notifier() -> cp.ui.notifier` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `notifier` that is tracking the application UI element. It has already been started. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The notifier.</li></ul> |

#### [quit](#quit)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app:quit(waitSeconds) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Asks the application to quit, if it's running. The app may not have actually quit after this |
| **Parameters**                                       | <ul><li><code>waitSeconds</code>    - If povided, the number of seconds to wait until the quit completes. If <code>nil</code>, it will return immediately.</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.app</code> instance.</li></ul> |

#### [searchResources](#searchresources)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app:searchResources(value) -> hs.task` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Creates a `hs.task` which will search for the specified string value in the resources |
| **Parameters**                                       | <ul><li>value     - The string value to search for.</li></ul> |
| **Returns**                                          | <ul><li><code>hs.task</code> which is already running, searching for the <code>value</code>. Results will be output in the Error Log.</li></ul> |
| **Notes**                                            | <ul><li>This may take some time to complete, depending on how many resources the app contains.</li></ul> |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app:show() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Ensure the app is onscreen if it is currently running. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.app</code> instance.</li></ul> |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app:update() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Updates the app, triggering any watchers if values have changed. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.app</code> instance.</li></ul> |

