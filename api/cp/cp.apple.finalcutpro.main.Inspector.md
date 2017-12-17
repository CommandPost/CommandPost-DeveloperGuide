# [docs](index.md) » cp.apple.finalcutpro.main.Inspector
---

Inspector

## API Overview
* Functions - API calls offered directly by the extension
 * [isShowing](#isshowing)
 * [matches](#matches)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [hide](#hide)
 * [new](#new)
 * [parent](#parent)
 * [selectedTab](#selectedtab)
 * [selectTab](#selecttab)
 * [show](#show)
 * [stabilization](#stabilization)
 * [UI](#ui)

## API Documentation

### Functions

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Inspector.isShowing() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns `true` if the Inspector is showing otherwise `false`                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>`true` if showing, otherwise `false`</li></ul>          |

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Inspector.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if an element matches what we think it should be.                                                                                         |
| **Parameters**                                       | <ul><li>element - axuielementObject</li></ul> |
| **Returns**                                          | <ul><li>`true` if matches otherwise `false`</li></ul>          |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Inspector:app() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the app instance representing Final Cut Pro.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>App</li></ul>          |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Inspector:hide() -> Inspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides the inspector.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The `Inspector` instance.</li></ul>          |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Inspector:new(parent) -> Inspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a new Inspector.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>App</li></ul>          |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Inspector:parent() -> Parent` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the parent of the Inspector.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>App</li></ul>          |

#### [selectedTab](#selectedtab)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Inspector:selectedTab() -> string or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the name of the selected inspector tab otherwise `nil`.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string of the selected tab, otherwise `nil` if the Inspector is closed or an error occurred.</li></ul>          |
| **Notes**                                            | <ul><li>The tab strings can be:</li><li>  Audio</li><li>  Color</li><li>  Effect</li><li>  Generator</li><li>  Info</li><li>  Share</li><li>  Text</li><li>  Title</li><li>  Transition</li><li>  Video</li></ul>                |

#### [selectTab](#selecttab)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Inspector:selectTab([value]) -> boolean or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Selects a tab in the inspector.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string of the selected tab, otherwise `nil` if an error occurred.</li></ul>          |
| **Notes**                                            | <ul><li>This method will open the Inspector if it's closed, and leave it open.</li><li>Valid strings for `value` are as follows:</li><li>  Audio</li><li>  Color</li><li>  Effect</li><li>  Generator</li><li>  Info</li><li>  Share</li><li>  Text</li><li>  Title</li><li>  Transition</li><li>  Video</li></ul>                |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Inspector:show() -> Inspector` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows the inspector.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The `Inspector` instance.</li></ul>          |

#### [stabilization](#stabilization)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Inspector:stabilization([value]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets or returns the stabilization setting for a clip.                                                                                         |
| **Parameters**                                       | <ul><li>[value] - A boolean value you want to set the stabilization setting for the clip to.</li></ul> |
| **Returns**                                          | <ul><li>The value of the stabilization settings, or `nil` if an error has occurred.</li></ul>          |
| **Notes**                                            | <ul><li>This method will open the Inspector if it's closed, and close it again after adjusting the stablization settings.</li></ul>                |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.Inspector:UI() -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Inspectors Accessibility Object                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>An `axuielementObject` on `nil`</li></ul>          |

