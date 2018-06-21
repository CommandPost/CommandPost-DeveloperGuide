# [docs](index.md) » plugins.finalcutpro.browser.keywords
---

Browser Keywords Presets.

## API Overview
* Constants - Useful values which cannot be changed
 * [NUMBER_OF_PRESETS](#number_of_presets)
 * [NUMBER_OF_SHORTCUTS](#number_of_shortcuts)
* Functions - API calls offered directly by the extension
 * [restore](#restore)
 * [save](#save)

## API Documentation

### Constants

#### [NUMBER_OF_PRESETS](#number_of_presets)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.browser.keywords.NUMBER_OF_PRESETS -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The number of presets available.                                                                                         |

#### [NUMBER_OF_SHORTCUTS](#number_of_shortcuts)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.browser.keywords.NUMBER_OF_SHORTCUTS -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The number of Keyword Keyboard shortcuts available.                                                                                         |

### Functions

#### [restore](#restore)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.browser.keywords.restore(preset) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Restores a Keyword preset.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">preset - A preset number between 1 and the value of `plugins.finalcutpro.browser.keywords.NUMBER_OF_PRESETS`.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

#### [save](#save)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.browser.keywords.save(preset) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Saves a Keyword preset.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">preset - A preset number between 1 and the value of `plugins.finalcutpro.browser.keywords.NUMBER_OF_PRESETS`.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">None</li></ul>          |

