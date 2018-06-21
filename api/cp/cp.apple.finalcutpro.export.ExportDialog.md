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
| **Parameters**                                       | <ul markdown="1"><li markdown="1">element - An `axuielementObject` to check.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`true` if matches otherwise `false`</li></ul>          |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.ExportDialog.new(app) -> ExportDialog` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new Export Dialog object.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">app - The `cp.apple.finalcutpro` object.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A new ExportDialog object.</li></ul>          |

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
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">App</li></ul>          |

#### [getTitle](#gettitle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.ExportDialog:getTitle() -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | The title of the Go To Prompt window or `nil`.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The title of the Go To Prompt window as a string or `nil`.</li></ul>          |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.ExportDialog:hide() -> cp.apple.finalcutpro.export.ExportDialog` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides the Export Dialog                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The `cp.apple.finalcutpro.export.ExportDialog` object for method chaining.</li></ul>          |

#### [pressCancel](#presscancel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.ExportDialog:pressCancel() -> cp.apple.finalcutpro.export.ExportDialog` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Presses the Cancel Button.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The `cp.apple.finalcutpro.export.ExportDialog` object for method chaining.</li></ul>          |

#### [pressNext](#pressnext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.ExportDialog:pressNext() -> cp.apple.finalcutpro.export.ExportDialog` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Presses the Next Button.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The `cp.apple.finalcutpro.export.ExportDialog` object for method chaining.</li></ul>          |

#### [saveSheet](#savesheet)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.ExportDialog:saveSheet() -> SaveSheet` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Creates a new Save Sheet.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The SaveSheet.</li></ul>          |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.ExportDialog:show(destinationSelect, ignoreProxyWarning, ignoreMissingMedia, quiet) -> cp.apple.finalcutpro.export.ExportDialog, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows the Export Dialog with the Destination that matches the `destinationSelect`.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">destinationSelect    - The name, number or match function of the destination to export with.</li><li markdown="1">ignoreProxyWarning   - if `true`, the warning regarding exporting Proxies will be ignored.</li><li markdown="1">ignoreMissingMedia   - if `true`, the warning regarding exporting with missing media will be ignored.</li><li markdown="1">quiet                - if `true`, no dialogs will be shown if there is an error.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The `cp.apple.finalcutpro.export.ExportDialog` object for method chaining.</li><li markdown="1">If an error occurred, the message is returned as the second value</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">* If providing a function, it will be passed one item - the name of the destination, and should return `true` to indicate a match. The name will not contain " (default)" if present.</li></ul>                |

