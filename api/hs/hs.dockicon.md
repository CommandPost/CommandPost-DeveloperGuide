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
 * [tileCanvas](#tilecanvas)
 * [tileSize](#tilesize)
 * [tileUpdate](#tileupdate)
 * [visible](#visible)

## API Documentation

### Functions

#### [bounce](#bounce)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.dockicon.bounce(indefinitely)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Bounce Hammerspoon's dock icon |
| **Parameters**                                       | <ul><li>indefinitely - A boolean value, true if the dock icon should bounce until the dock icon is clicked, false if the dock icon should only bounce briefly</li></ul> |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.dockicon.hide()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Hide Hammerspoon's dock icon |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [setBadge](#setbadge)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.dockicon.setBadge(badge)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Set Hammerspoon's dock icon badge |
| **Parameters**                                       | <ul><li>badge - A string containing the label to place inside the dock icon badge. If the string is empty, the badge will be cleared</li></ul> |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.dockicon.show()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Make Hammerspoon's dock icon visible |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [tileCanvas](#tilecanvas)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.dockicon.tileCanvas([canvas]) -> canvasObject | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Get or set a canvas object to be displayed as the Hamemrspoon dock icon |
| **Parameters**                                       | <ul><li><code>canvas</code> - an optional <code>hs.canvas</code> object specifying the canvas to be displayed as the dock icon for Hammerspoon. If an explicit <code>nil</code> is specified, the dock icon will revert to the Hammerspoon application icon.</li></ul> |
| **Returns**                                          | <ul><li>If the dock icon is assigned a canvas object, that canvas object will be returned, otherwise returns nil.</li></ul> |
| **Notes**                                            | <ul><li>If you update the canvas object by changing any of its components, it will not be reflected in the dock icon until you invoke <a href="#tileUpdate">hs.dockicon.tileUpdate</a>.</li></ul> |

#### [tileSize](#tilesize)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.dockicon.tileSize() -> size table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a table containing the size of the tile representing the dock icon. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a table containing the size of the tile representing the dock icon for Hammerspoon. This table will contain <code>h</code> and <code>w</code> keys specifying the tile height and width as numbers.</li></ul> |
| **Notes**                                            | <ul><li>the size returned specifies the display size of the dock icon tile. If your canvas item is larger than this, then only the top left portion corresponding to the size returned will be displayed.</li></ul> |

#### [tileUpdate](#tileupdate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.dockicon.tileUpdate() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Force an update of the dock icon. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |
| **Notes**                                            | <ul><li>Changes made to a canvas object are not reflected automatically like they are when a canvas is being displayed on the screen; you must invoke this method after making changes to the canvas for the updates to be reflected in the dock icon.</li></ul> |

#### [visible](#visible)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.dockicon.visible() -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Determine whether Hammerspoon's dock icon is visible |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A boolean, true if the dock icon is visible, false if not</li></ul> |

