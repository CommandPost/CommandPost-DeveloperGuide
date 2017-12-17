# [docs](index.md) » plugins.finalcutpro.notifications.pushover
---

Pushover Notifications Plugin.

## API Overview
* Functions - API calls offered directly by the extension
 * [init](#init)
 * [sendNotification](#sendnotification)
 * [update](#update)
 * [validateAPIKeys](#validateapikeys)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [apiValidated](#apivalidated)
 * [appAPIKey](#appapikey)
 * [enabled](#enabled)
 * [userAPIKey](#userapikey)

## API Documentation

### Functions

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.notifications.pushover.init() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialises the plugin.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [sendNotification](#sendnotification)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.notifications.pushover.sendNotification(message, [title]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sends a notification.                                                                                         |
| **Parameters**                                       | <ul><li>message - The message you want to send as a string.</li><li>[title] - An optional Title for the message as a string.</li></ul> |
| **Returns**                                          | <ul><li>success - `true` if successful otherwise `false`</li><li>errorMessage - a string containing any error messages</li></ul>          |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.notifications.pushover.update() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Enables or disables Pushover Notifications depending on the user's preferences.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [validateAPIKeys](#validateapikeys)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.notifications.pushover.validateAPIKeys(userKey, appKey) -> success, errorMessage` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Validates a Pushover User & Application API Key                                                                                         |
| **Parameters**                                       | <ul><li>userKey - The User API Key as a string</li><li>appKey - The Application API Key as a string</li></ul> |
| **Returns**                                          | <ul><li>success - `true` if successful otherwise `false`</li><li>errorMessage - a string containing any error messages</li></ul>          |

### Fields

#### [apiValidated](#apivalidated)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.notifications.pushover.apiValidated <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Whether or not the API keys have been validated.                                                                                         |

#### [appAPIKey](#appapikey)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.notifications.pushover.appAPIKey <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Application API Key                                                                                         |

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.notifications.pushover.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Whether or not the plugin has been enabled.                                                                                         |

#### [userAPIKey](#userapikey)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.notifications.pushover.userAPIKey <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | User API Key                                                                                         |

