# [docs](index.md) » cp.ui.Element
---

A support class for `hs._asm.axuielement` management.

See:
* [Button](cp.ui.Button.md)
* [CheckBox](cp.rx.CheckBox.md)
* [MenuButton](cp.rx.MenuButton.md)

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [Element](#element)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [frame](#frame)
 * [identifier](#identifier)
 * [isEnabled](#isenabled)
 * [isShowing](#isshowing)
 * [position](#position)
 * [role](#role)
 * [size](#size)
 * [subrole](#subrole)
 * [textValue](#textvalue)
 * [title](#title)
 * [value](#value)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [doLayout](#dolayout)
 * [doShow](#doshow)
 * [focus](#focus)
 * [loadLayout](#loadlayout)
 * [parent](#parent)
 * [saveLayout](#savelayout)
 * [show](#show)
 * [snapshot](#snapshot)
 * [valueIs](#valueis)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Element.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Matches to any valid `hs._asm.axuielement`. Sub-types should provide their own `matches` method. |
| **Parameters**                                       | <ul><li>The element to check</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the element is a valid instance of an <code>hs._asm.axuielement</code>.</li></ul> |

### Constructors

#### [Element](#element)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Element(parent, uiFinder) -> cp.ui.Element` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `Element` with the specified `parent` and `uiFinder`. |
| **Parameters**                                       | <ul><li>parent - The parent Element (may be <code>nil</code>)</li><li>uiFinder - The <code>function</code> or <code>prop</code> that actually provides the current <code>axuielement</code> instance.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Element</code> instance.</li></ul> |

### Fields

#### [frame](#frame)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Element.frame <cp.prop: table; read-only; live?>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns the table containing the `x`, `y`, `w`, and `h` values for the `Element` frame, or `nil` if not available. |

#### [identifier](#identifier)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Element.identifier <cp.prop: string; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns the `AX` identifier for the element. |

#### [isEnabled](#isenabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Element.isEnabled <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns `true` if the `Element` is visible and enabled. |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Element.isShowing <cp.prop: boolean; read-only; live?>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | If `true`, the `Element` is showing on screen. |

#### [position](#position)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Element.position <cp.prop: table; read-only; live?>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns the table containing the `x` and `y` values for the `Element` frame, or `nil` if not available. |

#### [role](#role)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Element.role <cp.prop: string; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns the `AX` role name for the element. |

#### [size](#size)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Element.size <cp.prop: table; read-only; live?>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns the table containing the `w` and `h` values for the `Element` frame, or `nil` if not available. |

#### [subrole](#subrole)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Element.subrole <cp.prop: string; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns the `AX` subrole name for the element. |

#### [textValue](#textvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Element.textValue <cp.prop: string; read-only; live?>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The 'AXValue' of the element, if it is a `string`. |

#### [title](#title)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Element.title <cp.prop: string; read-only, live?>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The 'AXTitle' of the element. |

#### [value](#value)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Element.value <cp.prop: anything; live?>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The 'AXValue' of the element. |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Element:app() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the app instance. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>App</li></ul> |

#### [doLayout](#dolayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Element:doLayout(layout) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) which will attempt to load the layout based on the parameters |
| **Parameters**                                       | <ul><li>layout - a <code>table</code> of parameters that will be used to layout the element.</li></ul> |
| **Returns**                                          | <ul><li>The <a href="cp.rx.go.Statement.md">Statement</a> to execute.</li></ul> |
| **Notes**                                            | <ul><li>By default, to enable backwards-compatibility, this method will simply call the [#loadLayout]. Override it to provide more optimal asynchonous behaviour if required.</li><li>When subclassing, the overriding <code>doLayout</code> method should call the parent class's <code>doLayout</code> method,then process any custom values from it, like so:   <code>lua   function MyElement:doLayout(layout)       layout = layout or {}       return Do(Element.doLayout(self, layout))       :Then(function()           self.myConfig = layout.myConfig       end)       :Label("MyElement:doLayout")   end</code></li></ul> |

#### [doShow](#doshow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Element:doShow() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `Statement` that will ensure the Element is showing. |

#### [focus](#focus)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Element:focus() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Set the focus on an element. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>self</li></ul> |

#### [loadLayout](#loadlayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Element:loadLayout(layout) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | When called, the Element (or subclass) will attempt to load the layout based on the parameters |
| **Parameters**                                       | <ul><li>layout - a <code>table</code> of parameters that will be used to layout the element.</li></ul> |
| **Notes**                                            | <ul><li>When subclassing, the overriding <code>loadLayout</code> method should call the parent's <code>loadLayout</code> method,then process any custom values from it, like so:   <code>function MyElement:loadLayout(layout)       Element.loadLayout(self, layout)       self.myConfig = layout.myConfig   end</code></li></ul> |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Element:parent() -> parent` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the parent object. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>parent</li></ul> |

#### [saveLayout](#savelayout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Element:saveLayout() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a `table` containing the current configuration details for this Element (or subclass). |
| **Notes**                                            | <ul><li>When subclassing, the overriding <code>saveLayout</code> method should call the parent's saveLayout method,then add values to it, like so:   <code>function MyElement:saveLayout()       local layout = Element.saveLayout(self)       layout.myConfig = self.myConfig       return layout   end</code></li></ul> |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Element:show() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Shows the Element. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>self</li></ul> |

#### [snapshot](#snapshot)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Element:snapshot([path]) -> hs.image | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Takes a snapshot of the button in its current state as a PNG and returns it. |
| **Parameters**                                       | <ul><li>path     - (optional) The path to save the file. Should include the extension (should be <code>.png</code>).</li></ul> |

#### [valueIs](#valueis)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Element.valueIs(value) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Checks if the current value of this element is the provided value. |
| **Parameters**                                       | <ul><li>value - The value to compare to.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the current [#value] is equal to the provided <code>value</code>.</li></ul> |

