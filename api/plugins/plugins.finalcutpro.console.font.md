# [docs](index.md) » plugins.finalcutpro.console.font
---

Final Cut Pro Font Console

## API Overview
* Constants - Useful values which cannot be changed
 * [FILE_NAME](#file_name)
 * [FOLDER_NAME](#folder_name)
 * [FONT_EXTENSIONS](#font_extensions)
 * [IGNORE_FONTS](#ignore_fonts)
 * [RENAME_FONTS](#rename_fonts)
* Functions - API calls offered directly by the extension
 * [getRunningFonts](#getrunningfonts)
 * [onActivate](#onactivate)
 * [show](#show)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [cachedFonts](#cachedfonts)

## API Documentation

### Constants

#### [FILE_NAME](#file_name)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.console.font.FILE_NAME -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | File name of settings file.                                                                                         |

#### [FOLDER_NAME](#folder_name)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.console.font.FOLDER_NAME -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Folder Name where settings file is contained.                                                                                         |

#### [FONT_EXTENSIONS](#font_extensions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.console.font.FONT_EXTENSIONS -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Table of support font file extensions.                                                                                         |

#### [IGNORE_FONTS](#ignore_fonts)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.console.font.IGNORE_FONTS -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Fonts to ignore as they're used internally by Final Cut Pro or macOS.                                                                                         |

#### [RENAME_FONTS](#rename_fonts)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.console.font.RENAME_FONTS -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Special Fonts that appear to have a different name in Final Cut Pro than they do in Font Book.                                                                                         |

### Functions

#### [getRunningFonts](#getrunningfonts)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.console.font.getRunningFonts() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Shows the Final Cut Pro Console.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [onActivate](#onactivate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.console.font.onActivate() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Handles Console Activations.                                                                                         |
| **Parameters**                                       | <ul><li>handler - Handler instance.</li><li>action - Action table.</li><li>text - Selected text from the Console.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.console.font.show() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Shows the Font Console.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

### Fields

#### [cachedFonts](#cachedfonts)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.console.font.cachedFonts <cp.prop: table | nil>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Table of cached fonts.                                                                                         |

