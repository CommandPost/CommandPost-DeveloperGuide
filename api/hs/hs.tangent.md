# [docs](index.md) » hs.tangent
---

Tangent Control Surface Extension

**API Version:** TUBE Version 3.2 - TIPC Rev 4 (22nd February 2017)

This plugin allows Hammerspoon to communicate with Tangent's range of panels, such as their Element, Virtual Element Apps, Wave, Ripple and any future panels.

The Tangent Unified Bridge Engine (TUBE) is made up of two software elements, the Mapper and the Hub. The Hub communicates with your application via the
TUBE Inter Process Communications (TIPC). TIPC is a standardised protocol to allow any application that supports it to communicate with any current and
future panels produced by Tangent via the TUBE Hub.

You can download the Tangent Developer Support Pack & Tangent Hub Installer for Mac [here](http://www.tangentwave.co.uk/developer-support/).

This extension was thrown together by [Chris Hocking](https://github.com/latenitefilms), then dramatically improved by [David Peterson](https://github.com/randomeizer) for [CommandPost](http://commandpost.io).

## API Overview
* Constants - Useful values which cannot be changed
 * [action](#action)
 * [fromHub](#fromhub)
 * [panelType](#paneltype)
 * [parameter](#parameter)
 * [toHub](#tohub)
* Variables - Configurable values
 * [automaticallySendApplicationDefinition](#automaticallysendapplicationdefinition)
 * [ipAddress](#ipaddress)
 * [port](#port)
* Functions - API calls offered directly by the extension
 * [callback](#callback)
 * [connect](#connect)
 * [connected](#connected)
 * [disconnect](#disconnect)
 * [isTangentHubInstalled](#istangenthubinstalled)
 * [send](#send)
 * [sendAllChange](#sendallchange)
 * [sendApplicationDefinition](#sendapplicationdefinition)
 * [sendDisplayText](#senddisplaytext)
 * [sendHighlightControl](#sendhighlightcontrol)
 * [sendIndicateControl](#sendindicatecontrol)
 * [sendMenuString](#sendmenustring)
 * [sendModeValue](#sendmodevalue)
 * [sendPanelConnectionStatesRequest](#sendpanelconnectionstatesrequest)
 * [sendParameterValue](#sendparametervalue)
 * [sendRenameControl](#sendrenamecontrol)
 * [sendUnmanagedDisplayWrite](#sendunmanageddisplaywrite)
 * [sendUnmanagedPanelCapabilitiesRequest](#sendunmanagedpanelcapabilitiesrequest)
 * [setLogLevel](#setloglevel)

## API Documentation

### Constants

#### [action](#action)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.reserved.action -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Definitions for reserved action IDs. |
| **Notes**                                            | <ul><li><code>alt</code>                     - toggles the 'ALT' function.</li><li><code>nextKnobBank</code>            - switches to the next knob bank.</li><li><code>prevKnobBank</code>            - switches to the previous knob bank.</li><li><code>nextButtonBank</code>          - switches to the next button bank.</li><li><code>prevBasketBank</code>          - switches to the previous button bank.</li><li><code>nextTrackerballBank</code>     - switches to the next trackerball bank.</li><li><code>prevTrackerballBank</code>     - switches to the previous trackerball bank.</li><li><code>nextMode</code>                - switches to the next mode.</li><li><code>prevMode</code>                - switches to the previous mode.</li><li><code>goToMode</code>                - switches to the specified mode, requiring a Argument with the mode ID.</li><li><code>toggleJogShuttle</code>        - toggles jog/shuttle mode.</li><li><code>toggleMouseEmulation</code>    - toggles mouse emulation.</li><li><code>fakeKeypress</code>            - generates a keypress, requiring an Argument with the key code.</li><li><code>showHUD</code>                 - shows the HUD on screen.</li><li><code>goToKnobBank</code>            - goes to the specific knob bank, requiring an Argument with the bank number.</li><li><code>goToButtonBank</code>          - goes to the specific button bank, requiring an Argument with the bank number.</li><li><code>goToTrackerballBank</code>     - goes to the specific trackerball bank, requiring an Argument with the bank number.</li></ul> |

#### [fromHub](#fromhub)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.fromHub -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Definitions for IPC Commands from the HUB to Hammerspoon. |
| **Notes**                                            | <ul><li><code>connected</code>                       - a connection is established with the Hub.</li><li><code>disconnected</code>                    - the connection is dropped with the Hub.</li><li><code>initiateComms</code>                   - sent when the Hub wants to initiate communications.</li><li><code>parameterChange</code>                 - a parameter was incremented.</li><li><code>parameterReset</code>                  - a parameter was reset.</li><li><code>parameterValueRequest</code>           - the Hub wants the current value of the parameter.</li><li><code>menuChange</code>                      - The menu was changed, <code>+1</code> or <code>-1</code>.</li><li><code>menuReset</code>                       - The menu was reset.</li><li><code>menuStringRequest</code>               - The application should send a <code>menuString</code> with the current value.</li><li><code>actionOn</code>                        - An action button was pressed.</li><li><code>actionOff</code>                       - An action button was released.</li><li><code>modeChange</code>                      - The current mode was changed.</li><li><code>transport</code>                       - The transport.</li><li><code>unmanagedPanelCapabilities</code>      - Send by the Hub to advertise an unmanaged panel.</li><li><code>unmanagedButtonDown</code>             - A button on an unmanaged panel was pressed.</li><li><code>unmanagedButtonUp</code>               - A button on an unmanaged panel was released.</li><li><code>unmanagedEncoderChange</code>          - An encoder (dial/wheel) on an unmanaged panel changed.</li><li><code>unmanagedDisplayRefresh</code>         - Triggered when an unmanaged panel's display needs to update.</li><li><code>panelConnectionState</code>            - A panel's connection state changed.</li></ul> |

#### [panelType](#paneltype)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.panelType -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Tangent Panel Types. |

#### [parameter](#parameter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.reserved.parameter -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | A table of reserved parameter IDs. |
| **Notes**                                            | <ul><li><code>transportRing</code>           - transport ring.</li><li><code>fakeKeypress</code>            - sends a fake keypress.</li></ul> |

#### [toHub](#tohub)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.toHub -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Definitions for IPC Commands from Hammerspoon to the HUB. |

### Variables

#### [automaticallySendApplicationDefinition](#automaticallysendapplicationdefinition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.automaticallySendApplicationDefinition -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Automatically send the "Application Definition" response. Defaults to `true`. |

#### [ipAddress](#ipaddress)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.ipAddress -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | IP Address that the Tangent Hub is located at. Defaults to 127.0.0.1. |

#### [port](#port)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.port -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | The port that Tangent Hub monitors. Defaults to 64246. |

### Functions

#### [callback](#callback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.callback() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sets a callback when new messages are received. |
| **Parameters**                                       | <ul><li>callbackFn - a function to set as the callback for <code>hs.tangent</code>. If the value provided is <code>nil</code>, any currently existing callback function is removed.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful otherwise <code>false</code></li></ul> |
| **Notes**                                            | <ul><li>Full documentation for the Tangent API can be downloaded <a href="http://www.tangentwave.co.uk/download/developer-support-pack/">here</a>.</li><li>The callback function should expect 1 argument and should not return anything.</li><li>The 1 argument will be a table, which can contain one or many commands. Each command is it's own table with the following contents:</li><li>id - the message ID of the incoming message</li><li>metadata - A table of data for the Tangent command (see below).</li><li>The metadata table will return the following, depending on the <code>id</code> for the callback:</li><li><code>connected</code> - Connection to Tangent Hub successfully established.</li><li><code>disconnected</code> - The connection to Tangent Hub was dropped.</li><li><code>initiateComms</code> - Initiates communication between the Hub and the application.<ul><li><code>protocolRev</code> - The revision number of the protocol.</li><li><code>numPanels</code> - The number of panels connected.</li><li><code>panels</code></li><li><code>panelID</code> - The ID of the panel.</li><li><code>panelType</code> - The type of panel connected.</li><li><code>data</code> - The raw data from the Tangent Hub</li></ul></li><li><code>parameterChange</code> - Requests that the application increment a parameter.<ul><li><code>paramID</code> - The ID value of the parameter.</li><li><code>increment</code> - The incremental value which should be applied to the parameter.</li></ul></li><li><code>parameterReset</code> - Requests that the application changes a parameter to its reset value.<ul><li><code>paramID</code> - The ID value of the parameter.</li></ul></li><li><code>parameterValueRequest</code> - Requests that the application sends a <code>ParameterValue (0x82)</code> command to the Hub.<ul><li><code>paramID</code> - The ID value of the parameter.</li></ul></li><li><code>menuChange</code> - Requests the application change a menu index by +1 or -1.<ul><li><code>menuID</code> - The ID value of the menu.</li><li><code>increment</code> - The incremental amount by which the menu index should be changed which will always be an integer value of +1 or -1.</li></ul></li><li><code>menuReset</code> - Requests that the application changes a menu to its reset value.<ul><li><code>menuID</code> - The ID value of the menu.</li></ul></li><li><code>menuStringRequest</code> - Requests that the application sends a <code>MenuString (0x83)</code> command to the Hub.<ul><li><code>menuID</code> - The ID value of the menu.</li></ul></li><li><code>actionOn</code> - Requests that the application performs the specified action.<ul><li><code>actionID</code> - The ID value of the action.</li></ul></li><li><code>modeChange</code> - Requests that the application changes to the specified mode.<ul><li><code>modeID</code> - The ID value of the mode.</li></ul></li><li><code>transport</code> - Requests the application to move the currently active transport.<ul><li><code>jogValue</code> - The number of jog steps to move the transport.</li><li><code>shuttleValue</code> - An incremental value to add to the shuttle speed.</li></ul></li><li><code>actionOff</code> - Requests that the application cancels the specified action.<ul><li><code>actionID</code> - The ID value of the action.</li></ul></li><li><code>unmanagedPanelCapabilities</code> - Only used when working in Unmanaged panel mode. Sent in response to a <code>UnmanagedPanelCapabilitiesRequest (0xA0)</code> command.<ul><li><code>panelID</code> - The ID of the panel as reported in the <code>InitiateComms</code> command.</li><li><code>numButtons</code> - The number of buttons on the panel.</li><li><code>numEncoders</code> - The number of encoders on the panel.</li><li><code>numDisplays</code> - The number of displays on the panel.</li><li><code>numDisplayLines</code> - The number of lines for each display on the panel.</li><li><code>numDisplayChars</code> - The number of characters on each line of each display on the panel.</li></ul></li><li><code>unmanagedButtonDown</code> - Only used when working in Unmanaged panel mode. Issued when a button has been pressed.<ul><li><code>panelID</code> - The ID of the panel as reported in the <code>InitiateComms</code> command.</li><li><code>buttonID</code> - The hardware ID of the button</li></ul></li><li><code>unmanagedButtonUp</code> - Only used when working in Unmanaged panel mode. Issued when a button has been released.<ul><li><code>panelID</code> - The ID of the panel as reported in the <code>InitiateComms</code> command.</li><li><code>buttonID</code> - The hardware ID of the button.</li></ul></li><li><code>unmanagedEncoderChange</code> - Only used when working in Unmanaged panel mode. Issued when an encoder has been moved.<ul><li><code>panelID</code> - The ID of the panel as reported in the <code>InitiateComms</code> command.</li><li><code>paramID</code> - The hardware ID of the encoder.</li><li><code>increment</code> - The incremental value.</li></ul></li><li><code>unmanagedDisplayRefresh</code> - Only used when working in Unmanaged panel mode. Issued when a panel has been connected or the focus of the panel has been returned to your application.<ul><li><code>panelID</code> - The ID of the panel as reported in the <code>InitiateComms</code> command.</li></ul></li><li><code>panelConnectionState</code><ul><li><code>panelID</code> - The ID of the panel as reported in the <code>InitiateComms</code> command.</li><li><code>state</code> - The connected state of the panel, <code>true</code> if connected, <code>false</code> if disconnected.</li></ul></li></ul> |

#### [connect](#connect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.connect(applicationName, systemPath[, userPath]) -> boolean, errorMessage` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Connects to the Tangent Hub. |
| **Parameters**                                       | <ul><li>applicationName - Your application name as a string</li><li>systemPath - A string containing the absolute path of the directory that contains the Controls and Default Map XML files.</li><li>[userPath] - An optional string containing the absolute path of the directory that contains the User’s Default Map XML files.</li></ul> |
| **Returns**                                          | <ul><li>success - <code>true</code> on success, otherwise <code>nil</code></li><li>errorMessage - The error messages as a string or <code>nil</code> if <code>success</code> is <code>true</code>.</li></ul> |

#### [connected](#connected)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.connected() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks to see whether or not you're successfully connected to the Tangent Hub. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if connected, otherwise <code>false</code></li></ul> |

#### [disconnect](#disconnect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.disconnect() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Disconnects from the Tangent Hub. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [isTangentHubInstalled](#istangenthubinstalled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.isTangentHubInstalled() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks to see whether or not the Tangent Hub software is installed. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if Tangent Hub is installed otherwise <code>false</code>.</li></ul> |

#### [send](#send)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.send(byteString) -> boolean, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sends a "bytestring" message to the Tangent Hub. This should be a full |
| **Parameters**                                       | <ul><li>byteString   - The string of bytes to send to tangent.</li></ul> |
| **Returns**                                          | <ul><li>success - <code>true</code> if connected, otherwise <code>false</code></li><li>errorMessage - An error message if an error occurs, as a string</li></ul> |
| **Notes**                                            | <ul><li>Full documentation for the Tangent API can be downloaded <a href="http://www.tangentwave.co.uk/download/developer-support-pack/">here</a>.</li></ul> |

#### [sendAllChange](#sendallchange)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.sendAllChange() -> boolean, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Tells the Hub that a large number of software-controls have changed. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful, or <code>false</code> and an error message if not.</li></ul> |

#### [sendApplicationDefinition](#sendapplicationdefinition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.sendApplicationDefinition([appName, systemPath, userPath]) -> boolean, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sends the application details to the Tangent Hub. |
| **Parameters**                                       | <ul><li>appName       - The human-readable name of the application.</li><li>systemPath    - A string containing the absolute path of the directory that contains the Controls and Default Map XML files (Path String)</li><li>userPath      - A string containing the absolute path of the directory that contains the User’s Default Map XML files (Path String)</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful, <code>false</code> and an error message if there was a problem.</li></ul> |

#### [sendDisplayText](#senddisplaytext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.sendDisplayText(messages[, doubleHeight]) -> boolean, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      |  * Updates the Hub with a number of character strings that will be displayed |
| **Parameters**                                       | <ul><li>messages      - A list of messages to send.</li><li>doubleHeight  - An optional list of <code>boolean</code>s indicating if the corresponding message is double-height.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful, or <code>false</code> and an error message if not.</li></ul> |

#### [sendHighlightControl](#sendhighlightcontrol)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.sendHighlightControl(targetID, active) -> boolean, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      |  * Highlights the control on any panel where this feature is available. |
| **Parameters**                                       | <ul><li>targetID      - The id of any application defined Parameter, Menu, Action or Mode (Unsigned Int)</li><li>active        - If <code>true</code>, the control is highlighted, otherwise it is not.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if sent successfully, <code>false</code> and an error message if no.</li></ul> |

#### [sendIndicateControl](#sendindicatecontrol)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.sendIndicateControl(targetID, indicated) -> boolean, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      |  * Sets the Indicator of the control on any panel where this feature is |
| **Parameters**                                       | <ul><li>targetID      - The id of any application defined Parameter, Menu, Action or Mode</li><li>active        - If <code>true</code>, the control is indicated, otherwise it is not.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if sent successfully, <code>false</code> and an error message if no.</li></ul> |

#### [sendMenuString](#sendmenustring)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.sendMenuString(menuID, value[, atDefault]) -> boolean, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Updates the Hub with a menu value. |
| **Parameters**                                       | <ul><li>menuID - The ID value of the menu (Unsigned Int)</li><li>value - The current ‘value’ of the parameter represented as a string</li><li>atDefault - if <code>true</code> the value represents the default. Otherwise <code>false</code>.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful, or <code>false</code> and an error message if not.</li></ul> |

#### [sendModeValue](#sendmodevalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.sendModeValue(modeID) -> boolean, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Updates the Hub with a mode value. |
| **Parameters**                                       | <ul><li>modeID - The ID value of the mode (Unsigned Int)</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful, or <code>false</code> and an error message if not.</li></ul> |

#### [sendPanelConnectionStatesRequest](#sendpanelconnectionstatesrequest)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.sendPanelConnectionStatesRequest())` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      |  * Requests the Hub to respond with a sequence of PanelConnectionState |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if sent successfully, <code>false</code> and an error message if not.</li></ul> |

#### [sendParameterValue](#sendparametervalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.sendParameterValue(paramID, value[, atDefault]) -> boolean, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Updates the Hub with a parameter value. |
| **Parameters**                                       | <ul><li>paramID - The ID value of the parameter (Unsigned Int)</li><li>value - The current value of the parameter (Float)</li><li>atDefault - if <code>true</code> the value represents the default. Defaults to <code>false</code>.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful, or <code>false</code> and an error message if not.</li></ul> |

#### [sendRenameControl](#sendrenamecontrol)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.sendRenameControl(targetID, newName) -> boolean, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      |  * Renames a control dynamically. |
| **Parameters**                                       | <ul><li>targetID  - The id of any application defined Parameter, Menu, Action or Mode (Unsigned Int)</li><li>newName   - The new name to apply.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful, <code>false</code> and an error message if not.</li></ul> |

#### [sendUnmanagedDisplayWrite](#sendunmanageddisplaywrite)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.sendUnmanagedDisplayWrite(panelID, displayID, lineNum, pos, message) -> boolean, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      |  * Only used when working in Unmanaged panel mode. |
| **Parameters**                                       | <ul><li>panelID       - The ID of the panel as reported in the InitiateComms command (Unsigned Int)</li><li>displayID     - The ID of the display to be written to (Unsigned Int)</li><li>lineNum       - The line number of the display to be written to with <code>1</code> as the top line (Unsigned Int)</li><li>pos           - The position on the line to start writing from with <code>1</code> as the first column (Unsigned Int)</li><li>message       - A line of text (Character String)</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful, or <code>false</code> and an error message if not.</li></ul> |

#### [sendUnmanagedPanelCapabilitiesRequest](#sendunmanagedpanelcapabilitiesrequest)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.sendUnmanagedPanelCapabilitiesRequest(panelID) -> boolean, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      |  * Only used when working in Unmanaged panel mode |
| **Parameters**                                       | <ul><li>panelID - The ID of the panel as reported in the InitiateComms command (Unsigned Int)</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful, or <code>false</code> and an error message if not.</li></ul> |

#### [setLogLevel](#setloglevel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.setLogLevel(loglevel) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sets the Log Level. |
| **Parameters**                                       | <ul><li>loglevel - can be 'nothing', 'error', 'warning', 'info', 'debug', or 'verbose'; or a corresponding number between 0 and 5</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

