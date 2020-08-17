# [docs](index.md) » cp.apple.finalcutpro.export.SaveSheet
---

Save Sheet

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
 * [SaveSheet](#savesheet)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [cancel](#cancel)
 * [filename](#filename)
 * [goToPrompt](#gotoprompt)
 * [replaceAlert](#replacealert)
 * [save](#save)
* Methods - API calls which can only be made on an object returned by a constructor
 * [setPath](#setpath)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.SaveSheet.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks to see if an element matches what we think it should be. |
| **Parameters**                                       | <ul><li>element - An <code>axuielementObject</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if matches otherwise <code>false</code></li></ul> |

#### [SaveSheet](#savesheet)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.SaveSheet(app) -> SaveSheet` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Creates a new SaveSheet object. |
| **Parameters**                                       | <ul><li>app - The <code>cp.apple.finalcutpro</code> object.</li></ul> |
| **Returns**                                          | <ul><li>A new SaveSheet object.</li></ul> |

### Fields

#### [cancel](#cancel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.SaveSheet.cancel <cp.ui.Button>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Cancel" `Button`. |

#### [filename](#filename)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.SaveSheet.filename <cp.ui.TextField>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The Save Sheet Filename Text Field. |

#### [goToPrompt](#gotoprompt)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.SaveSheet.goToPrompt <GoToPrompt>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The Go To Prompt object. |

#### [replaceAlert](#replacealert)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.SaveSheet.replaceAlert <ReplaceAlert>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The Replace Alert object. |

#### [save](#save)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.SaveSheet.save <cp.ui.Button>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Save" `Button`. |

### Methods

#### [setPath](#setpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.SaveSheet:setPath(path) -> cp.apple.finalcutpro.export.SaveSheet` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the path. |
| **Parameters**                                       | <ul><li>path - The path as a string.</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.apple.finalcutpro.export.SaveSheet</code> object for method chaining.</li></ul> |

