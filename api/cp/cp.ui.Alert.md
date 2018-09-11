# [docs](index.md) » cp.ui.Alert
---

Alert UI Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [cancel](#cancel)
 * [default](#default)
 * [title](#title)
* Methods - API calls which can only be made on an object returned by a constructor
 * [containsText](#containstext)
 * [doCancel](#docancel)
 * [doDefault](#dodefault)
 * [doHide](#dohide)
 * [doPress](#dopress)
 * [hide](#hide)
 * [pressCancel](#presscancel)
 * [pressDefault](#pressdefault)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Alert.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks to see if an element matches what we think it should be. |
| **Parameters**                                       | <ul><li>element - An <code>axuielementObject</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if matches otherwise <code>false</code></li></ul> |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Alert:new(app) -> Alert` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `Alert` instance. |
| **Parameters**                                       | <ul><li>parent - The parent object.</li></ul> |
| **Returns**                                          | <ul><li>A new <code>Browser</code> object.</li></ul> |

### Fields

#### [cancel](#cancel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Alert.cancel <cp.ui.Button>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The cancel [Button](cp.ui.Button.md) for the `Alert`. |

#### [default](#default)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Alert.default <cp.ui.Button>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The default [Button](cp.ui.Button.md) for the `Alert`. |

#### [title](#title)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Alert.title <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Gets the title of the alert. |

### Methods

#### [containsText](#containstext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Alert:containsText(value[, plain]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Checks if there are any child text elements containing the exact text or pattern, from beginning to end. |
| **Parameters**                                       | <ul><li>textPattern   - The text pattern to check.</li><li>plain         - If <code>true</code>, the text will be compared exactly, otherwise it will be considered to be a pattern. Defaults to <code>false</code>.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if an element's <code>AXValue</code> matches the text pattern exactly.</li></ul> |

#### [doCancel](#docancel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Alert:doCancel() -> cp.rx.go.Statement <boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Attempts to hide the Alert (if visible) by pressing the [Cancel](#cancel) button. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A <a href="cp.rx.go.Statement.md">Statement</a> to execute, resolving to <code>true</code> if the button was present and clicked, otherwise <code>false</code>.</li></ul> |

#### [doDefault](#dodefault)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Alert:doDefault() -> cp.rx.go.Statement <boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Attempts to press the `default` [Button](cp.ui.Button.md). |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A <a href="cp.rx.go.Statement.md">Statement</a> to execute, resolving to <code>true</code> if the button was present and clicked, otherwise <code>false</code>.</li></ul> |

#### [doHide](#dohide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Alert:doHide() -> cp.rx.go.Statement <boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Attempts to hide the Alert (if visible) by pressing the [Cancel](#cancel) button. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A <a href="cp.rx.go.Statement.md">Statement</a> to execute, resolving to <code>true</code> if the button was present and clicked, otherwise <code>false</code>.</li></ul> |

#### [doPress](#dopress)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Alert:doPress(buttonFromLeft) -> cp.rx.go.Statement <boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Attempts to press the indicated button from left-to-right, if it can be found. |
| **Parameters**                                       | <ul><li>buttonFromLeft    - The number of the button from left-to-right.</li></ul> |
| **Returns**                                          | <ul><li>a <a href="cp.rx.go.Statement.md">Statement</a> to execute, resolving in <code>true</code> if the button was found and pressed, otherwise <code>false</code>.</li></ul> |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Alert:hide() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Hides the alert by pressing the "Cancel" button. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [pressCancel](#presscancel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Alert:pressCancel() -> self, boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Presses the Cancel button. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Alert</code> object.</li><li><code>true</code> if successful, otherwise <code>false</code>.</li></ul> |

#### [pressDefault](#pressdefault)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.Alert:pressDefault() -> self, boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Presses the Default button. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Alert</code> object.</li><li><code>true</code> if successful, otherwise <code>false</code>.</li></ul> |

