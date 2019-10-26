# [docs](index.md) » cp.apple.finalcutpro.export.ExportDialog
---

Export Dialog Module.

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [ExportDialogTitleText](#exportdialogtitletext)
* Methods - API calls which can only be made on an object returned by a constructor
 * [fileExtension](#fileextension)
 * [getTitle](#gettitle)
 * [hide](#hide)
 * [pressCancel](#presscancel)
 * [pressNext](#pressnext)
 * [saveSheet](#savesheet)
 * [show](#show)

## API Documentation

### Constructors

#### [ExportDialogTitleText](#exportdialogtitletext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.ExportDialogTitleText(parent)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new Export [Dialog](cp.ui.Dialog.md) |

### Methods

#### [fileExtension](#fileextension)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.ExportDialog:fileExtension() -> cp.ui.StaticText` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The "File Extension" [StaticText](cp.ui.StaticText.md). |

#### [getTitle](#gettitle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.ExportDialog:getTitle() -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The title of the Go To Prompt window or `nil`. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The title of the Go To Prompt window as a string or <code>nil</code>.</li></ul> |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.ExportDialog:hide() -> cp.apple.finalcutpro.export.ExportDialog` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Hides the Export Dialog |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.apple.finalcutpro.export.ExportDialog</code> object for method chaining.</li></ul> |

#### [pressCancel](#presscancel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.ExportDialog:pressCancel() -> cp.apple.finalcutpro.export.ExportDialog` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Presses the Cancel Button. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.apple.finalcutpro.export.ExportDialog</code> object for method chaining.</li></ul> |

#### [pressNext](#pressnext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.ExportDialog:pressNext() -> cp.apple.finalcutpro.export.ExportDialog` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Presses the Next Button. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.apple.finalcutpro.export.ExportDialog</code> object for method chaining.</li></ul> |

#### [saveSheet](#savesheet)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.ExportDialog:saveSheet() -> SaveSheet` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Creates a new Save Sheet. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The SaveSheet.</li></ul> |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.export.ExportDialog:show(destinationSelect, ignoreProxyWarning, ignoreMissingMedia, ignoreInvalidCaptions, quiet) -> cp.apple.finalcutpro.export.ExportDialog, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Shows the Export Dialog with the Destination that matches the `destinationSelect`. |
| **Parameters**                                       | <ul><li>destinationSelect        - The name, number or match function of the destination to export with.</li><li>ignoreProxyWarning       - if <code>true</code>, the warning regarding exporting Proxies will be ignored.</li><li>ignoreMissingMedia       - if <code>true</code>, the warning regarding exporting with missing media will be ignored.</li><li>ignoreInvalidCaptions    - if <code>true</code>, the warning regarding exporting with Bad Captions will be ignored.</li><li>quiet                    - if <code>true</code>, no dialogs will be shown if there is an error.</li></ul> |
| **Returns**                                          | <ul><li>The <code>cp.apple.finalcutpro.export.ExportDialog</code> object for method chaining.</li><li>If an error occurred, the message is returned as the second value</li></ul> |
| **Notes**                                            | <ul><li>If providing a function, it will be passed one item - the name of the destination, and should return <code>true</code> to indicate a match. The name will not contain " (default)" if present.</li></ul> |

