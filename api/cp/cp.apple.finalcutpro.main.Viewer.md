# [docs](index.md) » cp.apple.finalcutpro.main.Viewer
---

Viewer Module.

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [isEventViewer](#iseventviewer)
 * [isMainViewer](#ismainviewer)

## API Documentation

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Viewer.new(app, eventViewer) -> Viewer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `Viewer` instance.                                                                                         |
| **Parameters**                                       | <ul><li>* app           - The FCP application.</li><li>* eventViewer   - If `true`, the viewer is the Event Viewer.</li></ul> |
| **Returns**                                          | <ul><li>* The new `Viewer` instance.</li></ul>          |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Viewer:app() -> application` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the application.                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* The application.</li></ul>          |

#### [isEventViewer](#iseventviewer)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Viewer:isEventViewer() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns `true` if this is the Event Viewer.                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* `true` if this is the Event Viewer.</li></ul>          |

#### [isMainViewer](#ismainviewer)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Viewer:isMainViewer() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns `true` if this is the main Viewer.                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* `true` if this is the main Viewer.</li></ul>          |

