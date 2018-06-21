# [docs](index.md) » cp.ui.Button
---

Button Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [frame](#frame)
 * [isShowing](#isshowing)
 * [title](#title)
 * [UI](#ui)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [isEnabled](#isenabled)
 * [parent](#parent)
 * [press](#press)
 * [snapshot](#snapshot)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Button.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the `element` is a `Button`, returning `true` if so.                                                                                         |
| **Parameters**                                       |  * element		- The `hs._asm.axuielement` to check.                                       |
| **Returns**                                          |  * `true` if the `element` is a `Button`, or `false` if not.                                                |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Button.new(parent, finderFn) -> cp.ui.Button` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `Button` instance.                                                                                         |
| **Parameters**                                       |  * parent		- The parent object. Should have a `UI` and `isShowing` field. * finderFn		- A function which will return the `hs._asm.axuielement` the button belongs to, or `nil` if not available.                                       |
| **Returns**                                          | The new `Button` instance.                                                |

### Fields

#### [frame](#frame)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Button.frame <cp.prop: table; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns the table containing the `x`, `y`, `w`, and `h` values for the button frame, or `nil` if not available.                                                                                         |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Button.isShowing <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | If `true`, the `Button` is showing on screen.                                                                                         |

#### [title](#title)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Button.title <cp.prop: string; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The button title, if available.                                                                                         |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Button.UI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Retrieves the `axuielement` for the `Button`, or `nil` if not available..                                                                                         |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Button:app() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the app instance.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * App                                                |

#### [isEnabled](#isenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Button:isEnabled() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns `true` if the button is visible and enabled.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `true` if the button is visible and enabled.                                                |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Button:parent() -> parent` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the parent object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * parent                                                |

#### [press](#press)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Button:press() -> self, boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Performs a button press action, if the button is available.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `Button` instance. * `true` if the button was actually pressed successfully.                                                |

#### [snapshot](#snapshot)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Button:snapshot([path]) -> hs.image | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Takes a snapshot of the button in its current state as a PNG and returns it.                                                                                         |
| **Parameters**                                       |  * path		- (optional) The path to save the file. Should include the extension (should be `.png`).                                       |

