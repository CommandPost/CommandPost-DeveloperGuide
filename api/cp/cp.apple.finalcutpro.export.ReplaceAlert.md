# [docs](index.md) » cp.apple.finalcutpro.export.ReplaceAlert
---

Replace Alert

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [isShowing](#isshowing)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [getTitle](#gettitle)
 * [hide](#hide)
 * [parent](#parent)
 * [pressCancel](#presscancel)
 * [pressReplace](#pressreplace)
 * [UI](#ui)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.ReplaceAlert.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if an element matches what we think it should be.                                                                                         |
| **Parameters**                                       | <ul><li>element - An <code>axuielementObject</code> to check.</li></ul>   |
| **Returns**                                          | <ul><li><code>true</code> if matches otherwise <code>false</code></li></ul>            |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.ReplaceAlert.new(app) -> ReplaceAlert` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new Replace Alert object.                                                                                         |
| **Parameters**                                       | <ul><li>app - The <code>cp.apple.finalcutpro</code> object.</li></ul>   |
| **Returns**                                          | <ul><li>A new ReplaceAlert object.</li></ul>            |

### Fields

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.ReplaceAlert.isShowing <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Is the Replace File alert showing?                                                                                         |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.ReplaceAlert:app() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the App instance representing Final Cut Pro.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>App</li></ul>            |

#### [getTitle](#gettitle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.ReplaceAlert:getTitle() -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | The title of the Replace Alert window or `nil`.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The title of the Replace Alert window as a string or <code>nil</code>.</li></ul>            |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.ReplaceAlert:hide() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides the Replace Alert.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.ReplaceAlert:parent() -> object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Parent object.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The parent object.</li></ul>            |

#### [pressCancel](#presscancel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.ReplaceAlert:pressCancel() -> cp.apple.finalcutpro.export.ReplaceAlert` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Presses the Cancel button.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The <code>cp.apple.finalcutpro.export.ReplaceAlert</code> object for method chaining.</li></ul>            |

#### [pressReplace](#pressreplace)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.ReplaceAlert:pressReplace() -> cp.apple.finalcutpro.export.ReplaceAlert` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Presses the Replace button.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The <code>cp.apple.finalcutpro.export.ReplaceAlert</code> object for method chaining.</li></ul>            |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.ReplaceAlert:UI() -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Replace Alert Accessibility Object                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>An <code>axuielementObject</code> or <code>nil</code></li></ul>            |

