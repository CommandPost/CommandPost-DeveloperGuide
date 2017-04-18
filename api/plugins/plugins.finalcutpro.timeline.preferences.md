# [docs](index.md) » plugins.finalcutpro.timeline.preferences
---

Final Cut Pro Timeline Preferences.

## API Overview
* Functions - API calls offered directly by the extension
 * [getAutoRenderDelay](#getautorenderdelay)
 * [toggleBackgroundRender](#togglebackgroundrender)

## API Documentation

### Functions

#### [getAutoRenderDelay](#getautorenderdelay)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`plugins.finalcutpro.timeline.preferences.getAutoRenderDelay() -> number` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the 'FFAutoRenderDelay' value from the Final Cut Pro Preferences file.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>'FFAutoRenderDelay' value as number.</li></ul>          |

#### [toggleBackgroundRender](#togglebackgroundrender)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`plugins.finalcutpro.timeline.preferences.toggleBackgroundRender(optionalValue) -> nil` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Toggles Background Render in Final Cut Pro.                                                                                         |
| **Parameters**                                       | <ul><li>optionalValue - Set the Background Render to `true` or `false`</li></ul> |
| **Returns**                                          | <ul><li>`true` if successful otherwise `false`</li></ul>          |

