# [docs](index.md) » plugins.finalcutpro.notifications.ifttt
---

IFTTT Notifications Plugin.

Author: [JFtechOfficial](https://github.com/JFtechOfficial)

## API Overview
* Functions - API calls offered directly by the extension
 * [init](#init)
 * [sendNotification](#sendnotification)
 * [update](#update)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [appAPIKey](#appapikey)
 * [enabled](#enabled)
 * [userAPIKey](#userapikey)

## API Documentation

### Functions

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.notifications.ifttt.init() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Initialises the plugin. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [sendNotification](#sendnotification)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.notifications.ifttt.sendNotification(message, [title]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sends a notification. |
| **Parameters**                                       | <ul><li>message - The message you want to send as a string.</li><li>[title] - An optional Title for the message as a string.</li></ul> |
| **Returns**                                          | <ul><li>success - <code>true</code> if successful otherwise <code>false</code></li><li>errorMessage - a string containing any error messages</li></ul> |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.notifications.ifttt.update() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Enables or disables ifttt Notifications depending on the user's preferences. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

### Fields

#### [appAPIKey](#appapikey)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.notifications.ifttt.appAPIKey <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Application API Key |

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.notifications.ifttt.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Whether or not the plugin has been enabled. |

#### [userAPIKey](#userapikey)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.notifications.ifttt.userAPIKey <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | User API Key |

