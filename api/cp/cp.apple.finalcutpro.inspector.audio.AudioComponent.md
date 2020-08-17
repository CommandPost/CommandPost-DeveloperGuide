# [docs](index.md) » cp.apple.finalcutpro.inspector.audio.AudioComponent
---

The Audio Configuration section of the Audio Inspector.

## API Overview
* Functions - API calls offered directly by the extension
 * [AudioComponent](#audiocomponent)
 * [matches](#matches)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [channels](#channels)
 * [role](#role)
 * [showAs](#showas)
* Methods - API calls which can only be made on an object returned by a constructor
 * [doShow](#doshow)
 * [enabled](#enabled)
 * [show](#show)

## API Documentation

### Functions

#### [AudioComponent](#audiocomponent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.audio.AudioComponent(parent) -> AudioComponent` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Creates a new Audio Component object. |
| **Parameters**                                       | <ul><li>parent - The parent object.</li><li>subcomponent - A boolean that defines whether or not this is a subcomponent.</li><li>componentType - "multicam", "compound" or "standard"</li><li>index - The index of the component</li></ul> |
| **Returns**                                          | <ul><li>A new AudioComponent object.</li></ul> |

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.audio.AudioComponent.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks to see if an element matches what we think it should be. |
| **Parameters**                                       | <ul><li>element - An <code>axuielementObject</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if matches otherwise <code>false</code></li></ul> |

### Fields

#### [channels](#channels)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.audio.AudioComponent.channels <cp.ui.MenuButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The channels popup menu button for the component. This only present for |

#### [role](#role)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.audio.AudioComponent.role <cp.ui.MenuButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The role popup menu button for the subcomponent. Only present for |

#### [showAs](#showas)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.audio.AudioComponent.showAs <cp.ui.MenuButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The subroles popup menu button for the component. Only present for |

### Methods

#### [doShow](#doshow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.audio.AudioComponent:doShow() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A Statement that will attempt to show the bar. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code>, which will resolve to <code>true</code> if successful, or send an <code>error</code> if not.</li></ul> |

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.audio.AudioComponent:enabled() -> Button` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the enable/disable button for the component. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Button</code> instance.</li></ul> |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.audio.AudioComponent:show() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Attempts to show the bar. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>AudioComponent</code> instance.</li></ul> |

