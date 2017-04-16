# Plugin Overview

CommandPost has a very easy to use and powerful plugins functionality, and because Lua is quite a simple language to use, it's really easy to throw together your own CommandPost Plugins!

---

## Plugins Location

CommandPost will load any 3rd Party Plugins located in:

`~/Application Support/CommandPost/Plugins`

Internally, all the user interface and features for CommandPost are also plugins. They are automatically loaded from:

`CommandPost.app/Contents/Resources/plugins/`

This means if you build a plugin that's really awesome, it's very easily to add it to the main CommandPost Application when it's ready.

---

## Plugins Structure

A CommandPost Plugin is simply a macOS bundle which contains Lua scripts (and any other resources you want to throw in it).

When you first run CommandPost it will register the `.cpPlugin` extension in macOS, which means if you create a folder called `SOMETHING.cpPlugin` it will prompt you with:

![CommandPost Plugin](images/cpplugin.png)

If you click **Add** it will turn that newly created folder into a CommandPost Plugin Bundle.

You view the contents of the bundle, simply right click and select **Show Package Contents**.

![Show Package Contents](images/show-package-contents.png)

At a very minimum, the plugin should contain a single `.lua` file, which will be the Lua code that's executed.

CommandPost Plugins can either be pure Lua or a mixture of Lua and Objective-C (although since they are just dynamically loaded libraries, they could ultimately be compiled in almost any language such as [Swift](https://developer.apple.com/swift/).

--

## Example Plugin

Below is a simple Plugin example that adds a button to the very bottom of the CommandPost menubar, and when click it displays the CommandPost version in a dialog box.

* To make things easy for others to understand, and to help with automatic documentation generation, we recommend you use [these naming conventions](https://dev.commandpost.io/naming_conventions.html) when building your own plugins.
* You can learn more about the plugins API [here](https://dev.commandpost.io/api/cp/cp.plugins.html).
* You can learn more about `cp.config` [here](https://dev.commandpost.io/api/cp/cp.config.html).

```lua
--------------------------------------------------------------------------------
--------------------------------------------------------------------------------
--                               E X A M P L E                                --
--------------------------------------------------------------------------------
--------------------------------------------------------------------------------

--- === plugins.core.example ===
---
--- An example plugin.

--------------------------------------------------------------------------------
--
-- EXTENSIONS:
--
--------------------------------------------------------------------------------
local config			= require("cp.config")
local dialog			= require("cp.dialog")

--------------------------------------------------------------------------------
--
-- THE MODULE:
--
--------------------------------------------------------------------------------
local mod = {}

--- plugins.core.example.displayVersion() -> nil
--- Function
--- Displays a Dialog Box that displays the CommandPost Version.
---
--- Parameters:
---  * None
---
--- Returns:
---  * None
function mod.displayVersion()
	dialog.displayMessage("The CommandPost Version is: " .. config.appVersion)
end

--------------------------------------------------------------------------------
--
-- THE PLUGIN:
--
--------------------------------------------------------------------------------
local plugin = {
	id				= "core.example",
	group			= "core",
	dependencies	= {
		["core.menu.bottom"] = "bottom",
	}
}

--------------------------------------------------------------------------------
-- INITIALISE PLUGIN:
--------------------------------------------------------------------------------
function plugin.init(deps)
	deps.bottom:addSeparator(9999999999):addItem(99999999999, function()
		return { title = "Example Menu Item",	fn = mod.displayVersion }
	end)

	return mod
end

return plugin
```