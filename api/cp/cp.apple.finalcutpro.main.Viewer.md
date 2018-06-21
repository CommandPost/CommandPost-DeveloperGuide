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
| **Parameters**                                       | <ul markdown="1"><li markdown="1">element - An `axuielementObject` to check.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`true` if matches otherwise `false`</li></ul>          |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Viewer.new(app, eventViewer) -> Viewer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `Viewer` instance.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* app           - The FCP application.</li><li markdown="1">* eventViewer   - If `true`, the viewer is the Event Viewer.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The new `Viewer` instance.</li></ul>          |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Viewer:app() -> application` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the application.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The application.</li></ul>          |

#### [currentWindow](#currentwindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Viewer:currentWindow() -> PrimaryWindow | SecondaryWindow` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the current window object.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The `PrimaryWindow` or the `SecondaryWindow`.</li></ul>          |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Viewer:hide() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides the Viewer.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* Self</li></ul>          |

#### [isEventViewer](#iseventviewer)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Viewer:isEventViewer() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns `true` if this is the Event Viewer.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* `true` if this is the Event Viewer.</li></ul>          |

#### [isMainViewer](#ismainviewer)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Viewer:isMainViewer() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns `true` if this is the main Viewer.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* `true` if this is the main Viewer.</li></ul>          |

#### [playButton](#playbutton)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Viewer:playButton() -> Button` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the Play Button object.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* A Button</li></ul>          |

#### [showOnPrimary](#showonprimary)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Viewer:showOnPrimary() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows the Viewer on the Primary display.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* Self</li></ul>          |

#### [showOnSecondary](#showonsecondary)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Viewer:showOnSecondary() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows the Viewer on the Seconary display.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* Self</li></ul>          |

