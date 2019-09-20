# [docs](index.md) » plugins.finalcutpro.console.font
---

Final Cut Pro Font Console

## API Overview
* Variables - Configurable values
 * [processedFonts](#processedfonts)
* Functions - API calls offered directly by the extension
 * [onActivate](#onactivate)
 * [show](#show)

## API Documentation

### Variables

#### [processedFonts](#processedfonts)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.console.font.processedFonts -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Table of font paths which have already been loaded or skipped. |

### Functions

#### [onActivate](#onactivate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.console.font.onActivate() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Handles Console Activations. |
| **Parameters**                                       | <ul><li>handler - Handler instance.</li><li>action - Action table.</li><li>text - Selected text from the Console.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.console.font.show() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Shows the Font Console. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

