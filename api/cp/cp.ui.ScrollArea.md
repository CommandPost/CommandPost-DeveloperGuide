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
| **Parameters**                                       | <ul markdown="1"><li markdown="1">element - An `axuielementObject` to check.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`true` if matches otherwise `false`</li></ul>          |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea.new(parent, finderFn) -> cp.ui.ScrollArea` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `ScrollArea`.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">parent		- The parent object.</li><li markdown="1">finderFn		- A function which will return the `hs._asm.axuielement` when available.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The new `ScrollArea`.</li></ul>          |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:app() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the app instance representing Final Cut Pro.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">App</li></ul>          |

#### [childrenUI](#childrenui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:childrenUI(filterFn) -> hs._asm.axuielement | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `axuielement` representing the Scroll Area Contents, or `nil` if not available.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">filterFn - The function which checks if the child matches the requirements.</li></ul> |

#### [contentsUI](#contentsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:contentsUI() -> hs._asm.axuielement | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `axuielement` representing the Scroll Area Contents, or `nil` if not available.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |

#### [deselectAll](#deselectall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:deselectAll() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Deselect all children in a scroll area.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |

#### [horizontalScrollBarUI](#horizontalscrollbarui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:horizontalScrollBarUI() -> hs._asm.axuielement | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `axuielement` representing the Horizontal Scroll Bar, or `nil` if not available.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:isShowing() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Is the Scroll Area showing?                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |

#### [loadLayout](#loadlayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:loadLayout(layout) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Loads a Scroll Area layout.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">layout - A table containing the Browser layout settings - created using `cp.apple.finalcutpro.main.Browser:saveLayout()`.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:parent() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | The parent object.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The parent object.</li></ul>          |

#### [saveLayout](#savelayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:saveLayout() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Saves the current Scroll Area layout to a table.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A table containing the current Scroll Area Layout.</li></ul>          |

#### [selectAll](#selectall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:selectAll(childrenUI) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Select all children in a scroll area.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">childrenUI - A table of `hs._asm.axuielement` objects.</li></ul> |

#### [selectChild](#selectchild)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:selectChild(childUI) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Select a specific child within a Scroll Area.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">childUI - The `hs._asm.axuielement` object of the child you want to select.</li></ul> |

#### [selectChildAt](#selectchildat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:selectChildAt(index) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Select a child element in a Scroll Area given a specific index.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">index - The index of the child you want to select.</li></ul> |

#### [selectedChildrenUI](#selectedchildrenui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:selectedChildrenUI() -> hs._asm.axuielement | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `axuielement` representing the Scroll Area Selected Children, or `nil` if not available.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |

#### [showChild](#showchild)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:showChild(childUI) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Show's a child element in a Scroll Area.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">childUI - The `hs._asm.axuielement` object of the child you want to show.</li></ul> |

#### [showChildAt](#showchildat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:showChildAt(index) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Show's a child element in a Scroll Area given a specific index.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">index - The index of the child you want to show.</li></ul> |

#### [snapshot](#snapshot)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:snapshot([path]) -> hs.image | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Takes a snapshot of the UI in its current state as a PNG and returns it.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">path - (optional) The path to save the file. Should include the extension (should be `.png`).</li></ul> |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:UI() -> hs._asm.axuielement | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `axuielement` representing the `ScrollArea`, or `nil` if not available.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |

#### [verticalScrollBarUI](#verticalscrollbarui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:verticalScrollBarUI() -> hs._asm.axuielement | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `axuielement` representing the Vertical Scroll Bar, or `nil` if not available.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |

#### [viewFrame](#viewframe)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:viewFrame() -> hs.geometry rect` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Scroll Area frame.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |

