# [docs](index.md) » hs.application.watcher
---

Watch for application launch/terminate events

This module is based primarily on code from the previous incarnation of Mjolnir by [Markus Engelbrecht](https://github.com/mgee) and [Steven Degutis](https://github.com/sdegutis/).

## API Overview
* Constants - Useful values which cannot be changed
 * [activated](#activated)
 * [deactivated](#deactivated)
 * [hidden](#hidden)
 * [launched](#launched)
 * [launching](#launching)
 * [terminated](#terminated)
 * [unhidden](#unhidden)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [start](#start)
 * [stop](#stop)

## API Documentation

### Constants

#### [activated](#activated)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application.watcher.activated` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | An application has been activated (i.e. given keyboard/mouse focus)                                                                                         |

#### [deactivated](#deactivated)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application.watcher.deactivated` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | An application has been deactivated (i.e. lost keyboard/mouse focus)                                                                                         |

#### [hidden](#hidden)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application.watcher.hidden` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | An application has been hidden                                                                                         |

#### [launched](#launched)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application.watcher.launched` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | An application has been launched                                                                                         |

#### [launching](#launching)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application.watcher.launching` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | An application is in the process of being launched                                                                                         |

#### [terminated](#terminated)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application.watcher.terminated` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | An application has been terminated                                                                                         |

#### [unhidden](#unhidden)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application.watcher.unhidden` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | An application has been unhidden                                                                                         |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application.watcher.new(fn) -> watcher` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates an application event watcher                                                                                         |
| **Parameters**                                       |  * fn - A function that will be called when application events happen. It should accept three parameters:  * A string containing the name of the application  * An event type (see the constants defined above)  * An `hs.application` object representing the application, or nil if the application couldn't be found                                       |
| **Returns**                                          |  * An `hs.application.watcher` object                                                |
| **Notes**                                            |  * If the function is called with an event type of `hs.application.watcher.terminated` then the application name parameter will be `nil` and the `hs.application` parameter, will only be useful for getting the UNIX process ID (i.e. the PID) of the application                                                      |

### Methods

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application.watcher:start()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Starts the application watcher                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `hs.application.watcher` object                                                |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.application.watcher:stop()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Stops the application watcher                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `hs.application.watcher` object                                                |

