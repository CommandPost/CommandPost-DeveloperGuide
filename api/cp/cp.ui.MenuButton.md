# [docs](index.md) » cp.ui.MenuButton
---

Pop Up Button Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [getTitle](#gettitle)
 * [getValue](#getvalue)
 * [isEnabled](#isenabled)
 * [loadLayout](#loadlayout)
 * [parent](#parent)
 * [press](#press)
 * [saveLayout](#savelayout)
 * [selectItem](#selectitem)
 * [selectItemMatching](#selectitemmatching)
 * [setValue](#setvalue)
 * [show](#show)
 * [snapshot](#snapshot)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.MenuButton.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if an element matches what we think it should be.                                                                                         |
| **Parameters**                                       |  * element - An `axuielementObject` to check.                                       |
| **Returns**                                          |  * `true` if matches otherwise `false`                                                |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.MenuButton.new(parent, finderFn) -> MenuButton` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new MenuButton.                                                                                         |
| **Parameters**                                       | * parent		- The parent object. Should have an `isShowing` property.* finderFn		- A `cp.prop` or function which will return a `hs._asm.axuielement`, or `nil` if it's not available.                                       |

### Methods

#### [getTitle](#gettitle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.MenuButton:getTitle() -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the `MenuButton` title.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `MenuButton` title as string, or `nil` if the title cannot be determined.                                                |

#### [getValue](#getvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.MenuButton:getValue() -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the `MenuButton` value.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `MenuButton` value as string, or `nil` if the value cannot be determined.                                                |

#### [isEnabled](#isenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.MenuButton:isEnabled() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Is the `MenuButton` enabled?                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `true` if enabled otherwise `false`.                                                |

#### [loadLayout](#loadlayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.MenuButton:loadLayout(layout) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Loads a `MenuButton` layout.                                                                                         |
| **Parameters**                                       |  * layout - A table containing the `MenuButton` layout settings - created using `cp.ui.MenuButton:saveLayout()`.                                       |
| **Returns**                                          |  * None                                                |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.MenuButton:parent() -> parent` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the parent object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * parent                                                |

#### [press](#press)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.MenuButton:press() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Presses the MenuButton.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * self                                                |

#### [saveLayout](#savelayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.MenuButton:saveLayout() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Saves the current `MenuButton` layout to a table.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A table containing the current `MenuButton` Layout.                                                |

#### [selectItem](#selectitem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.MenuButton:selectItem(index) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Select an item on the `MenuButton` by index.                                                                                         |
| **Parameters**                                       |  * index - The index of the item you want to select.                                       |
| **Returns**                                          |  * `true` if successfully selected, otherwise `false`.                                                |

#### [selectItemMatching](#selectitemmatching)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.MenuButton:selectItemMatching(pattern) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Select an item on the `MenuButton` by pattern.                                                                                         |
| **Parameters**                                       |  * pattern - A pattern used to select the `MenuButton` item.                                       |
| **Returns**                                          |  * `true` if successfully selected, otherwise `false`.                                                |

#### [setValue](#setvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.MenuButton:setValue(value) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the `MenuButton` value.                                                                                         |
| **Parameters**                                       |  * value - The value you want to set the `MenuButton` to.                                       |
| **Returns**                                          |  * self                                                |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.MenuButton:show() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Show's the MenuButton.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * self                                                |

#### [snapshot](#snapshot)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.MenuButton:snapshot([path]) -> hs.image | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Takes a snapshot of the UI in its current state as a PNG and returns it.                                                                                         |
| **Parameters**                                       | * path		- (optional) The path to save the file. Should include the extension (should be `.png`).                                       |

