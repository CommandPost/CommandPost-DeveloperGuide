# [docs](index.md) » hs.uielement
---

A generalized framework for working with OSX UI elements

## Submodules
 * [hs.uielement.watcher](hs.uielement.watcher.md)

## API Overview
* Functions - API calls offered directly by the extension
 * [focusedElement](#focusedelement)
* Constructors - API calls which return an object, typically one that offers API methods
 * [newWatcher](#newwatcher)
* Methods - API calls which can only be made on an object returned by a constructor
 * [isApplication](#isapplication)
 * [isWindow](#iswindow)
 * [role](#role)
 * [selectedText](#selectedtext)

## API Documentation

### Functions

#### [focusedElement](#focusedelement)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.uielement.focusedElement() -> element or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets the currently focused UI element |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>An <code>hs.uielement</code> object or nil if no object could be found</li></ul> |

### Constructors

#### [newWatcher](#newwatcher)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.uielement:newWatcher(handler[, userData]) -> hs.uielement.watcher or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new watcher for the element represented by self (the object the method is being invoked for). |
| **Parameters**                                       | <ul><li>a function to be called when a watched event occurs.  The argument will be passed the following arguments:</li><li>element: The element the event occurred on. Note this is not always the element being watched.</li><li>event: The name of the event that occurred.</li><li>watcher: The watcher object being created.</li><li>userData: The userData you included, if any.</li><li>an optional userData object which will be included as the final argument to the callback function when it is called.</li></ul> |
| **Returns**                                          | <ul><li>An <code>hs.uielement.watcher</code> object, or <code>nil</code> if an error occurred</li></ul> |

### Methods

#### [isApplication](#isapplication)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.uielement:isApplication() -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns whether the UI element represents an application. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A boolean, true if the UI element is an application</li></ul> |

#### [isWindow](#iswindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.uielement:isWindow() -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns whether the UI element represents a window. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A boolean, true if the UI element is a window, otherwise false</li></ul> |

#### [role](#role)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.uielement:role() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the role of the element. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string containing the role of the UI element</li></ul> |

#### [selectedText](#selectedtext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.uielement:selectedText() -> string or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the selected text in the element |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string containing the selected text, or nil if none could be found</li></ul> |
| **Notes**                                            | <ul><li>Many applications (e.g. Safari, Mail, Firefox) do not implement the necessary accessibility features for this to work in their web views</li></ul> |

