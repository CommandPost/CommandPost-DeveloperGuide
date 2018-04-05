# [docs](index.md) » cp.ui.PopUpButton
---

Pop Up Button Module.

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [snapshot](#snapshot)

## API Documentation

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PopUpButton.new(axuielement, function) -> cp.ui.PopUpButton` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new PopUpButton.                                                                                         |
| **Parameters**                                       | <ul><li>* parent		- The parent table. Should have a `isShowing` property.</li></ul> |
| **Returns**                                          | <ul><li>* The new `PopUpButton` instance.</li></ul>          |

### Methods

#### [snapshot](#snapshot)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.PopUpButton:snapshot([path]) -> hs.image | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Takes a snapshot of the UI in its current state as a PNG and returns it.                                                                                         |
| **Parameters**                                       | <ul><li>* path		- (optional) The path to save the file. Should include the extension (should be `.png`).</li></ul> |

