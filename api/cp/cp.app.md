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
* Constructors - API calls which return an object, typically one that offers API methods
 * [forBundleID](#forbundleid)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [frontmostApp](#frontmostapp)
* Methods - API calls which can only be made on an object returned by a constructor
 * [bestSupportedLocale](#bestsupportedlocale)
 * [bundleID](#bundleid)
 * [hide](#hide)
 * [isSupportedLocale](#issupportedlocale)
 * [launch](#launch)
 * [menu](#menu)
 * [notifier](#notifier)
 * [quit](#quit)
 * [restart](#restart)
 * [show](#show)
 * [update](#update)

## API Documentation

### Functions

#### [apps](#apps)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.apps() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a list of all apps that have been requested via [forBundleID](#forBundleID), in no particular order.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A list of <code>cp.app</code> instances.</li></ul>            |

#### [bundleIDs](#bundleids)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.bundleIDs() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a list of Bundle IDs which have been requested via [forBundleID](#forBundleID).                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A list of Bundle IDs.</li></ul>            |

### Constructors

#### [forBundleID](#forbundleid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.forBundleID(bundleID)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Returns the `cp.app` for the specified Bundle ID. If the app has already been created,                                                                                         |
| **Parameters**                                       | <ul><li>bundleID      - The application bundle ID to find the app for.</li></ul>   |
| **Returns**                                          | <ul><li>The <code>cp.app</code> for the bundle.</li></ul>            |

### Fields

#### [frontmostApp](#frontmostapp)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app.frontmostApp <cp.prop: cp.app; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns the most recent 'registered' app that was active, other than CommandPost itself.                                                                                         |

### Methods

#### [bestSupportedLocale](#bestsupportedlocale)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app:bestSupportedLocale(locale) -> cp.i18n.localeID or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Finds the closest match for the specified locale. The returned locale                                                                                         |
| **Parameters**                                       | <ul><li>locale    - The local to match</li></ul>   |
| **Returns**                                          | <ul><li>The closest supported locale or <code>nil</code> if none are available in the language.</li></ul>            |

#### [bundleID](#bundleid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app:bundleID() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Bundle ID for the app.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The Bundle ID.</li></ul>            |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app:hide() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides the application, if it's currently running.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The <code>cp.app</code> instance.</li></ul>            |

#### [isSupportedLocale](#issupportedlocale)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app:isSupportedLocale(locale) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Checks if the specified locale is supported. The `locale` can                                                                                         |
| **Parameters**                                       | <ul><li>locale    - The locale code string or <code>localeID</code> to check.</li></ul>   |
| **Returns**                                          | <ul><li><code>true</code> if it is supported, otherwise <code>false</code>.</li></ul>            |

#### [launch](#launch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app:launch(waitSeconds) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Launches the application, or brings it to the front if it was already running.                                                                                         |
| **Parameters**                                       | <ul><li><code>waitSeconds</code>    - If povided, the number of seconds to wait until the launch completes. If <code>nil</code>, it will return immediately.</li></ul>   |
| **Returns**                                          | <ul><li>The <code>cp.app</code> instance.</li></ul>            |

#### [menu](#menu)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app:menu() -> cp.app.menu` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the main `menu` for the application.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The <code>cp.app.menu</code> for the <code>cp.app</code> instance.</li></ul>            |

#### [notifier](#notifier)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app:notifier() -> cp.ui.notifier` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a `notifier` that is tracking the application UI element. It has already been started.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The notifier.</li></ul>            |

#### [quit](#quit)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app:quit(waitSeconds) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Asks the application to quit, if it's running. The app may not have actually quit after this                                                                                         |
| **Parameters**                                       | <ul><li><code>waitSeconds</code>    - If povided, the number of seconds to wait until the quit completes. If <code>nil</code>, it will return immediately.</li></ul>   |
| **Returns**                                          | <ul><li>The <code>cp.app</code> instance.</li></ul>            |

#### [restart](#restart)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app:restart(waitSeconds) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Restart the application, if currently running. If not, no action is taken.                                                                                         |
| **Parameters**                                       | <ul><li><code>waitSeconds</code>    - If povided, the number of seconds to wait until the quit completes. If <code>nil</code>, it will return immediately.</li></ul>   |
| **Returns**                                          | <ul><li>The <code>cp.app</code> instance.</li></ul>            |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app:show() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Ensure the app is onscreen if it is currently running.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The <code>cp.app</code> instance.</li></ul>            |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.app:update() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Updates the app, triggering any watchers if values have changed.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The <code>cp.app</code> instance.</li></ul>            |

