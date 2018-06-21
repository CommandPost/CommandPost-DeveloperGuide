# [docs](index.md) » plugins.core.webapp
---

WebApp Plugin.

## API Overview
* Constants - Useful values which cannot be changed
 * [DEFAULT_PORT](#default_port)
 * [DEFAULT_SETTING](#default_setting)
 * [PREFERENCE_NAME](#preference_name)
* Functions - API calls offered directly by the extension
 * [copyLinkToPasteboard](#copylinktopasteboard)
 * [start](#start)
 * [stop](#stop)
 * [update](#update)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [enabled](#enabled)

## API Documentation

### Constants

#### [DEFAULT_PORT](#default_port)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.webapp.DEFAULT_PORT -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The Default Port.                                                                                         |

#### [DEFAULT_SETTING](#default_setting)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.webapp.DEFAULT_SETTING -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Whether or not the WebApp should be enabled by default.                                                                                         |

#### [PREFERENCE_NAME](#preference_name)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.webapp.PREFERENCE_NAME -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The Preference Name                                                                                         |

### Functions

#### [copyLinkToPasteboard](#copylinktopasteboard)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.webapp.copyLinkToPasteboard() -> None` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Copies the Hostname to the Pasteboard.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.webapp.start() -> WebApp` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Starts the WebApp.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The WebApp object.                                                |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.webapp.stop() -> WebApp` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Stops the WebApp.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The WebApp object.                                                |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.webapp.update() -> None` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Starts or Stops the WebApp.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

### Fields

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.webapp.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Is `true` if the plugin is enabled.                                                                                         |

