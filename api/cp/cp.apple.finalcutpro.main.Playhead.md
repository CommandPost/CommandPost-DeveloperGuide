# [docs](index.md) » cp.apple.finalcutpro.main.Playhead
---

Playhead Module.

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)

## API Documentation

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Playhead:new(parent, skimming, containerFn) -> Playhead` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Constructs a new Playhead                                                                                         |
| **Parameters**                                       | <ul><li>* parent 		- The parent object</li><li>* skimming		- (optional) if `true`, this links to the 'skimming' playhead created under the mouse, if present.</li><li>* containerFn 	- (optional) a function which returns the container axuielement which contains the playheads. If not present, it will use the parent's UI element.</li></ul> |
| **Returns**                                          | <ul><li>* The new `Playhead` instance.</li></ul>          |

