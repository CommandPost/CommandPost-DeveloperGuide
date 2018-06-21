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
| **Parameters**                                       |  * element - An `axuielementObject` to check.                                       |
| **Returns**                                          |  * `true` if matches otherwise `false`                                                |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Alert.new(app) -> Alert` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `Alert` instance.                                                                                         |
| **Parameters**                                       |  * parent - The parent object.                                       |
| **Returns**                                          |  * A new `Browser` object.                                                |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Alert:app() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the app instance.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * App                                                |

#### [cancel](#cancel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Alert:cancel() -> Button` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the Cancel button object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A `Button` object.                                                |

#### [containsText](#containstext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Alert:containsText(value[, plain]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Checks if there are any child text elements containing the exact text or pattern, from beginning to end.                                                                                         |
| **Parameters**                                       |  * textPattern   - The text pattern to check. * plain         - If `true`, the text will be compared exactly, otherwise it will be considered to be a pattern. Defaults to `false`.                                       |
| **Returns**                                          |  * `true` if an element's `AXValue` matches the text pattern exactly.                                                |

#### [default](#default)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Alert:default() -> Button` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the default button object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A `Button` object.                                                |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Alert:hide() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides the alert by pressing the "Cancel" button.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Alert:parent() -> parent` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the parent object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * parent                                                |

#### [pressCancel](#presscancel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Alert:pressCancel() -> self, boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Presses the Cancel button.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `Alert` object. * `true` if successful, otherwise `false`.                                                |

#### [pressDefault](#pressdefault)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Alert:pressDefault() -> self, boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Presses the Default button.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `Alert` object. * `true` if successful, otherwise `false`.                                                |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Alert:UI() -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the UI object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * An axuielementObject object.                                                |

