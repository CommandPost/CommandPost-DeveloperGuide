# [docs](index.md) » cp.apple.finalcutpro.main.Timeline
---

Timeline Module.

## API Overview
* Methods - API calls which can only be made on an object returned by a constructor
 * [lockPlayhead](#lockplayhead)

## API Documentation

### Methods

#### [lockPlayhead](#lockplayhead)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Timeline:lockPlayhead(deactivateWhenStopped, lockInCentre) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Locks the playhead on-screen.                                                                                         |
| **Parameters**                                       | <ul><li>deactivateWhenStopped - If set to `true`, this will automatically deactivate itself when the playhead stops moving.</li><li>lockInCentre - If set to `true`, the playhead will lock in the centre of the timeline. Otherwise, it will lock in it's current position.</li></ul> |
| **Returns**                                          | <ul><li>The `Timeline` instance.</li></ul>          |

