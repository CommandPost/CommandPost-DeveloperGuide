# [docs](index.md) » cp.ui.SplitGroup
---

Split Group UI.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [SplitGroup](#splitgroup)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.SplitGroup.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks to see if an element matches what we think it should be. |
| **Parameters**                                       | <ul><li>element - An <code>axuielementObject</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if matches otherwise <code>false</code></li></ul> |

### Constructors

#### [SplitGroup](#splitgroup)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.SplitGroup(parent, uiFinder) -> cp.ui.SplitGroup` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new Split Group. |
| **Parameters**                                       | <ul><li>parent       - The parent object.</li><li>uiFinder     - The <code>function</code> or <code>cp.prop</code> which returns an <code>hs._asm.axuielement</code> for the Split Group, or <code>nil</code>.</li></ul> |
| **Returns**                                          | <ul><li>A new <code>SplitGroup</code> instance.</li></ul> |

