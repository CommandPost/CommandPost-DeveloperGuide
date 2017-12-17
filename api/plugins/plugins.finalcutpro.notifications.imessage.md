# [docs](index.md) » plugins.finalcutpro.notifications.imessage
---

iMessage Notifications Plugin.

## API Overview
* Functions - API calls offered directly by the extension
 * [init](#init)
 * [sendNotification](#sendnotification)
 * [update](#update)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [enabled](#enabled)
 * [target](#target)

## API Documentation

### Functions

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.notifications.imessage.init() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialises the plugin.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [sendNotification](#sendnotification)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.notifications.imessage.sendNotification(message) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sends a notification.                                                                                         |
| **Parameters**                                       | <ul><li>message - The message you want to send as a string.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.notifications.imessage.update() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Enables or disables iMessage Notifications depending on the user's preferences.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

### Fields

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.notifications.imessage.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Whether or not the plugin has been enabled.                                                                                         |

#### [target](#target)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.notifications.imessage.target <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | A string containing a mobile number or Apple ID                                                                                         |

