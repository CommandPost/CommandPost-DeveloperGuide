# [docs](index.md) » hs.ipc
---

Provides the server portion of the Hammerspoon command line interface
Note that in order to use the command line tool, you will need to explicitly load `hs.ipc` in your init.lua. The simplest way to do that is `require("hs.ipc")`

This module is based primarily on code from Mjolnir by [Steven Degutis](https://github.com/sdegutis/).

## API Overview
* Commands - External shell commands
 * [cli](#cli)
* Functions - API calls offered directly by the extension
 * [cliGetColors](#cliGetColors)
 * [cliInstall](#cliInstall)
 * [cliResetColors](#cliResetColors)
 * [cliSetColors](#cliSetColors)
 * [cliStatus](#cliStatus)
 * [cliUninstall](#cliUninstall)
 * [handler](#handler)

## API Documentation

### Commands

| #### [cli](#cli)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.ipc.cli                                                            |
| **Type**                                    | Command                                                           |
| **Description**                             | This documents the external shell command `hs` provided by the hs.ipc module for external access to and control of your `Hammerspoon` environment.                                                           |

### Functions

| #### [cliGetColors](#cliGetColors)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.ipc.cliGetColors() -> table                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Gets the terminal escape codes used to produce colors in the `hs` command line tool                                                           |
| **Parameters**                              |  * None         |
| **Returns**                                 |  * A table containing the terminal escape codes used to produce colors. The available keys are:  * initial  * input  * output                  |

| #### [cliInstall](#cliInstall)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.ipc.cliInstall([path][,silent]) -> bool                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Installs the `hs` command line tool                                                           |
| **Parameters**                              |  * path - An optional string containing a path to install the tool in. Defaults to `/usr/local` * silent - An optional boolean indicating whether or not to print errors to the Hammerspoon Console         |
| **Returns**                                 |  * A boolean, true if the tool was successfully installed, otherwise false                  |

| #### [cliResetColors](#cliResetColors)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.ipc.cliResetColors()                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Restores default terminal escape codes used to produce colors in the `hs` command line tool                                                           |
| **Parameters**                              |  * None         |
| **Returns**                                 |  * None                  |

| #### [cliSetColors](#cliSetColors)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.ipc.cliSetColors(table) -> table                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Sets the terminal escape codes used to produce colors in the `hs` command line tool                                                           |
| **Parameters**                              |  * table - A table of terminal escape sequences (or empty strings if you wish to suppress the usage of colors) containing the following keys:  * initial  * input  * output         |
| **Returns**                                 |  * A table containing the terminal escape codes that have been set. The available keys match the table parameter.                  |
| **Notes**                                   |  * For a brief intro into terminal colors, you can visit a web site like this one [http://jafrog.com/2013/11/23/colors-in-terminal.html](http://jafrog.com/2013/11/23/colors-in-terminal.html) * Lua doesn't support octal escapes in it's strings, so use `\x1b` or `\27` to indicate the `escape` character e.g. `ipc.cliSetColors{ initial = "", input = "\27[33m", output = "\27[38;5;11m" }` * The values are stored by the `hs.settings` extension, so will persist across restarts of Hammerspoon                        |

| #### [cliStatus](#cliStatus)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.ipc.cliStatus([path][,silent]) -> bool                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Gets the status of the `hs` command line tool                                                           |
| **Parameters**                              |  * path - An optional string containing a path to look for the `hs` tool. Defaults to `/usr/local` * silent - An optional boolean indicating whether or not to print errors to the Hammerspoon Console         |
| **Returns**                                 |  * A boolean, true if the `hs` command line tool is correctly installed, otherwise false                  |

| #### [cliUninstall](#cliUninstall)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.ipc.cliUninstall([path][,silent]) -> bool                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Uninstalls the `hs` command line tool                                                           |
| **Parameters**                              |  * path - An optional string containing a path to remove the tool from. Defaults to `/usr/local` * silent - An optional boolean indicating whether or not to print errors to the Hammerspoon Console         |
| **Returns**                                 |  * A boolean, true if the tool was successfully removed, otherwise false                  |
| **Notes**                                   |  * This function is very conservative and will only remove the tool if it was installed by this instance of Hammerspoon. If you have more than one copy of Hammerspoon, this will be detected and they will not remove each others' tools.                        |

| #### [handler](#handler)    |                                                                           |
| --------------------------------------------|---------------------------------------------------------------------------|
| **Signature**                               | hs.ipc.handler(str) -> value                                                            |
| **Type**                                    | Function                                                           |
| **Description**                             | Processes received IPC messages and returns the results                                                           |
| **Parameters**                              |  * str - A string containing some a message to process (typically, some Lua code)         |
| **Returns**                                 |  * A string containing the results of the IPC message                  |
| **Notes**                                   |  * This is not a function you should typically call directly, rather, it is documented because you can override it with your own function if you have particular IPC needs. * The return value of this function is always turned into a string via `lua_tostring()` and returned to the IPC client (typically the `hs` command line tool) * The default handler is:~~~    function hs.ipc.handler(str)        local fn, err = load("return " .. str)        if not fn then fn, err = load(str) end        if fn then return fn() else return err end    end~~~                        |

