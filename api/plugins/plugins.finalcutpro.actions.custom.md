# [docs](index.md) » plugins.finalcutpro.actions.custom
---

Creates a bunch of commands that can be used to assign actions to.
This allows you to assign any action to a shortcut key in CommandPost.

## API Overview
* Variables - Configurable values
 * [shortcuts](#shortcuts)
* Functions - API calls offered directly by the extension
 * [apply](#apply)
 * [assign](#assign)

## API Documentation

### Variables

#### [shortcuts](#shortcuts)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.actions.custom.shortcuts <cp.prop: table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Table of shortcuts. |

### Functions

#### [apply](#apply)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.actions.custom.apply(id) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Applies a shortcut. |
| **Parameters**                                       | <ul><li><code>id</code> - The Custom Action ID.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [assign](#assign)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.actions.custom.assign(id, handlerId) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Assigns an Action to a Shortcut via a Console. |
| **Parameters**                                       | <ul><li><code>id</code> - The Custom Action ID.</li><li><code>completionFn</code> - An optional completion function that triggers when a selection is made.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

