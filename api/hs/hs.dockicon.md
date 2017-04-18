# [docs](index.md) » hs.dockicon
---

Control Hammerspoon's dock icon

This module is based primarily on code from the previous incarnation of Mjolnir by [Steven Degutis](https://github.com/sdegutis/).

## API Overview
* Functions - API calls offered directly by the extension
 * [bounce](#bounce)
 * [hide](#hide)
 * [setBadge](#setBadge)
 * [show](#show)
 * [visible](#visible)

## API Documentation

### Functions

#### [bounce](#bounce)
| **Signature**                               | `hs.dockicon.bounce(indefinitely)`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Function                                                                     |
| **Description**                             | Bounce Hammerspoon's dock icon                                                                     |
| **Parameters**                              | <ul><li>indefinitely - A boolean value, true if the dock icon should bounce until the dock icon is clicked, false if the dock icon should only bounce briefly</li></ul> |

#### [hide](#hide)
| **Signature**                               | `hs.dockicon.hide()`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Function                                                                     |
| **Description**                             | Hide Hammerspoon's dock icon                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |

#### [setBadge](#setBadge)
| **Signature**                               | `hs.dockicon.setBadge(badge)`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Function                                                                     |
| **Description**                             | Set Hammerspoon's dock icon badge                                                                     |
| **Parameters**                              | <ul><li>badge - A string containing the label to place inside the dock icon badge. If the string is empty, the badge will be cleared</li></ul> |

#### [show](#show)
| **Signature**                               | `hs.dockicon.show()`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Function                                                                     |
| **Description**                             | Make Hammerspoon's dock icon visible                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |

#### [visible](#visible)
| **Signature**                               | `hs.dockicon.visible() -> bool`                                                                    |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Type**                                    | Function                                                                     |
| **Description**                             | Determine whether Hammerspoon's dock icon is visible                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A boolean, true if the dock icon is visible, false if not</li></ul>          |

