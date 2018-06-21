# [docs](index.md) » hs.dockicon
---

Control Hammerspoon's dock icon

This module is based primarily on code from the previous incarnation of Mjolnir by [Steven Degutis](https://github.com/sdegutis/).

## API Overview
* Functions - API calls offered directly by the extension
 * [bounce](#bounce)
 * [hide](#hide)
 * [setBadge](#setbadge)
 * [show](#show)
 * [visible](#visible)

## API Documentation

### Functions

#### [bounce](#bounce)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.dockicon.bounce(indefinitely)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Bounce Hammerspoon's dock icon                                                                                         |
| **Parameters**                                       |  * indefinitely - A boolean value, true if the dock icon should bounce until the dock icon is clicked, false if the dock icon should only bounce briefly                                       |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.dockicon.hide()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Hide Hammerspoon's dock icon                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [setBadge](#setbadge)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.dockicon.setBadge(badge)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Set Hammerspoon's dock icon badge                                                                                         |
| **Parameters**                                       |  * badge - A string containing the label to place inside the dock icon badge. If the string is empty, the badge will be cleared                                       |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.dockicon.show()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Make Hammerspoon's dock icon visible                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [visible](#visible)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.dockicon.visible() -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Determine whether Hammerspoon's dock icon is visible                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A boolean, true if the dock icon is visible, false if not                                                |

