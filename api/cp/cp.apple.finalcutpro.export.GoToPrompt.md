# [docs](index.md) » cp.apple.finalcutpro.export.GoToPrompt
---

Go To Prompt.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
 * [new](#new)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [isShowing](#isshowing)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [hide](#hide)
 * [parent](#parent)
 * [pressCancel](#presscancel)
 * [pressDefault](#pressdefault)
 * [setValue](#setvalue)
 * [show](#show)
 * [UI](#ui)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.GoToPrompt.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks to see if an element matches what we think it should be. |
| **Parameters**                                       | <ul><li>element - An <code>axuielementObject</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if matches otherwise <code>false</code></li></ul> |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.GoToPrompt.new(app) -> GoToPrompt` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Creates a new Go To Prompt object. |
| **Parameters**                                       | <ul><li>app - The <code>cp.apple.finalcutpro</code> object.</li></ul> |
| **Returns**                                          | <ul><li>A new GoToPrompt object.</li></ul> |

### Fields

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.GoToPrompt.isShowing <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Is the 'Go To' prompt showing? |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.GoToPrompt:app() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the App instance representing Final Cut Pro. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>App</li></ul> |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.GoToPrompt:hide() -> cp.apple.finalcutpro.export.GoToPrompt` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Hides the Go To Prompt |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.apple.finalcutpro.export.GoToPrompt</code> object for method chaining.</li></ul> |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.GoToPrompt:parent() -> object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the Parent object. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The parent object.</li></ul> |

#### [pressCancel](#presscancel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.GoToPrompt:pressCancel() -> cp.apple.finalcutpro.export.GoToPrompt` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Presses the Cancel Button. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.apple.finalcutpro.export.GoToPrompt</code> object for method chaining.</li></ul> |

#### [pressDefault](#pressdefault)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.GoToPrompt:pressDefault() -> cp.apple.finalcutpro.export.GoToPrompt` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Presses the Default Button. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.apple.finalcutpro.export.GoToPrompt</code> object for method chaining.</li></ul> |

#### [setValue](#setvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.GoToPrompt:setValue(value) -> cp.apple.finalcutpro.export.GoToPrompt` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the value of the text box within the Go To Prompt. |
| **Parameters**                                       | <ul><li>value - The value of the text box as a string.</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.apple.finalcutpro.export.GoToPrompt</code> object for method chaining.</li></ul> |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.GoToPrompt:show() -> cp.apple.finalcutpro.export.GoToPrompt` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Shows the Go To Prompt |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.apple.finalcutpro.export.GoToPrompt</code> object for method chaining.</li></ul> |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.GoToPrompt:UI() -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the Go To Prompt Accessibility Object |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>An <code>axuielementObject</code> or <code>nil</code></li></ul> |

