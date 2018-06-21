# [docs](index.md) » cp.ui.Alert
---

Alert UI Module.

## API Overview
* Variables - Configurable values
 * [isShowing](#isshowing)
 * [title](#title)
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [cancel](#cancel)
 * [containsText](#containstext)
 * [default](#default)
 * [hide](#hide)
 * [parent](#parent)
 * [pressCancel](#presscancel)
 * [pressDefault](#pressdefault)
 * [UI](#ui)

## API Documentation

### Variables

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Alert.isShowing <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Is the alert showing?                                                                                         |

#### [title](#title)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Alert.title <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Gets the title of the alert.                                                                                         |

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Alert.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if an element matches what we think it should be.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">element - An `axuielementObject` to check.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`true` if matches otherwise `false`</li></ul>          |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Alert.new(app) -> Alert` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `Alert` instance.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">parent - The parent object.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A new `Browser` object.</li></ul>          |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Alert:app() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the app instance.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">App</li></ul>          |

#### [cancel](#cancel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Alert:cancel() -> Button` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the Cancel button object.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A `Button` object.</li></ul>          |

#### [containsText](#containstext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Alert:containsText(value[, plain]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Checks if there are any child text elements containing the exact text or pattern, from beginning to end.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">textPattern   - The text pattern to check.</li><li markdown="1">plain         - If `true`, the text will be compared exactly, otherwise it will be considered to be a pattern. Defaults to `false`.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`true` if an element's `AXValue` matches the text pattern exactly.</li></ul>          |

#### [default](#default)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Alert:default() -> Button` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the default button object.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A `Button` object.</li></ul>          |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Alert:hide() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides the alert by pressing the "Cancel" button.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Alert:parent() -> parent` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the parent object.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">parent</li></ul>          |

#### [pressCancel](#presscancel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Alert:pressCancel() -> self, boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Presses the Cancel button.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The `Alert` object.</li><li markdown="1">`true` if successful, otherwise `false`.</li></ul>          |

#### [pressDefault](#pressdefault)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Alert:pressDefault() -> self, boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Presses the Default button.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The `Alert` object.</li><li markdown="1">`true` if successful, otherwise `false`.</li></ul>          |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Alert:UI() -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the UI object.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">An axuielementObject object.</li></ul>          |

