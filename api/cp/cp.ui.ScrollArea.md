# [docs](index.md) » cp.ui.ScrollArea
---

Scroll Area Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [childrenUI](#childrenui)
 * [contentsUI](#contentsui)
 * [deselectAll](#deselectall)
 * [horizontalScrollBarUI](#horizontalscrollbarui)
 * [isShowing](#isshowing)
 * [loadLayout](#loadlayout)
 * [parent](#parent)
 * [saveLayout](#savelayout)
 * [selectAll](#selectall)
 * [selectChild](#selectchild)
 * [selectChildAt](#selectchildat)
 * [selectedChildrenUI](#selectedchildrenui)
 * [showChild](#showchild)
 * [showChildAt](#showchildat)
 * [snapshot](#snapshot)
 * [UI](#ui)
 * [verticalScrollBarUI](#verticalscrollbarui)
 * [viewFrame](#viewframe)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if an element matches what we think it should be.                                                                                         |
| **Parameters**                                       |  * element - An `axuielementObject` to check.                                       |
| **Returns**                                          |  * `true` if matches otherwise `false`                                                |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea.new(parent, finderFn) -> cp.ui.ScrollArea` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `ScrollArea`.                                                                                         |
| **Parameters**                                       |  * parent		- The parent object. * finderFn		- A function which will return the `hs._asm.axuielement` when available.                                       |
| **Returns**                                          |  * The new `ScrollArea`.                                                |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:app() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the app instance representing Final Cut Pro.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * App                                                |

#### [childrenUI](#childrenui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:childrenUI(filterFn) -> hs._asm.axuielement | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `axuielement` representing the Scroll Area Contents, or `nil` if not available.                                                                                         |
| **Parameters**                                       |  * filterFn - The function which checks if the child matches the requirements.                                       |

#### [contentsUI](#contentsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:contentsUI() -> hs._asm.axuielement | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `axuielement` representing the Scroll Area Contents, or `nil` if not available.                                                                                         |
| **Parameters**                                       |  * None                                       |

#### [deselectAll](#deselectall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:deselectAll() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Deselect all children in a scroll area.                                                                                         |
| **Parameters**                                       |  * None                                       |

#### [horizontalScrollBarUI](#horizontalscrollbarui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:horizontalScrollBarUI() -> hs._asm.axuielement | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `axuielement` representing the Horizontal Scroll Bar, or `nil` if not available.                                                                                         |
| **Parameters**                                       |  * None                                       |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:isShowing() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Is the Scroll Area showing?                                                                                         |
| **Parameters**                                       |  * None                                       |

#### [loadLayout](#loadlayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:loadLayout(layout) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Loads a Scroll Area layout.                                                                                         |
| **Parameters**                                       |  * layout - A table containing the Browser layout settings - created using `cp.apple.finalcutpro.main.Browser:saveLayout()`.                                       |
| **Returns**                                          |  * None                                                |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:parent() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | The parent object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The parent object.                                                |

#### [saveLayout](#savelayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:saveLayout() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Saves the current Scroll Area layout to a table.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A table containing the current Scroll Area Layout.                                                |

#### [selectAll](#selectall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:selectAll(childrenUI) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Select all children in a scroll area.                                                                                         |
| **Parameters**                                       |  * childrenUI - A table of `hs._asm.axuielement` objects.                                       |

#### [selectChild](#selectchild)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:selectChild(childUI) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Select a specific child within a Scroll Area.                                                                                         |
| **Parameters**                                       |  * childUI - The `hs._asm.axuielement` object of the child you want to select.                                       |

#### [selectChildAt](#selectchildat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:selectChildAt(index) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Select a child element in a Scroll Area given a specific index.                                                                                         |
| **Parameters**                                       |  * index - The index of the child you want to select.                                       |

#### [selectedChildrenUI](#selectedchildrenui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:selectedChildrenUI() -> hs._asm.axuielement | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `axuielement` representing the Scroll Area Selected Children, or `nil` if not available.                                                                                         |
| **Parameters**                                       |  * None                                       |

#### [showChild](#showchild)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:showChild(childUI) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Show's a child element in a Scroll Area.                                                                                         |
| **Parameters**                                       |  * childUI - The `hs._asm.axuielement` object of the child you want to show.                                       |

#### [showChildAt](#showchildat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:showChildAt(index) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Show's a child element in a Scroll Area given a specific index.                                                                                         |
| **Parameters**                                       |  * index - The index of the child you want to show.                                       |

#### [snapshot](#snapshot)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:snapshot([path]) -> hs.image | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Takes a snapshot of the UI in its current state as a PNG and returns it.                                                                                         |
| **Parameters**                                       |  * path - (optional) The path to save the file. Should include the extension (should be `.png`).                                       |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:UI() -> hs._asm.axuielement | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `axuielement` representing the `ScrollArea`, or `nil` if not available.                                                                                         |
| **Parameters**                                       |  * None                                       |

#### [verticalScrollBarUI](#verticalscrollbarui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:verticalScrollBarUI() -> hs._asm.axuielement | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `axuielement` representing the Vertical Scroll Bar, or `nil` if not available.                                                                                         |
| **Parameters**                                       |  * None                                       |

#### [viewFrame](#viewframe)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:viewFrame() -> hs.geometry rect` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Scroll Area frame.                                                                                         |
| **Parameters**                                       |  * None                                       |

