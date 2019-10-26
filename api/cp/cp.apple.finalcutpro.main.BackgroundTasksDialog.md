# [docs](index.md) » cp.apple.finalcutpro.main.BackgroundTasksDialog
---

Represents the Background Tasks warning dialog.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [BackgroundTasksDialog](#backgroundtasksdialog)
* Methods - API calls which can only be made on an object returned by a constructor
 * [cancel](#cancel)
 * [continue](#continue)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.BackgroundTasksDialog.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the element is an `BackgroundTasksDialog` instance. |
| **Parameters**                                       | <ul><li>element       - The <code>axuielement</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if it matches the pattern for a `BackgroundTasksDialog``.</li></ul> |

### Constructors

#### [BackgroundTasksDialog](#backgroundtasksdialog)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.BackgroundTasksDialog(cpApp)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new Background Tasks [Dialog](cp.ui.Dialog.md) |

### Methods

#### [cancel](#cancel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.BackgroundTasksDialog:cancel() -> cp.ui.Button` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The Cancel button. |

#### [continue](#continue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.BackgroundTasksDialog:continue() -> cp.ui.Button` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The Continue button. |

