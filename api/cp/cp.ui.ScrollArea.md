# [docs](index.md) » cp.ui.ScrollArea
---

Scroll Area Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [ScrollArea](#scrollarea)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [contentsUI](#contentsui)
 * [horizontalScrollBar](#horizontalscrollbar)
 * [selectedChildrenUI](#selectedchildrenui)
 * [verticalScrollBar](#verticalscrollbar)
 * [viewFrame](#viewframe)
* Methods - API calls which can only be made on an object returned by a constructor
 * [childrenUI](#childrenui)
 * [deselectAll](#deselectall)
 * [loadLayout](#loadlayout)
 * [saveLayout](#savelayout)
 * [selectAll](#selectall)
 * [selectChild](#selectchild)
 * [selectChildAt](#selectchildat)
 * [shiftHorizontalBy](#shifthorizontalby)
 * [shiftHorizontalTo](#shifthorizontalto)
 * [shiftVerticalBy](#shiftverticalby)
 * [shiftVerticalTo](#shiftverticalto)
 * [showChild](#showchild)
 * [showChildAt](#showchildat)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks to see if an element matches what we think it should be. |
| **Parameters**                                       | <ul><li>element - An <code>axuielementObject</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if matches otherwise <code>false</code></li></ul> |

### Constructors

#### [ScrollArea](#scrollarea)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea(parent, uiFinder) -> cp.ui.ScrollArea` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `ScrollArea`. |
| **Parameters**                                       | <ul><li>parent       - The parent object.</li><li>uiFinder     - A <code>function</code> or <code>cp.prop</code> which will return the <code>hs._asm.axuielement</code> when available.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>ScrollArea</code>.</li></ul> |

### Fields

#### [contentsUI](#contentsui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea.contentsUI <cp.prop: hs._asm.axuielement; read-only; live?>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns the `axuielement` representing the Scroll Area Contents, or `nil` if not available. |

#### [horizontalScrollBar](#horizontalscrollbar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea.horizontalScrollBar <cp.ui.ScrollBar>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The horizontal [ScrollBar](cp.ui.ScrollBar.md). |

#### [selectedChildrenUI](#selectedchildrenui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea.selectedChildrenUI <cp.prop: hs._asm.axuielement; read-only; live?>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns the `axuielement` representing the Scroll Area Selected Children, or `nil` if not available. |

#### [verticalScrollBar](#verticalscrollbar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea.verticalScrollBar <cp.ui.ScrollBar>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The vertical [ScrollBar](cp.ui.ScrollBar.md). |

#### [viewFrame](#viewframe)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea.viewFrame <cp.prop:hs.geometry.rect; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A `cp.prop` reporting the Scroll Area frame as a hs.geometry.rect. |

### Methods

#### [childrenUI](#childrenui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:childrenUI(filterFn) -> hs._asm.axuielement | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the `axuielement` representing the Scroll Area Contents, or `nil` if not available. |
| **Parameters**                                       | <ul><li>filterFn - The function which checks if the child matches the requirements.</li></ul> |

#### [deselectAll](#deselectall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:deselectAll() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Deselect all children in a scroll area. |
| **Parameters**                                       | <ul><li>None</li></ul> |

#### [loadLayout](#loadlayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:loadLayout(layout) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Loads a Scroll Area layout. |
| **Parameters**                                       | <ul><li>layout - A table containing the ScrollArea layout settings, typically created using <a href="#saveLayout">saveLayout</a>.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [saveLayout](#savelayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:saveLayout() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Saves the current Scroll Area layout to a table. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table containing the current Scroll Area Layout.</li></ul> |

#### [selectAll](#selectall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:selectAll(childrenUI) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Select all children in a scroll area. |
| **Parameters**                                       | <ul><li>childrenUI - A table of <code>hs._asm.axuielement</code> objects.</li></ul> |

#### [selectChild](#selectchild)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:selectChild(childUI) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Select a specific child within a Scroll Area. |
| **Parameters**                                       | <ul><li>childUI - The <code>hs._asm.axuielement</code> object of the child you want to select.</li></ul> |

#### [selectChildAt](#selectchildat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:selectChildAt(index) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Select a child element in a Scroll Area given a specific index. |
| **Parameters**                                       | <ul><li>index - The index of the child you want to select.</li></ul> |

#### [shiftHorizontalBy](#shifthorizontalby)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:shiftHorizontalBy(amount) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Attempts to shift the horizontal scroll bar by the specified amount. |
| **Parameters**                                       | <ul><li>amount - The amount to shift</li></ul> |
| **Returns**                                          | <ul><li>The actual value of the horizontal scroll bar.</li></ul> |

#### [shiftHorizontalTo](#shifthorizontalto)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:shiftHorizontalTo(value) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Attempts to shift the horizontal scroll bar to the specified value. |
| **Parameters**                                       | <ul><li>value - The new value (typically between <code>0</code> and <code>1</code>).</li></ul> |
| **Returns**                                          | <ul><li>The actual value of the horizontal scroll bar.</li></ul> |

#### [shiftVerticalBy](#shiftverticalby)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:shiftVerticalBy(amount) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Attempts to shift the vertical scroll bar by the specified amount. |
| **Parameters**                                       | <ul><li>amount - The amount to shift</li></ul> |
| **Returns**                                          | <ul><li>The actual value of the vertical scroll bar.</li></ul> |

#### [shiftVerticalTo](#shiftverticalto)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:shiftVerticalTo(value) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Attempts to shift the vertical scroll bar to the specified value. |
| **Parameters**                                       | <ul><li>value - The new value (typically between <code>0</code> and <code>1</code>).</li></ul> |
| **Returns**                                          | <ul><li>The actual value of the vertical scroll bar.</li></ul> |

#### [showChild](#showchild)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:showChild(childUI) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Show's a child element in a Scroll Area. |
| **Parameters**                                       | <ul><li>childUI - The <code>hs._asm.axuielement</code> object of the child you want to show.</li></ul> |

#### [showChildAt](#showchildat)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ScrollArea:showChildAt(index) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Show's a child element in a Scroll Area given a specific index. |
| **Parameters**                                       | <ul><li>index - The index of the child you want to show.</li></ul> |

