# [docs](index.md) » cp.ui.Slider
---

Slider Module.

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [snapshot](#snapshot)

## API Documentation

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Slider.new(parent, finderFn) -> cp.ui.Slider` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new Slider                                                                                         |
| **Parameters**                                       | <ul><li>* parent		- The parent object. Should have an `isShowing` property.</li><li>* finderFn		- The function which returns an `hs._asm.axuielement` for the slider, or `nil`.</li></ul> |
| **Returns**                                          | <ul><li>* A new `Slider` instance.</li></ul>          |

### Methods

#### [snapshot](#snapshot)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Slider:snapshot([path]) -> hs.image | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Takes a snapshot of the UI in its current state as a PNG and returns it.                                                                                         |
| **Parameters**                                       | <ul><li>* path		- (optional) The path to save the file. Should include the extension (should be `.png`).</li></ul> |

