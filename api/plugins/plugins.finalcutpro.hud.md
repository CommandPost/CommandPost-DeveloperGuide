# [docs](index.md) » plugins.finalcutpro.hud
---

Final Cut Pro HUD.

## API Overview
* Functions - API calls offered directly by the extension
 * [assignButton](#assignbutton)
 * [choices](#choices)
 * [delete](#delete)
 * [generateHTML](#generatehtml)
 * [getButton](#getbutton)
 * [getButtonCommand](#getbuttoncommand)
 * [getButtonText](#getbuttontext)
 * [getButtonURL](#getbuttonurl)
 * [getPosition](#getposition)
 * [hide](#hide)
 * [init](#init)
 * [isButtonsShown](#isbuttonsshown)
 * [isDropTargetsShown](#isdroptargetsshown)
 * [isEnabled](#isenabled)
 * [isInspectorShown](#isinspectorshown)
 * [javaScriptCallback](#javascriptcallback)
 * [new](#new)
 * [refresh](#refresh)
 * [setButton](#setbutton)
 * [setButtonsShown](#setbuttonsshown)
 * [setDropTargetsShown](#setdroptargetsshown)
 * [setEnabled](#setenabled)
 * [setInspectorShown](#setinspectorshown)
 * [setOption](#setoption)
 * [setPosition](#setposition)
 * [show](#show)
 * [toggleEnabled](#toggleenabled)
 * [toggleInspectorShown](#toggleinspectorshown)
 * [updateVisibility](#updatevisibility)
 * [visible](#visible)

## API Documentation

### Functions

#### [assignButton](#assignbutton)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.finalcutpro.hud.assignButton() -> none` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Assigns a HUD button.                                                                                         |
| **Parameters**                                       | <ul><li>button - which button you want to assign.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [choices](#choices)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.finalcutpro.hud.choices() -> none` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Choices for the Assign HUD Button chooser.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Table</li></ul>          |

#### [delete](#delete)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.finalcutpro.hud.delete()` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Deletes the existing HUD if it exists                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [generateHTML](#generatehtml)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.finalcutpro.hud.generateHTML() -> none` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Generate the HTML for the HUD.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [getButton](#getbutton)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.finalcutpro.hud.getButton() -> string` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the button values from settings.                                                                                         |
| **Parameters**                                       | <ul><li>index - Index of the Button</li><li>defaultValue - Default Value of the Button</li></ul> |
| **Returns**                                          | <ul><li>Button value</li></ul>          |

#### [getButtonCommand](#getbuttoncommand)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.finalcutpro.hud.getButtonCommand() -> string` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the button command.                                                                                         |
| **Parameters**                                       | <ul><li>index - Index of the Button</li></ul> |
| **Returns**                                          | <ul><li>Button Command</li></ul>          |

#### [getButtonText](#getbuttontext)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.finalcutpro.hud.getButtonText() -> string` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the button text.                                                                                         |
| **Parameters**                                       | <ul><li>index - Index of the Button</li></ul> |
| **Returns**                                          | <ul><li>Button Label or Unassigned Value</li></ul>          |

#### [getButtonURL](#getbuttonurl)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.finalcutpro.hud.getButtonURL() -> string` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the button URL.                                                                                         |
| **Parameters**                                       | <ul><li>index - Index of the Button</li></ul> |
| **Returns**                                          | <ul><li>Button URL</li></ul>          |

#### [getPosition](#getposition)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.finalcutpro.hud.getPosition() -> table` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the last HUD frame saved in settings.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The last HUD frame or {}.</li></ul>          |

#### [hide](#hide)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.finalcutpro.hud.hide() -> none` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Hide the HUD.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [init](#init)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.finalcutpro.hud.init() -> none` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialise HUD Module.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [isButtonsShown](#isbuttonsshown)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.finalcutpro.hud.isButtonsShown() -> boolean` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Should Buttons in the HUD be shown?                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>`true` or `false`</li></ul>          |

#### [isDropTargetsShown](#isdroptargetsshown)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.finalcutpro.hud.isDropTargetsShown() -> boolean` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Should Drop Targets in the HUD be shown?                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>`true` or `false`</li></ul>          |

#### [isEnabled](#isenabled)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.finalcutpro.hud.isEnabled() -> boolean` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Is the HUD enabled in the settings?                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>`true` if enabled otherwise false</li></ul>          |

#### [isInspectorShown](#isinspectorshown)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.finalcutpro.hud.isInspectorShown() -> boolean` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Should the Inspector in the HUD be shown?                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>`true` or `false`</li></ul>          |

#### [javaScriptCallback](#javascriptcallback)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.finalcutpro.hud.javaScriptCallback() -> none` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Javascript Callback                                                                                         |
| **Parameters**                                       | <ul><li>message - the message for the callback</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [new](#new)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.finalcutpro.hud.new()` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates a new HUD                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [refresh](#refresh)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.finalcutpro.hud.refresh() -> none` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Refresh the HUD's content.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [setButton](#setbutton)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.finalcutpro.hud.setButton() -> string` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the button.                                                                                         |
| **Parameters**                                       | <ul><li>index - Index of the Button</li><li>value - Value you want to set the button to.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [setButtonsShown](#setbuttonsshown)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.finalcutpro.hud.setButtonsShown() -> none` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Set whether or not Buttons should be shown in the HUD.                                                                                         |
| **Parameters**                                       | <ul><li>value - `true` or `false`</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [setDropTargetsShown](#setdroptargetsshown)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.finalcutpro.hud.setDropTargetsShown() -> none` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Set whether or not Drop Targets should be shown in the HUD.                                                                                         |
| **Parameters**                                       | <ul><li>value - `true` or `false`</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [setEnabled](#setenabled)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.finalcutpro.hud.setEnabled() -> none` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets whether or not the HUD is enabled.                                                                                         |
| **Parameters**                                       | <ul><li>value - `true` if HUD should be enabled otherwise `false`</li></ul> |
| **Returns**                                          | <ul><li>`true` if enabled otherwise false</li></ul>          |

#### [setInspectorShown](#setinspectorshown)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.finalcutpro.hud.setInspectorShown() -> none` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Set whether or not the Inspector should be shown in the HUD.                                                                                         |
| **Parameters**                                       | <ul><li>value - `true` or `false`</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [setOption](#setoption)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.finalcutpro.hud.setOption() -> none` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets a HUD option                                                                                         |
| **Parameters**                                       | <ul><li>name - The name of the option</li><li>value - The value of the option</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [setPosition](#setposition)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.finalcutpro.hud.setPosition() -> none` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Saves the HUD position to settings.                                                                                         |
| **Parameters**                                       | <ul><li>value - Position as table</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [show](#show)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.finalcutpro.hud.show() -> none` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Show the HUD.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [toggleEnabled](#toggleenabled)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.finalcutpro.hud.toggleEnabled() -> none` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Toggles the HUD                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [toggleInspectorShown](#toggleinspectorshown)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.finalcutpro.hud.toggleInspectorShown() -> none` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Toggles whether or not Buttons should be shown in the HUD.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [updateVisibility](#updatevisibility)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.finalcutpro.hud.updateVisibility() -> none` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Update the visibility of the HUD.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [visible](#visible)
| <span style="text-align: left;">**Signature**</span> | <span style="text-align: left;">`plugins.finalcutpro.hud.visible() -> none` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Is the HUD visible?                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>`true` or `false`</li></ul>          |

