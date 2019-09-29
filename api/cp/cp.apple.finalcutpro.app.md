# [docs](index.md) » cp.apple.finalcutpro.app
---

The [cp.app](cp.app.md) for Final Cut Pro. Will automatically determine
if only the trial version of FCPX is installed and use that instead.

## API Overview
* Constants - Useful values which cannot be changed
 * [app](#app)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [application](#application)

## API Documentation

### Constants

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.app <cp.app>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The [app](cp.app.md) for Final Cut Pro. |
| **Notes**                                            | <ul><li>All values from <a href="cp.app.md">app</a> can be accessed directly from the <code>finalcutpro</code> instance.</li></ul> |

### Fields

#### [application](#application)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.application <cp.prop: hs.application; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Returns the running `hs.application` for Final Cut Pro, or `nil` if it's not running. |

