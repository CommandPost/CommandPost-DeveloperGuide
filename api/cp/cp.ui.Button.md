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
 * [doPress](#dopress)
 * [isEnabled](#isenabled)
 * [parent](#parent)
 * [press](#press)
 * [snapshot](#snapshot)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Button.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the `element` is a `Button`, returning `true` if so. |
| **Parameters**                                       | <ul><li>element      - The <code>hs._asm.axuielement</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the <code>element</code> is a <code>Button</code>, or <code>false</code> if not.</li></ul> |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Button.new(parent, finderFn) -> cp.ui.Button` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `Button` instance. |
| **Parameters**                                       | <ul><li>parent       - The parent object. Should have a <code>UI</code> and <code>isShowing</code> field. * finderFn       - A function which will return the <code>hs._asm.axuielement</code> the button belongs to, or <code>nil</code> if not available.</li></ul> |
| **Returns**                                          | <p>The new <code>Button</code> instance.</p> |

### Fields

#### [frame](#frame)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Button.frame <cp.prop: table; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns the table containing the `x`, `y`, `w`, and `h` values for the button frame, or `nil` if not available. |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Button.isShowing <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | If `true`, the `Button` is showing on screen. |

#### [title](#title)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Button.title <cp.prop: string; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The button title, if available. |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Button.UI <cp.prop: hs._asm.axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Retrieves the `axuielement` for the `Button`, or `nil` if not available.. |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Button:app() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the app instance. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>App</li></ul> |

#### [doPress](#dopress)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Button:doPress() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `Statement` that will press the button when executed, if available at the time. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code> which will press the button when executed.</li></ul> |

#### [isEnabled](#isenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Button:isEnabled() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns `true` if the button is visible and enabled. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the button is visible and enabled.</li></ul> |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Button:parent() -> parent` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the parent object. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>parent</li></ul> |

#### [press](#press)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Button:press() -> self, boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Performs a button press action, if the button is available. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Button</code> instance. * <code>true</code> if the button was actually pressed successfully.</li></ul> |

#### [snapshot](#snapshot)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Button:snapshot([path]) -> hs.image | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Takes a snapshot of the button in its current state as a PNG and returns it. |
| **Parameters**                                       | <ul><li>path     - (optional) The path to save the file. Should include the extension (should be <code>.png</code>).</li></ul> |

