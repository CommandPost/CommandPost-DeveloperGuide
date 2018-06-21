# [docs](index.md) » cp.apple.finalcutpro.main.Viewer
---

Viewer Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [currentWindow](#currentwindow)
 * [hide](#hide)
 * [isEventViewer](#iseventviewer)
 * [isMainViewer](#ismainviewer)
 * [playButton](#playbutton)
 * [showOnPrimary](#showonprimary)
 * [showOnSecondary](#showonsecondary)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Viewer.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if an element matches what we think it should be.                                                                                         |
| **Parameters**                                       |  * element - An `axuielementObject` to check.                                       |
| **Returns**                                          |  * `true` if matches otherwise `false`                                                |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Viewer.new(app, eventViewer) -> Viewer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `Viewer` instance.                                                                                         |
| **Parameters**                                       | * app           - The FCP application.* eventViewer   - If `true`, the viewer is the Event Viewer.                                       |
| **Returns**                                          | * The new `Viewer` instance.                                                |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Viewer:app() -> application` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the application.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The application.                                                |

#### [currentWindow](#currentwindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Viewer:currentWindow() -> PrimaryWindow | SecondaryWindow` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the current window object.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The `PrimaryWindow` or the `SecondaryWindow`.                                                |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Viewer:hide() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides the Viewer.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * Self                                                |

#### [isEventViewer](#iseventviewer)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Viewer:isEventViewer() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns `true` if this is the Event Viewer.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * `true` if this is the Event Viewer.                                                |

#### [isMainViewer](#ismainviewer)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Viewer:isMainViewer() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns `true` if this is the main Viewer.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * `true` if this is the main Viewer.                                                |

#### [playButton](#playbutton)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Viewer:playButton() -> Button` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the Play Button object.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * A Button                                                |

#### [showOnPrimary](#showonprimary)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Viewer:showOnPrimary() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows the Viewer on the Primary display.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * Self                                                |

#### [showOnSecondary](#showonsecondary)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Viewer:showOnSecondary() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows the Viewer on the Seconary display.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * Self                                                |

