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
| **Parameters**                                       |  * button - which button you want to assign.                                       |
| **Returns**                                          |  * None                                                |

#### [choices](#choices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.choices() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Choices for the Assign HUD Button chooser.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * Table                                                |

#### [delete](#delete)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.delete()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Deletes the existing HUD if it exists                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [generateHTML](#generatehtml)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.generateHTML() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Generate the HTML for the HUD.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [getButton](#getbutton)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.getButton() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the button values from settings.                                                                                         |
| **Parameters**                                       |  * index - Index of the Button * defaultValue - Default Value of the Button                                       |
| **Returns**                                          |  * Button value                                                |

#### [getButtonCommand](#getbuttoncommand)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.getButtonCommand() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the button command.                                                                                         |
| **Parameters**                                       |  * index - Index of the Button                                       |
| **Returns**                                          |  * Button Command                                                |

#### [getButtonText](#getbuttontext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.getButtonText() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the button text.                                                                                         |
| **Parameters**                                       |  * index - Index of the Button                                       |
| **Returns**                                          |  * Button Label or Unassigned Value                                                |

#### [getButtonURL](#getbuttonurl)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.getButtonURL() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the button URL.                                                                                         |
| **Parameters**                                       |  * index - Index of the Button                                       |
| **Returns**                                          |  * Button URL                                                |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.hide() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Hide the HUD.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [init](#init)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.init() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Initialise HUD Module.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [javaScriptCallback](#javascriptcallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.javaScriptCallback() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Javascript Callback                                                                                         |
| **Parameters**                                       |  * message - the message for the callback                                       |
| **Returns**                                          |  * None                                                |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.new()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates a new HUD                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [refresh](#refresh)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.refresh() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Refresh the HUD's content.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [setButton](#setbutton)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.setButton() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the button.                                                                                         |
| **Parameters**                                       |  * index - Index of the Button * value - Value you want to set the button to.                                       |
| **Returns**                                          |  * None                                                |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.show() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Show the HUD.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [update](#update)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.update() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Enables or Disables the HUD.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [updateVisibility](#updatevisibility)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.updateVisibility() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Update the visibility of the HUD.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [visible](#visible)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.hud.visible() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Is the HUD visible?                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `true` or `false`                                                |

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

