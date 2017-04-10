# [docs](index.md) » hs
---

Core Hammerspoon functionality

## Submodules
 * [hs.alert](hs.alert.md)
 * [hs.appfinder](hs.appfinder.md)
 * [hs.applescript](hs.applescript.md)
 * [hs.application](hs.application.md)
 * [hs.audiodevice](hs.audiodevice.md)
 * [hs.base64](hs.base64.md)
 * [hs.battery](hs.battery.md)
 * [hs.brightness](hs.brightness.md)
 * [hs.caffeinate](hs.caffeinate.md)
 * [hs.canvas](hs.canvas.md)
 * [hs.chooser](hs.chooser.md)
 * [hs.console](hs.console.md)
 * [hs.crash](hs.crash.md)
 * [hs.deezer](hs.deezer.md)
 * [hs.distributednotifications](hs.distributednotifications.md)
 * [hs.doc](hs.doc.md)
 * [hs.dockicon](hs.dockicon.md)
 * [hs.drawing](hs.drawing.md)
 * [hs.eventtap](hs.eventtap.md)
 * [hs.expose](hs.expose.md)
 * [hs.fnutils](hs.fnutils.md)
 * [hs.fs](hs.fs.md)
 * [hs.geometry](hs.geometry.md)
 * [hs.grid](hs.grid.md)
 * [hs.hash](hs.hash.md)
 * [hs.hints](hs.hints.md)
 * [hs.host](hs.host.md)
 * [hs.hotkey](hs.hotkey.md)
 * [hs.http](hs.http.md)
 * [hs.httpserver](hs.httpserver.md)
 * [hs.image](hs.image.md)
 * [hs.inspect](hs.inspect.md)
 * [hs.ipc](hs.ipc.md)
 * [hs.itunes](hs.itunes.md)
 * [hs.javascript](hs.javascript.md)
 * [hs.json](hs.json.md)
 * [hs.keycodes](hs.keycodes.md)
 * [hs.layout](hs.layout.md)
 * [hs.location](hs.location.md)
 * [hs.logger](hs.logger.md)
 * [hs.menubar](hs.menubar.md)
 * [hs.messages](hs.messages.md)
 * [hs.milight](hs.milight.md)
 * [hs.mjomatic](hs.mjomatic.md)
 * [hs.mouse](hs.mouse.md)
 * [hs.network](hs.network.md)
 * [hs.noises](hs.noises.md)
 * [hs.notify](hs.notify.md)
 * [hs.osascript](hs.osascript.md)
 * [hs.pasteboard](hs.pasteboard.md)
 * [hs.pathwatcher](hs.pathwatcher.md)
 * [hs.redshift](hs.redshift.md)
 * [hs.screen](hs.screen.md)
 * [hs.settings](hs.settings.md)
 * [hs.sharing](hs.sharing.md)
 * [hs.socket](hs.socket.md)
 * [hs.sound](hs.sound.md)
 * [hs.spaces](hs.spaces.md)
 * [hs.speech](hs.speech.md)
 * [hs.spotify](hs.spotify.md)
 * [hs.spotlight](hs.spotlight.md)
 * [hs.sqlite3](hs.sqlite3.md)
 * [hs.styledtext](hs.styledtext.md)
 * [hs.tabs](hs.tabs.md)
 * [hs.task](hs.task.md)
 * [hs.timer](hs.timer.md)
 * [hs.uielement](hs.uielement.md)
 * [hs.urlevent](hs.urlevent.md)
 * [hs.usb](hs.usb.md)
 * [hs.utf8](hs.utf8.md)
 * [hs.vox](hs.vox.md)
 * [hs.watchable](hs.watchable.md)
 * [hs.webview](hs.webview.md)
 * [hs.wifi](hs.wifi.md)
 * [hs.window](hs.window.md)

## API Overview
* Constants - Useful values which cannot be changed
** [configdir](#configdir)
** [docstrings_json_file](#docstrings_json_file)
** [processInfo](#processInfo)
* Variables - Configurable values
** [accessibilityStateCallback](#accessibilityStateCallback)
** [completionsForInputString](#completionsForInputString)
** [shutdownCallback](#shutdownCallback)
* Functions - API calls offered directly by the extension
** [accessibilityState](#accessibilityState)
** [autoLaunch](#autoLaunch)
** [automaticallyCheckForUpdates](#automaticallyCheckForUpdates)
** [canCheckForUpdates](#canCheckForUpdates)
** [checkForUpdates](#checkForUpdates)
** [cleanUTF8forConsole](#cleanUTF8forConsole)
** [consoleOnTop](#consoleOnTop)
** [dockIcon](#dockIcon)
** [execute](#execute)
** [focus](#focus)
** [getObjectMetatable](#getObjectMetatable)
** [help](#help)
** [hsdocs](#hsdocs)
** [loadSpoon](#loadSpoon)
** [menuIcon](#menuIcon)
** [openAbout](#openAbout)
** [openConsole](#openConsole)
** [openPreferences](#openPreferences)
** [printf](#printf)
** [rawprint](#rawprint)
** [reload](#reload)
** [showError](#showError)
** [toggleConsole](#toggleConsole)
** [updateAvailable](#updateAvailable)
** [uploadCrashData](#uploadCrashData)

## API Documentation

### Constants

#### [configdir](#configdir)
| | |
|-|-|
| Signature   | hs.configdir  |
| Type        | Constant |
| Description | A string containing Hammerspoon's configuration directory. Typically `~/.hammerspoon/` |

#### [docstrings_json_file](#docstrings_json_file)
| | |
|-|-|
| Signature   | hs.docstrings_json_file  |
| Type        | Constant |
| Description | A string containing the full path to the `docs.json` file inside Hammerspoon's app bundle. This contains the full Hammerspoon API documentation and can be accessed in the Console using `help("someAPI")`. It can also be loaded and processed by the `hs.doc` extension |

#### [processInfo](#processInfo)
| | |
|-|-|
| Signature   | hs.processInfo  |
| Type        | Constant |
| Description | A table containing read-only information about the Hammerspoon application instance currently running. |

### Variables

#### [accessibilityStateCallback](#accessibilityStateCallback)
| | |
|-|-|
| Signature   | hs.accessibilityStateCallback  |
| Type        | Variable |
| Description | An optional function that will be called when the Accessibility State is changed. |
| Notes | * The function will not receive any arguments when called.  To check what the accessibility state has been changed to, you should call [hs.accessibilityState](#accessibilityState) from within your function. | 
#### [completionsForInputString](#completionsForInputString)
| | |
|-|-|
| Signature   | hs.completionsForInputString(completionWord) -> table of strings  |
| Type        | Variable |
| Description | Gathers tab completion options for the Console window |
| Parameters |  * completionWord - A string from the Console window's input field that completions are needed for | | Returns |  * A table of strings, each of which will be shown as a possible completion option to the user | | Notes |  * Hammerspoon provides a default implementation of this function, which can complete against the global Lua namespace, the 'hs' (i.e. extension) namespace, and object metatables. You can assign a new function to the variable to replace it with your own variant. | 
#### [shutdownCallback](#shutdownCallback)
| | |
|-|-|
| Signature   | hs.shutdownCallback  |
| Type        | Variable |
| Description | An optional function that will be called when the Lua environment is being destroyed (either because Hammerspoon is exiting or reloading its config) |
| Notes |  * This function should not perform any asynchronous tasks * You do not need to fastidiously destroy objects you have created, this callback exists purely for utility reasons (e.g. serialising state, destroying system resources that will not be released by normal Lua garbage collection processes, etc) | 
### Functions

#### [accessibilityState](#accessibilityState)
| | |
|-|-|
| Signature   | hs.accessibilityState(shouldPrompt) -> isEnabled  |
| Type        | Function |
| Description |  |
| Parameters |  * shouldPrompt - an optional boolean value indicating if the dialog box asking if the System Preferences application should be opened should be presented when Accessibility is not currently enabled for Hammerspoon.  Defaults to false. | | Returns |  * True or False indicating whether or not Accessibility is enabled for Hammerspoon. | | Notes |  * Since this check is done automatically when Hammerspoon loads, it is probably of limited use except for skipping things that are known to fail when Accessibility is not enabled.  Evettaps which try to capture keyUp and keyDown events, for example, will fail until Accessibility is enabled and the Hammerspoon application is relaunched. | 
#### [autoLaunch](#autoLaunch)
| | |
|-|-|
| Signature   | hs.autoLaunch([state]) -> bool  |
| Type        | Function |
| Description | Set or display the "Launch on Login" status for Hammerspoon. |
| Parameters |  * state - an optional boolean which will set whether or not Hammerspoon should be launched automatically when you log into your computer. | | Returns |  * True if Hammerspoon is currently (or has just been) set to launch on login or False if Hammerspoon is not. | 
#### [automaticallyCheckForUpdates](#automaticallyCheckForUpdates)
| | |
|-|-|
| Signature   | hs.automaticallyCheckForUpdates([setting]) -> bool  |
| Type        | Function |
| Description | Gets and optionally sets the Hammerspoon option to automatically check for updates. |
| Parameters |  * setting - an optional boolean variable indicating if Hammerspoon should (true) or should not (false) check for updates. | | Returns |  * The current (or newly set) value indicating whether or not automatic update checks should occur for Hammerspoon. | | Notes |  * If you are running a non-release or locally compiled version of Hammerspoon then the results of this function are unspecified. | 
#### [canCheckForUpdates](#canCheckForUpdates)
| | |
|-|-|
| Signature   | hs.canCheckForUpdates() -> boolean  |
| Type        | Function |
| Description | Returns a boolean indicating whether or not the Sparkle framework is available to check for Hammerspoon updates. |
| Parameters |  * None | | Returns |  * a boolean indicating whether or not the Sparkle framework is available to check for Hammerspoon updates | | Notes |  * The Sparkle framework is included in all regular releases of Hammerspoon but not included if you are running a non-release or locally compiled version of Hammerspoon, so this function can be used as a simple test to determine whether or not you are running a formal release Hammerspoon or not. | 
#### [checkForUpdates](#checkForUpdates)
| | |
|-|-|
| Signature   | hs.checkForUpdates([silent]) -> none  |
| Type        | Function |
| Description | Check for an update now, and if one is available, prompt the user to continue the update process. |
| Parameters |  * silent - An optional boolean. If true, no UI will be displayed if an update is available. Defaults to false. | | Returns |  * None | | Notes |  * If you are running a non-release or locally compiled version of Hammerspoon then the results of this function are unspecified. | 
#### [cleanUTF8forConsole](#cleanUTF8forConsole)
| | |
|-|-|
| Signature   | hs.cleanUTF8forConsole(inString) -> outString  |
| Type        | Function |
| Description | Returns a copy of the incoming string that can be displayed in the Hammerspoon console.  Invalid UTF8 sequences are converted to the Unicode Replacement Character and NULL (0x00) is converted to the Unicode Empty Set character. |
| Parameters |  * inString - the string to be cleaned up | | Returns |  * outString - the cleaned up version of the input string. | | Notes |  * This function is applied automatically to all output which appears in the Hammerspoon console, but not to the output provided by the `hs` command line tool. * This function does not modify the original string - to actually replace it, assign the result of this function to the original string. * This function is a more specifically targeted version of the `hs.utf8.fixUTF8(...)` function. | 
#### [consoleOnTop](#consoleOnTop)
| | |
|-|-|
| Signature   | hs.consoleOnTop([state]) -> bool  |
| Type        | Function |
| Description | Set or display whether or not the Hammerspoon console is always on top when visible. |
| Parameters |  * state - an optional boolean which will set whether or not the Hammerspoon console is always on top when visible. | | Returns |  * True if the console is currently set (or has just been) to be always on top when visible or False if it is not. | 
#### [dockIcon](#dockIcon)
| | |
|-|-|
| Signature   | hs.dockIcon([state]) -> bool  |
| Type        | Function |
| Description | Set or display whether or not the Hammerspoon dock icon is visible. |
| Parameters |  * state - an optional boolean which will set whether or not the Hammerspoon dock icon should be visible. | | Returns |  * True if the icon is currently set (or has just been) to be visible or False if it is not. | | Notes |  * This function is a wrapper to functions found in the `hs.dockicon` module, but is provided here to provide an interface consistent with other selectable preference items. | 
#### [execute](#execute)
| | |
|-|-|
| Signature   | hs.execute(command[, with_user_env]) -> output, status, type, rc  |
| Type        | Function |
| Description | Runs a shell command, optionally loading the users shell environment first, and returns stdout as a string, followed by the same result codes as `os.execute` would return. |
| Parameters |  * command - a string containing the shell command to execute * with_user_env - optional boolean argument which if provided and is true, executes the command in the users login shell as an "interactive" login shell causing the user's local profile (or other login scripts) to be loaded first. | | Returns |  * output -- the stdout of the command as a string.  May contain an extra terminating new-line (\n). * status -- `true` if the command terminated successfully or nil otherwise. * type   -- a string value of "exit" or "signal" indicating whether the command terminated of its own accord or if it was terminated by a signal (killed, segfault, etc.) * rc     -- if the command exited of its own accord, then this number will represent the exit code (usually 0 for success, not 0 for an error, though this is very command specific, so check man pages when there is a question).  If the command was killed by a signal, then this number corresponds to the signal type that caused the command to terminate. | | Notes |  * Setting `with_user_env` to true does incur noticeable overhead, so it should only be used if necessary (to set the path or other environment variables). * Because this function returns the stdout as it's first return value, it is not quite a drop-in replacement for `os.execute`.  In most cases, it is probable that `stdout` will be the empty string when `status` is nil, but this is not guaranteed, so this trade off of shifting os.execute's results was deemed acceptable. * This particular function is most useful when you're more interested in the command's output then a simple check for completion and result codes.  If you only require the result codes or verification of command completion, then `os.execute` will be slightly more efficient. | 
#### [focus](#focus)
| | |
|-|-|
| Signature   | hs.focus()  |
| Type        | Function |
| Description | Makes Hammerspoon the foreground app. |

#### [getObjectMetatable](#getObjectMetatable)
| | |
|-|-|
| Signature   | hs.getObjectMetatable(name) -> table or nil  |
| Type        | Function |
| Description | Fetches the Lua metatable for objects produced by an extension |
| Parameters |  * name - A string containing the name of a module to fetch object metadata for (e.g. `"hs.screen"`) | | Returns |  * The extension's object metatable, or nil if an error occurred | 
#### [help](#help)
| | |
|-|-|
| Signature   | hs.help(identifier)  |
| Type        | Function |
| Description | Prints the documentation for some part of Hammerspoon's API and Lua 5.3.  This function is actually sourced from hs.doc.help. |
| Parameters |  * identifier - A string containing the signature of some part of Hammerspoon's API (e.g. `"hs.reload"`) | | Returns |  * None | | Notes |  * This function is mainly for runtime API help while using Hammerspoon's Console * You can also access the results of this function by the following methods from the console:   * help("identifier") -- quotes are required, e.g. `help("hs.reload")`   * help.identifier.path -- no quotes are required, e.g. `help.hs.reload` * Lua information can be accessed by using the `lua` prefix, rather than `hs`.   * the identifier `lua._man` provides the table of contents for the Lua 5.3 manual.  You can pull up a specific section of the lua manual by including the chapter (and subsection) like this: `lua._man._3_4_8`.   * the identifier `lua._C` will provide information specifically about the Lua C API for use when developing modules which require external libraries. | 
#### [hsdocs](#hsdocs)
| | |
|-|-|
| Signature   | hs.hsdocs([identifier])  |
| Type        | Function |
| Description | Display's Hammerspoon API documentation in a webview browser. |
| Parameters |  * identifier - An optional string containing the signature of some part of Hammerspoon's API (e.g. `"hs.reload"`).  If no string is provided, then the table of contents for the Hammerspoon documentation is displayed. | | Returns |  * None | | Notes |  * You can also access the results of this function by the following methods from the console:   * hs.hsdocs.identifier.path -- no quotes are required, e.g. `hs.hsdocs.hs.reload` * See `hs.doc.hsdocs` for more information about the available settings for the documentation browser. * This function provides documentation for Hammerspoon modules, functions, and methods similar to the Hammerspoon Dash docset, but does not require any additional software. * This currently only provides documentation for the built in Hammerspoon modules, functions, and methods.  The Lua documentation and third-party modules are not presently supported, but may be added in a future release. | 
#### [loadSpoon](#loadSpoon)
| | |
|-|-|
| Signature   | hs.loadSpoon(name[, global]) -> Spoon object  |
| Type        | Function |
| Description | Loads a Spoon |
| Parameters |  * name - The name of a Spoon (without the trailing `.spoon`) * global - An optional boolean. If true, this function will insert the spoon into Lua's global namespace as `spoon.name`. Defaults to true. | | Returns |  * The object provided by the Spoon (which can be ignored if you chose to make the Spoon global) | | Notes |  * Spoons are a way of distributing self-contained units of Lua functionality, for Hammerspoon. For more information, see https://github.com/Hammerspoon/hammerspoon/blob/master/SPOON.md * This function will load the Spoon and call its `:init()` method if it has one. If you do not wish this to happen, or wish to use a Spoon that somehow doesn't fit with the behaviours of this function, you can also simply `require('name')` to load the Spoon * If the Spoon provides documentation, it will be loaded by made available in hs.docs * To learn how to distribute your own code as a Spoon, see https://github.com/Hammerspoon/hammerspoon/blob/master/SPOON.md | 
#### [menuIcon](#menuIcon)
| | |
|-|-|
| Signature   | hs.menuIcon([state]) -> bool  |
| Type        | Function |
| Description | Set or display whether or not the Hammerspoon menu icon is visible. |
| Parameters |  * state - an optional boolean which will set whether or not the Hammerspoon menu icon should be visible. | | Returns |  * True if the icon is currently set (or has just been) to be visible or False if it is not. | 
#### [openAbout](#openAbout)
| | |
|-|-|
| Signature   | hs.openAbout()  |
| Type        | Function |
| Description | Displays the OS X About panel for Hammerspoon; implicitly focuses Hammerspoon. |

#### [openConsole](#openConsole)
| | |
|-|-|
| Signature   | hs.openConsole([bringToFront])  |
| Type        | Function |
| Description | Opens the Hammerspoon Console window and optionally focuses it. |
| Parameters |  * bringToFront - if true (default), the console will be focused as well as opened. | 
#### [openPreferences](#openPreferences)
| | |
|-|-|
| Signature   | hs.openPreferences()  |
| Type        | Function |
| Description | Displays the Hammerspoon Preferences panel; implicitly focuses Hammerspoon. |

#### [printf](#printf)
| | |
|-|-|
| Signature   | hs.printf(format, ...)  |
| Type        | Function |
| Description | Prints formatted strings to the Console |
| Parameters |  * format - A format string * ... - Zero or more arguments to fill the placeholders in the format string | | Returns |  * None | | Notes |  * This is a simple wrapper around the Lua code `print(string.format(...))`. | 
#### [rawprint](#rawprint)
| | |
|-|-|
| Signature   | hs.rawprint(aString)  |
| Type        | Function |
| Description | The original Lua print() function |
| Parameters |  * aString - A string to be printed | | Returns |  * None | | Notes |  * Hammerspoon overrides Lua's print() function, but this is a reference we retain to is, should you need it for any reason | 
#### [reload](#reload)
| | |
|-|-|
| Signature   | hs.reload()  |
| Type        | Function |
| Description | Reloads your init-file in a fresh Lua environment. |

#### [showError](#showError)
| | |
|-|-|
| Signature   | hs.showError(err)  |
| Type        | Function |
| Description | Shows an error to the user, using Hammerspoon's Console |
| Parameters |  * err - A string containing an error message | | Returns |  * None | | Notes |  * This function is called whenever an (uncaught) error occurs or is thrown (via `error()`) * The default implementation shows a notification, opens the Console, and prints the error message and stacktrace * You can override this function if you wish to route errors differently (e.g. for remote systems) | 
#### [toggleConsole](#toggleConsole)
| | |
|-|-|
| Signature   | hs.toggleConsole()  |
| Type        | Function |
| Description | Toggles the visibility of the console |
| Parameters |  * None | | Returns |  * None | | Notes |  * If the console is not currently open, it will be opened. If it is open and not the focused window, it will be brought forward and focused. * If the console is focused, it will be closed. | 
#### [updateAvailable](#updateAvailable)
| | |
|-|-|
| Signature   | hs.updateAvailable() -> boolean  |
| Type        | Function |
| Description | Returns a boolean indicating whether or not the Sparkle framework has found a Hammerspoon update. |
| Parameters |  * None | | Returns |  * A boolean, true if an update is available, otherwise false | | Notes |  * This is not a live check, it is a cached result of whatever the previous update check found. By default Hammerspoon checks for updates every few hours, but you can also add your own timer to check for updates more frequently with `hs.checkForUpdates()` | 
#### [uploadCrashData](#uploadCrashData)
| | |
|-|-|
| Signature   | hs.uploadCrashData([state]) -> bool  |
| Type        | Function |
| Description | Get or set the "Upload Crash Data" preference for Hammerspoon |
| Parameters |  * state - An optional boolean, true to upload crash reports, false to not | | Returns |  * True if Hammerspoon is currently (or has just been) set to upload crash data or False otherwise | | Notes |  * If at all possible, please do allow Hammerspoon to upload crash reports to us, it helps a great deal in keeping Hammerspoon stable * Our Privacy Policy can be found here: [http://www.hammerspoon.org/privacy.html](https://github.com/Hammerspoon/hammerspoon/pull/1286/files) | 