# [docs](index.md) » cp.apple.finalcutpro.inspector.info.InfoProjectInspector
---

Info Inspector Module when a Project is selected.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [doShow](#doshow)
 * [modify](#modify)
 * [propertiesUI](#propertiesui)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.info.InfoProjectInspector.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks to see if an element matches what we think it should be. |
| **Parameters**                                       | <ul><li>element - An <code>axuielementObject</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if matches otherwise <code>false</code></li></ul> |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.info.InfoProjectInspector.new(parent) -> InfoProjectInspector object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new InfoProjectInspector object |
| **Parameters**                                       | <ul><li><code>parent</code>     - The parent</li></ul> |
| **Returns**                                          | <ul><li>A InfoProjectInspector object</li></ul> |

### Methods

#### [doShow](#doshow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.info.InfoProjectInspector:doShow() -> cp.rx.go.Statment` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that shows the panel. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code>, resolving to <code>true</code> if successful and sending an error if not.</li></ul> |

#### [modify](#modify)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.info.InfoProjectInspector:modify() -> Button` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the Modify Project button in the Info Inspector. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>An <code>Button</code> object.</li></ul> |

#### [propertiesUI](#propertiesui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.info.InfoProjectInspector:propertiesUI() -> hs._asm.axuielement object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the `hs._asm.axuielement` object for the Properties UI. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A <code>hs._asm.axuielement</code> object.</li></ul> |

