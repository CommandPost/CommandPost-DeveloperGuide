# [docs](index.md) » cp.ui.StaticText
---

Static Text Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [clear](#clear)
 * [isEnabled](#isenabled)
 * [loadLayout](#loadlayout)
 * [new](#new)
 * [parent](#parent)
 * [saveLayout](#savelayout)
 * [snapshot](#snapshot)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.StaticText.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the element is a Static Text element.                                                                                         |
| **Parameters**                                       |  * element		- The `axuielement` to check.                                       |
| **Returns**                                          |  * If `true`, the element is a Static Text element.                                                |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.StaticText:app() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the app object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The app.                                                |

#### [clear](#clear)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.StaticText:clear() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Clears the value of a Static Text box.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * Self                                                |

#### [isEnabled](#isenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.StaticText:isEnabled() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Is the Static Text box enabled?                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `true` if enabled, otherwise `false`.                                                |

#### [loadLayout](#loadlayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.StaticText:loadLayout(layout) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Loads a Static Text layout.                                                                                         |
| **Parameters**                                       |  * layout - A table containing the Static Text layout settings - created using `cp.ui.StaticText:saveLayout()`.                                       |
| **Returns**                                          |  * None                                                |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.StaticText.new(parent, finderFn[, convertFn]) -> StaticText` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a new StaticText. They have a parent and a finder function.                                                                                         |
| **Parameters**                                       |  * parent	- The parent object. * finderFn	- The function will return the `axuielement` for the StaticText. * convertFn	- (optional) If provided, will be passed the `string` value when returning.                                       |
| **Returns**                                          |  * The new `StaticText`.                                                |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.StaticText:parent() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the parent object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The parent.                                                |

#### [saveLayout](#savelayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.StaticText:saveLayout() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Saves the current Static Text layout to a table.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A table containing the current Static Text Layout.                                                |

#### [snapshot](#snapshot)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.StaticText:snapshot([path]) -> hs.image | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Takes a snapshot of the UI in its current state as a PNG and returns it.                                                                                         |
| **Parameters**                                       |  * path		- (optional) The path to save the file. Should include the extension (should be `.png`).                                       |

