# [docs](index.md) » cp.apple.finalcutpro.import.MediaImport
---

Media Import

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [frame](#frame)
 * [hsWindow](#hswindow)
 * [isFullScreen](#isfullscreen)
 * [isShowing](#isshowing)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [getTitle](#gettitle)
 * [hide](#hide)
 * [show](#show)
 * [UI](#ui)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.import.MediaImport.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if an element matches what we think it should be.                                                                                         |
| **Parameters**                                       |  * element - An `axuielementObject` to check.                                       |
| **Returns**                                          |  * `true` if matches otherwise `false`                                                |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.import.MediaImport.new(app) -> MediaImport` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new Media Import object.                                                                                         |
| **Parameters**                                       |  * app - The `cp.apple.finalcutpro` object.                                       |
| **Returns**                                          |  * A new MediaImport object.                                                |

### Fields

#### [frame](#frame)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.import.MediaImport.frame <cp.prop: frame>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The current position (x, y, width, height) of the window.                                                                                         |

#### [hsWindow](#hswindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.import.MediaImport.hsWindow <cp.prop: hs.window; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The `hs.window` instance for the window, or `nil` if it can't be found.                                                                                         |

#### [isFullScreen](#isfullscreen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.import.MediaImport.isFullScreen <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Is `true` if the window is full-screen.                                                                                         |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.import.MediaImport.isShowing <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Is `true` if the window is visible.                                                                                         |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.import.MediaImport:app() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the App instance representing Final Cut Pro.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * App                                                |

#### [getTitle](#gettitle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.import.MediaImport:getTitle() -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | The title of the Media Import window or `nil`.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The title of the Media Import window as a string or `nil`.                                                |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.import.MediaImport:hide() -> cp.apple.finalcutpro.import.MediaImport` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides the Media Import window.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `cp.apple.finalcutpro.import.MediaImport` object for method chaining.                                                |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.import.MediaImport:show() -> cp.apple.finalcutpro.import.MediaImport` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Triggers the Import All button.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `cp.apple.finalcutpro.import.MediaImport` object for method chaining.                                                |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.import.MediaImport:UI() -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Media Import Accessibility Object                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * An `axuielementObject` or `nil`                                                |

