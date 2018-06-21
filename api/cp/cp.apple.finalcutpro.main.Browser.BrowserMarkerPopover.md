# [docs](index.md) » cp.apple.finalcutpro.main.Browser.BrowserMarkerPopover
---

Browser Marker Popup.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [isShowing](#isshowing)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [chapter](#chapter)
 * [completed](#completed)
 * [delete](#delete)
 * [done](#done)
 * [hide](#hide)
 * [name](#name)
 * [parent](#parent)
 * [show](#show)
 * [standard](#standard)
 * [toDo](#todo)
 * [UI](#ui)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser.BrowserMarkerPopover.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if a GUI element is the Browser Marker Popover or not                                                                                         |
| **Parameters**                                       |  * element - The element you want to check                                       |
| **Returns**                                          |  * `true` if the `element` is the Browser Marker Popover otherwise `false`                                                |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser.BrowserMarkerPopover.new(parent) -> BrowserMarkerPopover` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Constructs a new Browser Marker Popover                                                                                         |
| **Parameters**                                       | * parent - The parent object                                       |
| **Returns**                                          | * The new `BrowserMarkerPopover` instance.                                                |

### Fields

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser.BrowserMarkerPopover.isShowing <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Is the Browser Marker Popover showing?                                                                                         |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser.BrowserMarkerPopover:app() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `cp.apple.finalcutpro` app table                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The application object as a table                                                |

#### [chapter](#chapter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser.BrowserMarkerPopover:chapter() -> RadioButton` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the "Chapter" Marker button.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A `RadioButton` object.                                                |

#### [completed](#completed)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser.BrowserMarkerPopover:completed() -> CheckBox` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the "Completed" checkbox. This only available if you have a "To Do" marker selected.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A `Button` object.                                                |

#### [delete](#delete)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser.BrowserMarkerPopover:delete() -> Button` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the "Delete" button.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A `Button` object.                                                |

#### [done](#done)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser.BrowserMarkerPopover:done() -> Button` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the "Done" button.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A `Button` object.                                                |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser.BrowserMarkerPopover:hide() -> BrowserMarkerPopover` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides the Browser Marker Popover by clicking "Done" on the popover.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * BrowserMarkerPopover object                                                |

#### [name](#name)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser.BrowserMarkerPopover:name() -> TextField` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the Marker Name text field.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A `TextField` object.                                                |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser.BrowserMarkerPopover:parent() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Browser Marker Popover's parent table                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The parent object as a table                                                |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser.BrowserMarkerPopover:show() -> BrowserMarkerPopover` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows the Browser Marker Popover by triggering "Add Marker and Modify" from the menu bar.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * BrowserMarkerPopover object                                                |

#### [standard](#standard)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser.BrowserMarkerPopover:standard() -> RadioButton` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the "Standard" Marker button.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A `RadioButton` object.                                                |

#### [toDo](#todo)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser.BrowserMarkerPopover:toDo() -> RadioButton` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the "To Do" Marker button.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A `RadioButton` object.                                                |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser.BrowserMarkerPopover:UI() -> hs._asm.axuielement object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `hs._asm.axuielement` object for the Browser Marker Popover                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A `hs._asm.axuielement` object                                                |

