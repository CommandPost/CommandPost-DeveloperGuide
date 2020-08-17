# [docs](index.md) » cp.ui.DisclosureTriangle
---

Disclosure Triangle UI Module.

This represents an `hs._asm.axuielement` with a `AXDisclosureTriangle` role.
It allows checking and modifying the `opened` status like so:

```lua
myButton:opened() == true			-- happens to be opened already
myButton:opened(false) == false	-- update to unopened.
myButton.opened:toggle() == true	-- toggled back to being opened.
```

You can also call instances of `DisclosureTriangle` as a function, which will return
the `opened` status:

```lua
myButton() == true			-- still true
myButton(false) == false	-- now false
```

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [DisclosureTriangle](#disclosuretriangle)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [opened](#opened)
 * [title](#title)
* Methods - API calls which can only be made on an object returned by a constructor
 * [click](#click)
 * [doClose](#doclose)
 * [doOpen](#doopen)
 * [doPress](#dopress)
 * [loadLayout](#loadlayout)
 * [press](#press)
 * [saveLayout](#savelayout)
 * [toggle](#toggle)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.DisclosureTriangle.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the provided `hs._asm.axuielement` is a DisclosureTriangle. |
| **Parameters**                                       | <ul><li>element      - The <code>axuielement</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if it's a match, or <code>false</code> if not.</li></ul> |

### Constructors

#### [DisclosureTriangle](#disclosuretriangle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.DisclosureTriangle(parent, uiFinder) -> cp.ui.DisclosureTriangle` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new DisclosureTriangle. |
| **Parameters**                                       | <ul><li>parent       - The parent object.</li><li>uiFinder     - A function which will return the <code>hs._asm.axuielement</code> when available.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>DisclosureTriangle</code>.</li></ul> |

### Fields

#### [opened](#opened)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.DisclosureTriangle.opened <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Indicates if the disclosure triangle is currently opened. |

#### [title](#title)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.DisclosureTriangle.title <cp.prop: string; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The button title, if available. |

### Methods

#### [click](#click)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.DisclosureTriangle:click() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Performs a single mouse click on the triangle. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>DisclosureTriangle</code> instance.</li></ul> |

#### [doClose](#doclose)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.DisclosureTriangle:doClose() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `Statement` that will ensure the `DisclosureTriangle` is unopened. |

#### [doOpen](#doopen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.DisclosureTriangle:doOpen() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `Statement` that will ensure the `DisclosureTriangle` is opened. |

#### [doPress](#dopress)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.DisclosureTriangle:doPress() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `Statement` that will press the button when executed, if available at the time. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code> which will press the button when executed.</li></ul> |

#### [loadLayout](#loadlayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.DisclosureTriangle:loadLayout(layout) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Applies the settings in the provided layout table. |
| **Parameters**                                       | <ul><li>layout       - The table containing layout settings. Usually created by the <code>saveLayout</code> method.</li></ul> |
| **Returns**                                          | <ul><li>nil</li></ul> |

#### [press](#press)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.DisclosureTriangle:press() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Attempts to press the button. May fail if the `UI` is not available. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <p>The <code>DisclosureTriangle</code> instance.</p> |

#### [saveLayout](#savelayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.DisclosureTriangle:saveLayout() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a table containing the layout settings. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A settings table.</li></ul> |

#### [toggle](#toggle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.DisclosureTriangle:toggle() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Toggles the `opened` status of the button. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>DisclosureTriangle</code> instance.</li></ul> |

