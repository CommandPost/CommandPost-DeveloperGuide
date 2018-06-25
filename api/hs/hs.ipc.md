# [docs](index.md) » hs.ipc
---

Provides Hammerspoon with the ability to create both local and remote message ports for inter-process communication.

The most common use of this module is to provide support for the command line tool `hs` which can be added to your terminal shell environment with [hs.ipc.cliInstall](#cliInstall).  The command line tool will not work unless the `hs.ipc` module is loaded first, so it is recommended that you add `require("hs.ipc")` to your Hammerspoon `init.lua` file (usually located at ~/.hammerspoon/init.lua) so that it is always available when Hammerspoon is running.

This module is based heavily on code from Mjolnir by [Steven Degutis](https://github.com/sdegutis/).

## API Overview
* Deprecateds - API features which will be removed in an future release
 * [cliGetColors](#cligetcolors)
 * [cliResetColors](#cliresetcolors)
 * [cliSetColors](#clisetcolors)
* Functions - API calls offered directly by the extension
 * [cliColors](#clicolors)
 * [cliInstall](#cliinstall)
 * [cliSaveHistory](#clisavehistory)
 * [cliSaveHistorySize](#clisavehistorysize)
 * [cliStatus](#clistatus)
 * [cliUninstall](#cliuninstall)
* Constructors - API calls which return an object, typically one that offers API methods
 * [localPort](#localport)
 * [remotePort](#remoteport)
* Methods - API calls which can only be made on an object returned by a constructor
 * [delete](#delete)
 * [isRemote](#isremote)
 * [isValid](#isvalid)
 * [name](#name)
 * [sendMessage](#sendmessage)

## API Documentation

### Deprecateds

#### [cliGetColors](#cligetcolors)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.ipc.cliGetColors() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Deprecated                                                                                         |
| **Description**                                      | See [hs.ipc.cliColors](#cliColors).                                                                                         |

#### [cliResetColors](#cliresetcolors)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.ipc.cliResetColors()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Deprecated                                                                                         |
| **Description**                                      | See [hs.ipc.cliColors](#cliColors).                                                                                         |

#### [cliSetColors](#clisetcolors)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.ipc.cliSetColors(table) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Deprecated                                                                                         |
| **Description**                                      | See [hs.ipc.cliColors](#cliColors).                                                                                         |

### Functions

#### [cliColors](#clicolors)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.ipc.cliColors([colors]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Get or set the terminal escape codes used to produce colorized output in the `hs` command line tool                                                                                         |
| **Parameters**                                       | <ul><br /><li>colors - an optional table or explicit nil specifying the colors to use when colorizing output for the command line tool.  If you specify an explicit nil, the colors will revert to their defaults.  If you specify a table it must contain one or more of the following keys with the terminal key sequence as a string for the value:   * initial - this color is used for the initial tagline when starting the command line tool and for output to the Hammerspoon console that is redirected to the instance.  Defaults to "\27[35m" (foreground magenta).   * input   - this color is used for input typed in by the user into the cli instance.  Defaults to "\27[33m" (foreground yellow).   * output  - this color is used for output generated by the commands executed within the instance and the results returned.  Defaults to "\27[36m" (foreground cyan).   * error   - this color is used for lua errors generated by the commands executed within the instance.  Defaults to "\27[31m" (foreground red).</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a table describing the colors used when colorizing output in the <code>hs</code> command line tool.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>For a brief intro into terminal colors, you can visit a web site like this one <a href="http://jafrog.com/2013/11/23/colors-in-terminal.html">http://jafrog.com/2013/11/23/colors-in-terminal.html</a> * Lua doesn't support octal escapes in it's strings, so use <code>\x1b</code> or <code>\27</code> to indicate the <code>escape</code> character e.g. <code>ipc.cliSetColors{ initial = "", input = "\27[33m", output = "\27[38;5;11m" }</code></li><br /></ul>                                             |

#### [cliInstall](#cliinstall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.ipc.cliInstall([path][,silent]) -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Installs the `cmdpost` command line tool                                                                                         |
| **Parameters**                                       | <ul><br /><li>path - An optional string containing a path to install the tool in. Defaults to <code>/usr/local</code> * silent - An optional boolean indicating whether or not to print errors to the CommandPost Error Log</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A boolean, true if the tool was successfully installed, otherwise false</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>If this function fails, it is likely that you have some old/broken symlinks. You can use <code>hs.ipc.cliUninstall()</code> to forcibly tidy them up</li><br /></ul>                                             |

#### [cliSaveHistory](#clisavehistory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.ipc.cliSaveHistory([state]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Get or set whether or not the command line tool saves a history of the commands you type.                                                                                         |
| **Parameters**                                       | <ul><br /><li>state - an optional boolean (default false) specifying whether or not a history of the commands you type into the command line tool should be saved between sessions.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>the current, possibly changed, value</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>If this is enabled, your history is saved in <code>hs.configDir .. ".cli.history"</code>, which is usually "~/.hammerspoon/.cli.history". * If you have multiple invocations of the command line tool running at the same time, only the history of the last one cleanly exited is saved; this is a limitation of the readline wrapper Apple has provided for libedit and at present no workaround is known.</li><br /></ul>                                             |

#### [cliSaveHistorySize](#clisavehistorysize)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.ipc.cliSaveHistorySize([size]) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Get or set whether the maximum number of commands saved when command line tool history saving is enabled.                                                                                         |
| **Parameters**                                       | <ul><br /><li>size - an optional integer (default 1000) specifying the maximum number of commands to save when <a href="#cliSaveHistory">hs.ipc.cliSaveHistory</a> is set to true.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>the current, possibly changed, value</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>When <a href="#cliSaveHistory">hs.ipc.cliSaveHistory</a> is enabled, your history is saved in <code>hs.configDir .. ".cli.history"</code>, which is usually "~/.hammerspoon/.cli.history". * If you have multiple invocations of the command line tool running at the same time, only the history of the last one cleanly exited is saved; this is a limitation of the readline wrapper Apple has provided for libedit and at present no workaround is known.</li><br /></ul>                                             |

#### [cliStatus](#clistatus)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.ipc.cliStatus([path][,silent]) -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the status of the `hs` command line tool                                                                                         |
| **Parameters**                                       | <ul><br /><li>path - An optional string containing a path to look for the <code>hs</code> tool. Defaults to <code>/usr/local</code> * silent - An optional boolean indicating whether or not to print errors to the Hammerspoon Console</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A boolean, true if the <code>hs</code> command line tool is correctly installed, otherwise false</li><br /></ul>                                           |

#### [cliUninstall](#cliuninstall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.ipc.cliUninstall([path][,silent]) -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Uninstalls the `hs` command line tool                                                                                         |
| **Parameters**                                       | <ul><br /><li>path - An optional string containing a path to remove the tool from. Defaults to <code>/usr/local</code> * silent - An optional boolean indicating whether or not to print errors to the CommandPost Error Log</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A boolean, true if the tool was successfully removed, otherwise false</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>This function used to be very conservative and refuse to remove symlinks it wasn't sure about, but now it will unconditionally remove whatever it finds at <code>path/bin/cmdpost</code> and <code>path/share/man/man1/cmdpost.1</code>. This is more likely to be useful in situations where this command is actually needed (please open an Issue on GitHub if you disagree!)</li><br /></ul>                                             |

### Constructors

#### [localPort](#localport)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.ipc.localPort(name, fn) -> ipcObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Create a new local ipcObject for receiving and responding to messages from a remote port                                                                                         |
| **Parameters**                                       | <ul><br /><li>name - a string acting as the message port name. * fn   - the callback function which will receive messages.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>the ipc object</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>a remote port can send messages at any time to a local port; a local port can only respond to messages from a remote port</li><br /></ul>                                             |

#### [remotePort](#remoteport)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.ipc.remotePort(name) -> ipcObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Create a new remote ipcObject for sending messages asynchronously to a local port                                                                                         |
| **Parameters**                                       | <ul><br /><li>name - a string acting as the message port name.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>the ipc object</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>a remote port can send messages at any time to a local port; a local port can only respond to messages from a remote port</li><br /></ul>                                             |

### Methods

#### [delete](#delete)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.ipc:delete() -> None` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Deletes the ipcObject, stopping it as well if necessary                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [isRemote](#isremote)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.ipc:isRemote() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns whether or not the ipcObject represents a remote or local port                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>true if the object is a remote port, otherwise false</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>a remote port can send messages at any time to a local port; a local port can only respond to messages from a remote port</li><br /></ul>                                             |

#### [isValid](#isvalid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.ipc:isValid() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns whether or not the ipcObject port is still valid or not                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>true if the object is a valid port, otherwise false</li><br /></ul>                                           |

#### [name](#name)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.ipc:name() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the name the ipcObject uses for its port when active                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>the port name as a string</li><br /></ul>                                           |

#### [sendMessage](#sendmessage)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.ipc:sendMessage(data, msgID, [waitTimeout], [oneWay]) -> status, response` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sends a message from a remote port to a local port                                                                                         |
| **Parameters**                                       | <ul><br /><li>data        - any data type which is to be sent to the local port.  The data will be converted into its string representation * msgID       - an integer message ID * waitTimeout - an optional number, default 2.0, representing the number of seconds the method will wait to send the message and then wait for a response.  The method <em>may</em> block up to twice this number of seconds, though usually it will be shorter. * oneWay      -  an optional boolean, default false, indicating whether or not to wait for a response.  It this is true, the second returned argument will be nil.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>status   - a boolean indicathing whether or not the local port responded before the timeout (true) or if an error or timeout occurred waiting for the response (false) * response - the response from the local port, usually a string, but may be nil if there was no response returned.  If status is false, will contain an error message describing the error.</li><br /></ul>                                           |

