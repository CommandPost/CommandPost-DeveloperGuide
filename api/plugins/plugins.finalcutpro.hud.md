# [docs](index.md) » plugins.finalcutpro.hud
---

Final Cut Pro HUD.

## API Overview
* Constants - Useful values which cannot be changed
 * [position](#position)
* Functions - API calls offered directly by the extension
 * [assignButton](#assignbutton)
 * [choices](#choices)
 * [delete](#delete)
 * [generateHTML](#generatehtml)
 * [getButton](#getbutton)
 * [getButtonCommand](#getbuttoncommand)
 * [getButtonText](#getbuttontext)
 * [getButtonURL](#getbuttonurl)
 * [hide](#hide)
 * [init](#init)
 * [javaScriptCallback](#javascriptcallback)
 * [new](#new)
 * [refresh](#refresh)
 * [setButton](#setbutton)
 * [show](#show)
 * [update](#update)
 * [updateVisibility](#updatevisibility)
 * [visible](#visible)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [buttonsShown](#buttonsshown)
 * [dropTargetsShown](#droptargetsshown)
 * [enabled](#enabled)
 * [inspectorShown](#inspectorshown)

## API Documentation

### Constants

#### [position](#position)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.position <cp.prop: table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Returns the last HUD frame saved in settings.                                                                                         |

### Functions

#### [assignButton](#assignbutton)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.assignButton() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Assigns a HUD button.                                                                                         |
| **Parameters**                                       | <ul><li>button - which button you want to assign.</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [choices](#choices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.choices() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Choices for the Assign HUD Button chooser.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>Table</li></ul>            |

#### [delete](#delete)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.delete()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Deletes the existing HUD if it exists                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [generateHTML](#generatehtml)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.generateHTML() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Generate the HTML for the HUD.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [getButton](#getbutton)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.getButton() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the button values from settings.                                                                                         |
| **Parameters**                                       | <ul><li>index - Index of the Button</li></ul><ul><li>defaultValue - Default Value of the Button</li></ul>   |
| **Returns**                                          | <ul><li>Button value</li></ul>            |

#### [getButtonCommand](#getbuttoncommand)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.getButtonCommand() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the button command.                                                                                         |
| **Parameters**                                       | <ul><li>index - Index of the Button</li></ul>   |
| **Returns**                                          | <ul><li>Button Command</li></ul>            |

#### [getButtonText](#getbuttontext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.getButtonText() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the button text.                                                                                         |
| **Parameters**                                       | <ul><li>index - Index of the Button</li></ul>   |
| **Returns**                                          | <ul><li>Button Label or Unassigned Value</li></ul>            |

#### [getButtonURL](#getbuttonurl)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.getButtonURL() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the button URL.                                                                                         |
| **Parameters**                                       | <ul><li>index - Index of the Button</li></ul>   |
| **Returns**                                          | <ul><li>Button URL</li></ul>            |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.hide() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Hide the HUD.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.init() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialise HUD Module.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [javaScriptCallback](#javascriptcallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.javaScriptCallback() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Javascript Callback                                                                                         |
| **Parameters**                                       | <ul><li>message - the message for the callback</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.new()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates a new HUD                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [refresh](#refresh)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.refresh() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Refresh the HUD's content.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [setButton](#setbutton)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.setButton() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the button.                                                                                         |
| **Parameters**                                       | <ul><li>index - Index of the Button</li></ul><ul><li>value - Value you want to set the button to.</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.show() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Show the HUD.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.update() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Enables or Disables the HUD.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [updateVisibility](#updatevisibility)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.updateVisibility() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Update the visibility of the HUD.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [visible](#visible)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.visible() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Is the HUD visible?                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li><code>true</code> or <code>false</code></li></ul>            |

### Fields

#### [buttonsShown](#buttonsshown)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.buttonsShown <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Should Buttons in the HUD be shown?                                                                                         |

#### [dropTargetsShown](#droptargetsshown)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.dropTargetsShown <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Should Drop Targets in the HUD be enabled?                                                                                         |

#### [enabled](#enabled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.enabled <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Is the HUD enabled in the settings?                                                                                         |

#### [inspectorShown](#inspectorshown)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.inspectorShown <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Should the Inspector in the HUD be shown?                                                                                         |

