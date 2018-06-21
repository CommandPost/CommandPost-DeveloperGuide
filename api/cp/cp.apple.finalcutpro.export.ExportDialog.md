# [docs](index.md) » cp.apple.finalcutpro.export.ExportDialog
---

Export Dialog Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [isShowing](#isshowing)
 * [title](#title)
 * [UI](#ui)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [getTitle](#gettitle)
 * [hide](#hide)
 * [pressCancel](#presscancel)
 * [pressNext](#pressnext)
 * [saveSheet](#savesheet)
 * [show](#show)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.ExportDialog.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if an element matches what we think it should be.                                                                                         |
| **Parameters**                                       |  * element - An `axuielementObject` to check.                                       |
| **Returns**                                          |  * `true` if matches otherwise `false`                                                |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.ExportDialog.new(app) -> ExportDialog` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new Export Dialog object.                                                                                         |
| **Parameters**                                       |  * app - The `cp.apple.finalcutpro` object.                                       |
| **Returns**                                          |  * A new ExportDialog object.                                                |

### Fields

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.ExportDialog.isShowing <cp.prop: boolean; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Is the window showing?                                                                                         |

#### [title](#title)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.ExportDialog.title <cp.prop: string; read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The window title, or `nil` if not available.                                                                                         |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.ExportDialog.UI <cp.prop: hs._asm.axuielement: read-only; live>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Returns the Export Dialog `axuielement`.                                                                                         |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.ExportDialog:app() -> App` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the app instance representing Final Cut Pro.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * App                                                |

#### [getTitle](#gettitle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.ExportDialog:getTitle() -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | The title of the Go To Prompt window or `nil`.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The title of the Go To Prompt window as a string or `nil`.                                                |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.ExportDialog:hide() -> cp.apple.finalcutpro.export.ExportDialog` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides the Export Dialog                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `cp.apple.finalcutpro.export.ExportDialog` object for method chaining.                                                |

#### [pressCancel](#presscancel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.ExportDialog:pressCancel() -> cp.apple.finalcutpro.export.ExportDialog` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Presses the Cancel Button.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `cp.apple.finalcutpro.export.ExportDialog` object for method chaining.                                                |

#### [pressNext](#pressnext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.ExportDialog:pressNext() -> cp.apple.finalcutpro.export.ExportDialog` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Presses the Next Button.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The `cp.apple.finalcutpro.export.ExportDialog` object for method chaining.                                                |

#### [saveSheet](#savesheet)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.ExportDialog:saveSheet() -> SaveSheet` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a new Save Sheet.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The SaveSheet.                                                |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.ExportDialog:show(destinationSelect, ignoreProxyWarning, ignoreMissingMedia, quiet) -> cp.apple.finalcutpro.export.ExportDialog, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows the Export Dialog with the Destination that matches the `destinationSelect`.                                                                                         |
| **Parameters**                                       |  * destinationSelect    - The name, number or match function of the destination to export with. * ignoreProxyWarning   - if `true`, the warning regarding exporting Proxies will be ignored. * ignoreMissingMedia   - if `true`, the warning regarding exporting with missing media will be ignored. * quiet                - if `true`, no dialogs will be shown if there is an error.                                       |
| **Returns**                                          |  * The `cp.apple.finalcutpro.export.ExportDialog` object for method chaining. * If an error occurred, the message is returned as the second value                                                |
| **Notes**                                            | * If providing a function, it will be passed one item - the name of the destination, and should return `true` to indicate a match. The name will not contain " (default)" if present.                                                      |

