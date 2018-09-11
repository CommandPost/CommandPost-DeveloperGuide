# [docs](index.md) » cp.ui.Button
---

The `Button` type extends [Element](cp.ui.Element.md) and includes all its
methods, fields and other properties.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [Button](#button)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [title](#title)
* Methods - API calls which can only be made on an object returned by a constructor
 * [doPress](#dopress)
 * [press](#press)

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

#### [Button](#button)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Button(parent, uiFinder) -> cp.ui.Button` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `Button` instance. |
| **Parameters**                                       | <ul><li>parent       - The parent object. Should have a <code>UI</code> and <code>isShowing</code> field.</li><li>uiFinder     - A function which will return the <code>hs._asm.axuielement</code> the button belongs to, or <code>nil</code> if not available.</li></ul> |
| **Returns**                                          | <p>The new <code>Button</code> instance.</p> |

### Fields

#### [title](#title)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Button.title <cp.prop: string; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The button title, if available. |

### Methods

#### [doPress](#dopress)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Button:doPress() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `Statement` that will press the button when executed, if available at the time. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code> which will press the button when executed.</li></ul> |

#### [press](#press)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Button:press() -> self, boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Performs a button press action, if the button is available. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Button</code> instance.</li><li><code>true</code> if the button was actually pressed successfully.</li></ul> |

