# [docs](index.md) » plugins.core.streamdeck.manager
---

Elgato Stream Deck Manager Plugin.

## API Overview
* Variables - Configurable values
 * [defaultLayout](#defaultlayout)
* Functions - API calls offered directly by the extension
 * [buttonCallback](#buttoncallback)
 * [discoveryCallback](#discoverycallback)
 * [getDeviceType](#getdevicetype)
 * [start](#start)
 * [update](#update)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [activeBanks](#activebanks)
 * [enabled](#enabled)
 * [items](#items)

## API Documentation

### Variables

#### [defaultLayout](#defaultlayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.defaultLayout -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Default Stream Deck Layout |

### Functions

#### [buttonCallback](#buttoncallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.buttonCallback(object, buttonID, pressed) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Stream Deck Button Callback |
| **Parameters**                                       | <ul><li>object - The <code>hs.streamdeck</code> userdata object</li><li>buttonID - A number containing the button that was pressed/released</li><li>pressed - A boolean indicating whether the button was pressed (<code>true</code>) or released (<code>false</code>)</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [discoveryCallback](#discoverycallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.discoveryCallback(connected, object) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Stream Deck Discovery Callback |
| **Parameters**                                       | <ul><li>connected - A boolean, <code>true</code> if a device was connected, <code>false</code> if a device was disconnected</li><li>object - An <code>hs.streamdeck</code> object, being the device that was connected/disconnected</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [getDeviceType](#getdevicetype)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.getDeviceType(object) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Translates a Stream Deck button layout into a device type string. |
| **Parameters**                                       | <ul><li>object - A <code>hs.streamdeck</code> object</li></ul> |
| **Returns**                                          | <ul><li>"Mini", "Original" or "XL"</li></ul> |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.start() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Stops the Stream Deck Plugin |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.update() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Updates the screens of all Stream Deck devices. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

### Fields

#### [activeBanks](#activebanks)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.activeBanks <cp.prop: table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Table of active banks for each application. |

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Enable or disable Stream Deck Support. |

#### [items](#items)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.streamdeck.manager.items <cp.prop: table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Contains all the saved Stream Deck Buttons |

