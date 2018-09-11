# [docs](index.md) » cp.apple.finalcutpro.main.Browser.BrowserMarkerPopover
---

Browser Marker Popup.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [BrowserMarkerPopover](#browsermarkerpopover)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [completed](#completed)
 * [delete](#delete)
 * [done](#done)
 * [name](#name)
* Methods - API calls which can only be made on an object returned by a constructor
 * [chapter](#chapter)
 * [hide](#hide)
 * [show](#show)
 * [standard](#standard)
 * [toDo](#todo)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser.BrowserMarkerPopover.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks to see if a GUI element is the Browser Marker Popover or not |
| **Parameters**                                       | <ul><li>element - The element you want to check</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the <code>element</code> is the Browser Marker Popover otherwise <code>false</code></li></ul> |

### Constructors

#### [BrowserMarkerPopover](#browsermarkerpopover)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser.BrowserMarkerPopover(parent) -> BrowserMarkerPopover` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Constructs a new Browser Marker Popover |
| **Parameters**                                       | <ul><li>parent - The parent object</li></ul> |
| **Returns**                                          | <ul><li>The new <code>BrowserMarkerPopover</code> instance.</li></ul> |

### Fields

#### [completed](#completed)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser.BrowserMarkerPopover.completed <cp.ui.CheckBox>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Gets the "Completed" checkbox. This only available if you have a "To Do" marker selected. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A <code>Button</code> object.</li></ul> |

#### [delete](#delete)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser.BrowserMarkerPopover.delete <cp.ui.Button>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Gets the "Delete" [Button](cp.ui.Button.md). |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A <code>Button</code> object.</li></ul> |

#### [done](#done)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser.BrowserMarkerPopover.done <cp.ui.Button>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Done" [Button](cp.ui.Button.md). |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A <code>Button</code> object.</li></ul> |

#### [name](#name)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser.BrowserMarkerPopover.name <cp.ui.TextField>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Gets the Marker Name [TextField](cp.ui.TextField.md). |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A <code>TextField</code> object.</li></ul> |

### Methods

#### [chapter](#chapter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser.BrowserMarkerPopover.chapter() -> RadioButton` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the "Chapter" Marker button. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A <code>RadioButton</code> object.</li></ul> |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser.BrowserMarkerPopover:hide() -> BrowserMarkerPopover` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Hides the Browser Marker Popover by clicking "Done" on the popover. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>BrowserMarkerPopover object</li></ul> |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser.BrowserMarkerPopover:show() -> BrowserMarkerPopover` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Shows the Browser Marker Popover by triggering "Add Marker and Modify" from the menu bar. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>BrowserMarkerPopover object</li></ul> |

#### [standard](#standard)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser.BrowserMarkerPopover:standard() -> RadioButton` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the "Standard" Marker button. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A <code>RadioButton</code> object.</li></ul> |

#### [toDo](#todo)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Browser.BrowserMarkerPopover:toDo() -> RadioButton` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the "To Do" Marker button. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A <code>RadioButton</code> object.</li></ul> |

