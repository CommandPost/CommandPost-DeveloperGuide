# [docs](index.md) » hs.caffeinate.watcher
---

Watch for display and system sleep/wake/power events
and for fast user switching session events.

This module is based primarily on code from the previous incarnation of Mjolnir by [Steven Degutis](https://github.com/sdegutis/).

## API Overview
* Constants - Useful values which cannot be changed
 * [screensaverDidStart](#screensaverdidstart)
 * [screensaverDidStop](#screensaverdidstop)
 * [screensaverWillStop](#screensaverwillstop)
 * [screensDidLock](#screensdidlock)
 * [screensDidSleep](#screensdidsleep)
 * [screensDidUnlock](#screensdidunlock)
 * [screensDidWake](#screensdidwake)
 * [sessionDidBecomeActive](#sessiondidbecomeactive)
 * [sessionDidResignActive](#sessiondidresignactive)
 * [systemDidWake](#systemdidwake)
 * [systemWillPowerOff](#systemwillpoweroff)
 * [systemWillSleep](#systemwillsleep)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [start](#start)
 * [stop](#stop)

## API Documentation

### Constants

#### [screensaverDidStart](#screensaverdidstart)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.caffeinate.watcher.screensaverDidStart` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The screensaver started                                                                                         |

#### [screensaverDidStop](#screensaverdidstop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.caffeinate.watcher.screensaverDidStop` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The screensaver stopped                                                                                         |

#### [screensaverWillStop](#screensaverwillstop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.caffeinate.watcher.screensaverWillStop` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The screensaver is about to stop                                                                                         |

#### [screensDidLock](#screensdidlock)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.caffeinate.watcher.screensDidLock` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The screen was locked                                                                                         |

#### [screensDidSleep](#screensdidsleep)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.caffeinate.watcher.screensDidSleep` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The displays have gone to sleep                                                                                         |

#### [screensDidUnlock](#screensdidunlock)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.caffeinate.watcher.screensDidUnlock` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The screen was unlocked                                                                                         |

#### [screensDidWake](#screensdidwake)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.caffeinate.watcher.screensDidWake` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The displays have woken from sleep                                                                                         |

#### [sessionDidBecomeActive](#sessiondidbecomeactive)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.caffeinate.watcher.sessionDidBecomeActive` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The session became active, due to fast user switching                                                                                         |

#### [sessionDidResignActive](#sessiondidresignactive)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.caffeinate.watcher.sessionDidResignActive` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The session is no longer active, due to fast user switching                                                                                         |

#### [systemDidWake](#systemdidwake)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.caffeinate.watcher.systemDidWake` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The system woke from sleep                                                                                         |

#### [systemWillPowerOff](#systemwillpoweroff)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.caffeinate.watcher.systemWillPowerOff` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The user requested a logout or shutdown                                                                                         |

#### [systemWillSleep](#systemwillsleep)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.caffeinate.watcher.systemWillSleep` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The system is preparing to sleep                                                                                         |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.caffeinate.watcher.new(fn) -> watcher` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a watcher object for system and display sleep/wake/power events                                                                                         |
| **Parameters**                                       | <ul><li>fn - A function that will be called when system/display events happen. It should accept one parameter:</li></ul><ul><li>An event type (see the constants defined above)</li></ul>   |
| **Returns**                                          | <ul><li>An <code>hs.caffeinate.watcher</code> object</li></ul>            |

### Methods

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.caffeinate.watcher:start()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Starts the sleep/wake watcher                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>An <code>hs.caffeinate.watcher</code> object</li></ul>            |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.caffeinate.watcher:stop()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Stops the sleep/wake watcher                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>An <code>hs.caffeinate.watcher</code> object</li></ul>            |

