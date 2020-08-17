# [docs](index.md) » cp.blackmagic.resolve.main.PrimaryWindow
---

Primary Window Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [PrimaryWindow](#primarywindow)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [doShow](#doshow)
 * [resolve](#resolve)
* Methods - API calls which can only be made on an object returned by a constructor
 * [show](#show)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.blackmagic.resolve.main.PrimaryWindow.matches(w) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks to see if a window matches the PrimaryWindow requirements |
| **Parameters**                                       | <ul><li>w - The window to check</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if matched otherwise <code>false</code></li></ul> |

### Constructors

#### [PrimaryWindow](#primarywindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.blackmagic.resolve.main.PrimaryWindow(app) -> PrimaryWindow object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new PrimaryWindow. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>PrimaryWindow</li></ul> |

### Fields

#### [doShow](#doshow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.blackmagic.resolve.main.PrimaryWindow:doShow() -> PrimaryWindow` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that attempts to show the Primary Window. |
| **Returns**                                          | <ul><li>The <code>Statement</code>, which resolves as either <code>true</code> or sends an error.</li></ul> |

#### [resolve](#resolve)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.blackmagic.resolve.main.PrimaryWindow.resolve -> cp.blackmagic.resolve` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The main `Resolve` application root. |

### Methods

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.blackmagic.resolve.main.PrimaryWindow:show() -> PrimaryWindow` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Shows the Primary Window. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>PrimaryWindow</code> instance.</li></ul> |

