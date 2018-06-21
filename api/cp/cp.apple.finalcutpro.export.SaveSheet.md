# [docs](index.md) » cp.apple.finalcutpro.export.SaveSheet
---

Save Sheet

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
 * [new](#new)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [SaveSheet](#savesheet)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [filename](#filename)
 * [getTitle](#gettitle)
 * [goToPrompt](#gotoprompt)
 * [hide](#hide)
 * [parent](#parent)
 * [pressCancel](#presscancel)
 * [pressSave](#presssave)
 * [setPath](#setpath)
 * [UI](#ui)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.SaveSheet.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if an element matches what we think it should be.                                                                                         |
| **Parameters**                                       |  * element - An `axuielementObject` to check.                                       |
| **Returns**                                          |  * `true` if matches otherwise `false`                                                |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.SaveSheet.new(app) -> SaveSheet` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates a new SaveSheet object.                                                                                         |
| **Parameters**                                       |  * app - The `cp.apple.finalcutpro` object.                                       |
| **Returns**                                          |  * A new SaveSheet object.                                                |

### Fields

#### [SaveSheet](#savesheet)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.SaveSheet <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Is the Save Sheet showing?                                                                                         |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.SaveSheet:app() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the App instance representing Final Cut Pro.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * App                                                |

#### [filename](#filename)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.SaveSheet:filename() -> TextField` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Save Sheet Filename Text Field.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The title of the Save Sheet window as a string or `nil`.                                                |

#### [getTitle](#gettitle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.SaveSheet:getTitle() -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | The title of the Save Sheet window or `nil`.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The title of the Save Sheet window as a string or `nil`.                                                |

#### [goToPrompt](#gotoprompt)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.SaveSheet:goToPrompt() -> GoToPrompt` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the Go To Prompt object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A `GoToPrompt` object.                                                |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.SaveSheet:hide() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides the Save Sheet                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.SaveSheet:parent() -> object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Parent object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The parent object.                                                |

#### [pressCancel](#presscancel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.SaveSheet:pressCancel() -> cp.apple.finalcutpro.export.SaveSheet` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Presses the Cancel Button.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `cp.apple.finalcutpro.export.SaveSheet` object for method chaining.                                                |

#### [pressSave](#presssave)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.SaveSheet:pressSave() -> cp.apple.finalcutpro.export.SaveSheet` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Presses the Save Button.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `cp.apple.finalcutpro.export.SaveSheet` object for method chaining.                                                |

#### [setPath](#setpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.SaveSheet:setPath() -> ReplaceAlert` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the Replace Alert object.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A `ReplaceAlert` object.                                                |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.SaveSheet:UI() -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Save Sheet Accessibility Object                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * An `axuielementObject` or `nil`                                                |

