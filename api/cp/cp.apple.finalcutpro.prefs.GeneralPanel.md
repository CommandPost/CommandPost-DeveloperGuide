# [docs](index.md) » cp.apple.finalcutpro.prefs.GeneralPanel
---

General Panel Module.

## API Overview
* Constants - Useful values which cannot be changed
 * [TIME_DISPLAY](#time_display)
* Functions - API calls offered directly by the extension
 * [timeDisplay](#timedisplay)
* Constructors - API calls which return an object, typically one that offers API methods
 * [GeneralPanel](#generalpanel)

## API Documentation

### Constants

#### [TIME_DISPLAY](#time_display)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.GeneralPanel.TIME_DISPLAY -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The time display options. |

### Functions

#### [timeDisplay](#timedisplay)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.GeneralPanel.timeDisplay([value]) -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets to sets the Time Display value. |
| **Parameters**                                       | <ul><li>value - An optional value to set the Time Display.</li></ul> |
| **Returns**                                          | <ul><li>The time display if successful, otherwise <code>nil</code> if an error occurs.</li></ul> |

### Constructors

#### [GeneralPanel](#generalpanel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.prefs.GeneralPanel(preferencesDialog) -> GeneralPanel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `GeneralPanel` instance. |
| **Parameters**                                       | <ul><li>parent - The parent object.</li></ul> |
| **Returns**                                          | <ul><li>A new <code>GeneralPanel</code> object.</li></ul> |

