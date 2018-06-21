# [docs](index.md) » cp.ui.SplitGroup
---

Split Group UI.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [parent](#parent)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.SplitGroup.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if an element matches what we think it should be.                                                                                         |
| **Parameters**                                       |  * element - An `axuielementObject` to check.                                       |
| **Returns**                                          |  * `true` if matches otherwise `false`                                                |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.SplitGroup.new(parent, finderFn) -> cp.ui.SplitGroup` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new Split Group.                                                                                         |
| **Parameters**                                       |  * parent		- The parent object. * finderFn		- The function which returns an `hs._asm.axuielement` for the Split Group, or `nil`.                                       |
| **Returns**                                          |  * A new `SplitGroup` instance.                                                |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.SplitGroup:app() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the app instance.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * App                                                |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.SplitGroup:parent() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | The parent object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The parent object.                                                |

