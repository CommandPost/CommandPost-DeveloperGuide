# [docs](index.md) » plugins.finalcutpro.notifications.prowl
---

Prowl Notifications Plugin.

## API Overview
* Functions - API calls offered directly by the extension
 * [init](#init)
 * [sendNotification](#sendnotification)
 * [update](#update)
 * [validateAPIKey](#validateapikey)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [apiKey](#apikey)
 * [apiValidated](#apivalidated)
 * [enabled](#enabled)

## API Documentation

### Functions

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.notifications.prowl.init() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Initialises the plugin. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [sendNotification](#sendnotification)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.notifications.prowl.sendNotification(message, [title]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sends a notification. |
| **Parameters**                                       | <ul><li>message - The message you want to send as a string.</li><li>[title] - An optional Title for the message as a string.</li></ul> |
| **Returns**                                          | <ul><li>success - <code>true</code> if successful otherwise <code>false</code></li><li>errorMessage - a string containing any error messages</li></ul> |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.notifications.prowl.update() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Enables or disables Prowl Notifications depending on the user's preferences. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [validateAPIKey](#validateapikey)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.notifications.prowl.validateAPIKey(key) -> success, errorMessage` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Validates a Growl API Key |
| **Parameters**                                       | <ul><li>key - The API key as string</li></ul> |
| **Returns**                                          | <ul><li>success - <code>true</code> if successful otherwise <code>false</code></li><li>errorMessage - a string containing any error messages</li></ul> |

### Fields

#### [apiKey](#apikey)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.notifications.prowl.apiKey <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Prowl API Key |

#### [apiValidated](#apivalidated)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.notifications.prowl.apiValidated <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Whether or not the API key has been validated. |

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.notifications.prowl.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Whether or not the plugin has been enabled. |

