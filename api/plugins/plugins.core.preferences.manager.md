# [docs](index.md) » plugins.core.preferences.manager
---

Manager for the CommandPost Preferences Panel.

## Submodules
 * [plugins.core.preferences.manager.panel](plugins.core.preferences.manager.panel.md)

## API Overview
* Functions - API calls offered directly by the extension
 * [addPanel](#addPanel)
 * [init](#init)
 * [showPreferences](#showPreferences)

## API Documentation

### Functions

| [addPanel](#addPanel)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.preferences.manager.addPanel(params) -> plugins.core.preferences.manager.panel`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Adds a new panel with the specified `params` to the preferences manager.                                                                     |
| **Parameters**                              | <ul><li>`params`	- The parameters table. Details below.</li></ul> |
| **Returns**                                 | <ul><li>The new `panel` instance.</li></ul>          |
| **Notes**                                   | <ul><li>The `params` can have the following properties. The `priority` and `id` and properties are **required**.</li><li> ** `priority`		- An integer value specifying the priority of the panel compared to others.</li><li> ** `id`			- A string containing the unique ID of the panel.</li><li> ** `label`			- The human-readable label for the panel icon.</li><li>	 ** `image`			- The `hs.image` for the panel icon.</li><li> ** `tooltip`		- The human-readable details for the toolbar icon when the mouse is hovering over it.</li></ul>                |

| [init](#init)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.preferences.manager.init() -> nothing`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Initialises the preferences panel.                                                                     |
| **Parameters**                              | <ul><li>* None</li></ul> |
| **Returns**                                 | <ul><li>* Nothing</li></ul>          |

| [showPreferences](#showPreferences)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.preferences.manager.showPreferences() -> boolean`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Shows the Preferences Window                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>True if successful or nil if an error occurred</li></ul>          |

