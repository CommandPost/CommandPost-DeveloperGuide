# [docs](index.md) » plugins.core.loupedeckctandlive.manager
---

Loupedeck CT & Loupedeck Live Manager Plugin.

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [callback](#callback)
 * [clearCache](#clearcache)
 * [getFlashDrivePath](#getflashdrivepath)
 * [refresh](#refresh)
 * [refreshItems](#refreshitems)
 * [reset](#reset)

## API Documentation

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.loupedeckctandlive.manager.new() -> Loupedeck` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new Loupedeck object. |
| **Parameters**                                       | <ul><li>deviceType - The device type defined in <code>hs.loupedeck.deviceTypes</code></li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |
| **Notes**                                            | <ul><li>The deviceType should be either <code>hs.loupedeck.deviceTypes.LIVE</code>   or <code>hs.loupedeck.deviceTypes.CT</code>.</li></ul> |

### Methods

#### [callback](#callback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.loupedeckctandlive.manager:callback(data) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The Loupedeck callback. |
| **Parameters**                                       | <ul><li>data - The callback data.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [clearCache](#clearcache)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.loupedeckctandlive.manager:clearCache() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Clears the cache. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [getFlashDrivePath](#getflashdrivepath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.loupedeckctandlive.manager:getFlashDrivePath() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the Loupedeck Flash Drive path. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The Loupedeck Flash Drive path as a string</li></ul> |

#### [refresh](#refresh)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.loupedeckctandlive.manager:refresh()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Refreshes the Loupedeck screens and LED buttons. |
| **Parameters**                                       | <ul><li>dueToAppChange - A optional boolean to specify whether the refresh is due to                    an application focus change.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [refreshItems](#refreshitems)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.loupedeckctandlive.manager:refreshItems() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Refreshes the items to either either local drive or the Loupedeck Flash Drive. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Self</li></ul> |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.loupedeckctandlive.manager:reset()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Resets the config back to the default layout. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

