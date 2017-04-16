# [docs](index.md) » plugins.finalcutpro.hud
---

Final Cut Pro HUD.

## API Overview
* Functions - API calls offered directly by the extension
 * [assignButton](#assignButton)
 * [choices](#choices)
 * [delete](#delete)
 * [generateHTML](#generateHTML)
 * [getButton](#getButton)
 * [getButtonCommand](#getButtonCommand)
 * [getButtonText](#getButtonText)
 * [getButtonURL](#getButtonURL)
 * [getPosition](#getPosition)
 * [hide](#hide)
 * [init](#init)
 * [isButtonsShown](#isButtonsShown)
 * [isDropTargetsShown](#isDropTargetsShown)
 * [isEnabled](#isEnabled)
 * [isInspectorShown](#isInspectorShown)
 * [javaScriptCallback](#javaScriptCallback)
 * [new](#new)
 * [refresh](#refresh)
 * [setButton](#setButton)
 * [setButtonsShown](#setButtonsShown)
 * [setDropTargetsShown](#setDropTargetsShown)
 * [setEnabled](#setEnabled)
 * [setInspectorShown](#setInspectorShown)
 * [setOption](#setOption)
 * [setPosition](#setPosition)
 * [show](#show)
 * [toggleEnabled](#toggleEnabled)
 * [toggleInspectorShown](#toggleInspectorShown)
 * [updateVisibility](#updateVisibility)
 * [visible](#visible)

## API Documentation

### Functions

| [assignButton](#assignButton)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hud.assignButton() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Assigns a HUD button.                                                                     |
| **Parameters**                              | <ul><li>button - which button you want to assign.</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |

| [choices](#choices)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hud.choices() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Choices for the Assign HUD Button chooser.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>Table</li></ul>          |

| [delete](#delete)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hud.delete()`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Deletes the existing HUD if it exists                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |

| [generateHTML](#generateHTML)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hud.generateHTML() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Generate the HTML for the HUD.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |

| [getButton](#getButton)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hud.getButton() -> string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Gets the button values from settings.                                                                     |
| **Parameters**                              | <ul><li>index - Index of the Button</li><li>defaultValue - Default Value of the Button</li></ul> |
| **Returns**                                 | <ul><li>Button value</li></ul>          |

| [getButtonCommand](#getButtonCommand)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hud.getButtonCommand() -> string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Gets the button command.                                                                     |
| **Parameters**                              | <ul><li>index - Index of the Button</li></ul> |
| **Returns**                                 | <ul><li>Button Command</li></ul>          |

| [getButtonText](#getButtonText)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hud.getButtonText() -> string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Gets the button text.                                                                     |
| **Parameters**                              | <ul><li>index - Index of the Button</li></ul> |
| **Returns**                                 | <ul><li>Button Label or Unassigned Value</li></ul>          |

| [getButtonURL](#getButtonURL)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hud.getButtonURL() -> string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Gets the button URL.                                                                     |
| **Parameters**                              | <ul><li>index - Index of the Button</li></ul> |
| **Returns**                                 | <ul><li>Button URL</li></ul>          |

| [getPosition](#getPosition)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hud.getPosition() -> table`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the last HUD frame saved in settings.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The last HUD frame or {}.</li></ul>          |

| [hide](#hide)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hud.hide() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Hide the HUD.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |

| [init](#init)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hud.init() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Initialise HUD Module.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |

| [isButtonsShown](#isButtonsShown)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hud.isButtonsShown() -> boolean`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Should Buttons in the HUD be shown?                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>`true` or `false`</li></ul>          |

| [isDropTargetsShown](#isDropTargetsShown)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hud.isDropTargetsShown() -> boolean`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Should Drop Targets in the HUD be shown?                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>`true` or `false`</li></ul>          |

| [isEnabled](#isEnabled)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hud.isEnabled() -> boolean`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Is the HUD enabled in the settings?                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>`true` if enabled otherwise false</li></ul>          |

| [isInspectorShown](#isInspectorShown)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hud.isInspectorShown() -> boolean`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Should the Inspector in the HUD be shown?                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>`true` or `false`</li></ul>          |

| [javaScriptCallback](#javaScriptCallback)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hud.javaScriptCallback() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Javascript Callback                                                                     |
| **Parameters**                              | <ul><li>message - the message for the callback</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |

| [new](#new)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hud.new()`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Creates a new HUD                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |

| [refresh](#refresh)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hud.refresh() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Refresh the HUD's content.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |

| [setButton](#setButton)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hud.setButton() -> string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Sets the button.                                                                     |
| **Parameters**                              | <ul><li>index - Index of the Button</li><li>value - Value you want to set the button to.</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |

| [setButtonsShown](#setButtonsShown)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hud.setButtonsShown() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Set whether or not Buttons should be shown in the HUD.                                                                     |
| **Parameters**                              | <ul><li>value - `true` or `false`</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |

| [setDropTargetsShown](#setDropTargetsShown)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hud.setDropTargetsShown() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Set whether or not Drop Targets should be shown in the HUD.                                                                     |
| **Parameters**                              | <ul><li>value - `true` or `false`</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |

| [setEnabled](#setEnabled)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hud.setEnabled() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Sets whether or not the HUD is enabled.                                                                     |
| **Parameters**                              | <ul><li>value - `true` if HUD should be enabled otherwise `false`</li></ul> |
| **Returns**                                 | <ul><li>`true` if enabled otherwise false</li></ul>          |

| [setInspectorShown](#setInspectorShown)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hud.setInspectorShown() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Set whether or not the Inspector should be shown in the HUD.                                                                     |
| **Parameters**                              | <ul><li>value - `true` or `false`</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |

| [setOption](#setOption)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hud.setOption() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Sets a HUD option                                                                     |
| **Parameters**                              | <ul><li>name - The name of the option</li><li>value - The value of the option</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |

| [setPosition](#setPosition)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hud.setPosition() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Saves the HUD position to settings.                                                                     |
| **Parameters**                              | <ul><li>value - Position as table</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |

| [show](#show)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hud.show() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Show the HUD.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |

| [toggleEnabled](#toggleEnabled)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hud.toggleEnabled() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Toggles the HUD                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |

| [toggleInspectorShown](#toggleInspectorShown)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hud.toggleInspectorShown() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Toggles whether or not Buttons should be shown in the HUD.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |

| [updateVisibility](#updateVisibility)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hud.updateVisibility() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Update the visibility of the HUD.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |

| [visible](#visible)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.hud.visible() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Is the HUD visible?                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>`true` or `false`</li></ul>          |

