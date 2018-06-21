# [docs](index.md) » hs.tangent
---

**Tangent Control Surface Extension**

**API Version:** TUBE Version 3.2 - TIPC Rev 4 (22nd February 2017)

This plugin allows Hammerspoon to communicate with Tangent's range of panels, such as their Element, Virtual Element Apps, Wave, Ripple and any future panels.

The Tangent Unified Bridge Engine (TUBE) is made up of two software elements, the Mapper and the Hub. The Hub communicates with your application via the
TUBE Inter Process Communications (TIPC). TIPC is a standardised protocol to allow any application that supports it to communicate with any current and
future panels produced by Tangent via the TUBE Hub.

You can download the Tangent Developer Support Pack & Tangent Hub Installer for Mac [here](http://www.tangentwave.co.uk/developer-support/).

This extension was thrown together by [Chris Hocking](http://latenitefilms.com) for [CommandPost](http://commandpost.io).

## API Overview
* Constants - Useful values which cannot be changed
 * [APP_MESSAGE](#app_message)
 * [HUB_MESSAGE](#hub_message)
 * [PANEL_TYPE](#panel_type)
* Variables - Configurable values
 * [automaticallySendApplicationDefinition](#automaticallysendapplicationdefinition)
 * [interval](#interval)
 * [ipAddress](#ipaddress)
 * [port](#port)
* Functions - API calls offered directly by the extension
 * [callback](#callback)
 * [connect](#connect)
 * [connected](#connected)
 * [disconnect](#disconnect)
 * [isTangentHubInstalled](#istangenthubinstalled)
 * [send](#send)
 * [setLogLevel](#setloglevel)

## API Documentation

### Constants

#### [APP_MESSAGE](#app_message)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.APP_MESSAGE -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Definitions for IPC Commands from Hammerspoon to the HUB.                                                                                         |

#### [HUB_MESSAGE](#hub_message)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.HUB_MESSAGE -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Definitions for IPC Commands from the HUB to Hammerspoon.                                                                                         |

#### [PANEL_TYPE](#panel_type)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.PANEL_TYPE -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Tangent Panel Types.                                                                                         |

### Variables

#### [automaticallySendApplicationDefinition](#automaticallysendapplicationdefinition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.automaticallySendApplicationDefinition -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | Automatically send the "Application Definition" response. Defaults to `true`.                                                                                         |

#### [interval](#interval)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.interval -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | How often we check for new socket messages. Defaults to 0.001.                                                                                         |

#### [ipAddress](#ipaddress)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.ipAddress -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | IP Address that the Tangent Hub is located at. Defaults to 127.0.0.1.                                                                                         |

#### [port](#port)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.port -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | The port that Tangent Hub monitors. Defaults to 64246.                                                                                         |

### Functions

#### [callback](#callback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.callback() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets a callback when new messages are received.                                                                                         |
| **Parameters**                                       |  * callbackFn - a function to set as the callback for `hs.tangent`. If the value provided is `nil`, any currently existing callback function is removed.                                       |
| **Returns**                                          |  * `true` if successful otherwise `false`                                                |
| **Notes**                                            |  * Full documentation for the Tangent API can be downloaded [here](http://www.tangentwave.co.uk/download/developer-support-pack/). * The callback function should expect 2 arguments and should not return anything:   * id - the message ID of the incoming message   * metadata - A table of data for the Tangent command (see below). * The metadata table will return the following, depending on the `id` for the callback:   * `CONNECTED` - Connection To Tangent Hub successfully established.   * `INITIATE_COMMS` - Initiates communication between the Hub and the application.     * `protocolRev` - The revision number of the protocol.     * `numPanels` - The number of panels connected.     * `panels`       * `panelID` - The ID of the panel.       * `panelType` - The type of panel connected.     * `data` - The raw data from the Tangent Hub   * `PARAMETER_CHANGE` - Requests that the application increment a parameter.     * `paramID` - The ID value of the parameter.     * `increment` - The incremental value which should be applied to the parameter.     * `data` - The raw data from the Tangent Hub   * `PARAMETER_RESET` - Requests that the application changes a parameter to its reset value.     * `paramID` - The ID value of the parameter.     * `data` - The raw data from the Tangent Hub   * `PARAMETER_VALUE_REQUEST` - Requests that the application sends a `ParameterValue (0x82)` command to the Hub.     * `paramID` - The ID value of the parameter.     * `data` - The raw data from the Tangent Hub   * `MENU_CHANGE` - Requests the application change a menu index by +1 or -1.     * `menuID` - The ID value of the menu.     * `increment` - The incremental amount by which the menu index should be changed which will always be an integer value of +1 or -1.     * `data` - The raw data from the Tangent Hub   * `MENU_RESET` - Requests that the application changes a menu to its reset value.     * `menuID` - The ID value of the menu.     * `data` - The raw data from the Tangent Hub   * `MENU_STRING_REQUEST` - Requests that the application sends a `MenuString (0x83)` command to the Hub.     * `menuID` - The ID value of the menu.     * `data` - The raw data from the Tangent Hub   * `ACTION_ON` - Requests that the application performs the specified action.     * `actionID` - The ID value of the action.     * `data` - The raw data from the Tangent Hub   * `MODE_CHANGE` - Requests that the application changes to the specified mode.     * `modeID` - The ID value of the mode.     * `data` - The raw data from the Tangent Hub   * `TRANSPORT` - Requests the application to move the currently active transport.     * `jogValue` - The number of jog steps to move the transport.     * `shuttleValue` - An incremental value to add to the shuttle speed.     * `data` - The raw data from the Tangent Hub   * `ACTION_OFF` - Requests that the application cancels the specified action.     * `actionID` - The ID value of the action.     * `data` - The raw data from the Tangent Hub   * `UNMANAGED_PANEL_CAPABILITIES` - Only used when working in Unmanaged panel mode. Sent in response to a `UnmanagedPanelCapabilitiesRequest (0xA0)` command.     * `panelID` - The ID of the panel as reported in the `InitiateComms` command.     * `numButtons` - The number of buttons on the panel.     * `numEncoders` - The number of encoders on the panel.     * `numDisplays` - The number of displays on the panel.     * `numDisplayLines` - The number of lines for each display on the panel.     * `numDisplayChars` - The number of characters on each line of each display on the panel.     * `data` - The raw data from the Tangent Hub   * `UNMANAGED_BUTTON_DOWN` - Only used when working in Unmanaged panel mode. Issued when a button has been pressed.     * `panelID` - The ID of the panel as reported in the `InitiateComms` command.     * `buttonID` - The hardware ID of the button     * `data` - The raw data from the Tangent Hub.   * `UNMANAGED_BUTTON_UP` - Only used when working in Unmanaged panel mode. Issued when a button has been released.     * `panelID` - The ID of the panel as reported in the `InitiateComms` command.     * `buttonID` - The hardware ID of the button.     * `data` - The raw data from the Tangent Hub   * `UNMANAGED_ENCODER_CHANGE` - Only used when working in Unmanaged panel mode. Issued when an encoder has been moved.     * `panelID` - The ID of the panel as reported in the `InitiateComms` command.     * `paramID` - The hardware ID of the encoder.     * `increment` - The incremental value.     * `data` - The raw data from the Tangent Hub   * `UNMANAGED_DISPLAY_REFRESH` - Only used when working in Unmanaged panel mode. Issued when a panel has been connected or the focus of the panel has been returned to your application.     * `panelID` - The ID of the panel as reported in the `InitiateComms` command.     * `data` - The raw data from the Tangent Hub   * `PANEL_CONNECTION_STATE`     * `panelID` - The ID of the panel as reported in the `InitiateComms` command.     * `state` - The connected state of the panel, `true` if connected, `false` if disconnected.     * `data` - The raw data from the Tangent Hub                                                      |

#### [connect](#connect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.connect(applicationName, systemPath[, userPath]) -> boolean, errorMessage` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Connects to the Tangent Hub.                                                                                         |
| **Parameters**                                       |  * applicationName - Your application name as a string * systemPath - A string containing the absolute path of the directory that contains the Controls and Default Map XML files. * [userPath] - An optional string containing the absolute path of the directory that contains the User’s Default Map XML files.                                       |
| **Returns**                                          |  * success - `true` on success, otherwise `nil` * errorMessage - The error messages as a string or `nil` if `success` is `true`.                                                |

#### [connected](#connected)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.connected() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see whether or not you're successfully connected to the Tangent Hub.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `true` if connected, otherwise `false`                                                |

#### [disconnect](#disconnect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.disconnect() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Disconnects from the Tangent Hub.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [isTangentHubInstalled](#istangenthubinstalled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.isTangentHubInstalled() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see whether or not the Tangent Hub software is installed.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `true` if Tangent Hub is installed otherwise `false`.                                                |

#### [send](#send)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.send(id, metadata) -> boolean, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sends a message to the Tangent Hub.                                                                                         |
| **Parameters**                                       |  * id - The ID of the message you want to send as defined in `hs.tangent.APP_MESSAGE` * metadata - A table of values as explained below.                                       |
| **Returns**                                          |  * success - `true` if connected, otherwise `false` * errorMessage - An error message if an error occurs, as a string                                                |
| **Notes**                                            |  * Full documentation for the Tangent API can be downloaded [here](http://www.tangentwave.co.uk/download/developer-support-pack/). * The metadata table will accept the following, depending on the `id` provided:   * `APPLICATION_DEFINITION` - This is sent in response to the `InitiateComms (0x01)` command and establishes communication between the application and the hub.     * `applicationName` - An string containing the name of the application.     * `systemPath` - A string containing the absolute path of the directory that contains the Controls and Default Map XML files.     * `userPath` - A string containing the absolute path of the directory that contains the User’s Default Map XML files.   * `PARAMETER_VALUE` - Updates the Hub with a parameter value.     * `paramID` - The ID value of the parameter.     * `value` - The current value of the parameter.     * `atDefault` - `true` if the value represents the default, otherwise `false`.   * `MENU_STRING` - Updates the Hub with a menu value.     * `menuID` - The ID value of the menu.     * `valueStr` - The current ‘value’ of the parameter represented as a string.     * `atDefault` - `true` if the value represents the default, otherwise `false`.   * `ALL_CHANGE` - Tells the Hub that a large number of software-controls have changed.   * `MODE_VALUE`     * `modeID` - The ID value of the mode.   * `DISPLAY_TEXT`     * `stringOne` - A line of status text.     * `stringOneDoubleHeight` - `true` if the string is to be printed double height, otherwise `false`.     * [`stringTwo`] - An optional line of status text.     * [`stringTwoDoubleHeight`] - `true` if the string is to be printed double height, otherwise `false` (required if `stringTwo` is supplied).     * [`stringThree`] - An optional line of status text.     * [`stringThreeDoubleHeight`] - `true` if the string is to be printed double height, otherwise `false` (required if `stringThree` is supplied).   * `UNMANAGED_PANEL_CAPABILITIES_REQUEST`     * `panelID` - The ID of the panel as reported in the `InitiateComms` command.   * `UNMANAGED_DISPLAY_WRITE`     * `panelID` - The ID of the panel as reported in the `InitiateComms` command.     * `displayID` - The ID of the display to be written to.     * `lineNum` - The line number of the display to be written to with 0 as the top line.     * `pos` - The position on the line to start writing from with 0 as the first column.     * `dispStr` - A line of text.   * `RENAME_CONTROL`     * `targetID` - The id of any application defined Parameter, Menu, Action or Mode.     * `nameStr` - The new name string.   * `HIGHLIGHT_CONTROL`     * `targetID` - The id of any application defined Parameter, Menu, Action or Mode.     * `state` - The state to set, `true` for highlighted, `false` for clear.   * `INDICATE_CONTROL`     * `targetID` - The id of any application defined Action or Mode.     * `state` - The state to set, `true` for indicated, `false` for clear.   * `REQUEST_PANEL_CONNECTION_STATES` - Requests the Hub to respond with a sequence of PanelConnectionState (0x35) commands to report the connected/disconnected status of each configured panel.                                                      |

#### [setLogLevel](#setloglevel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.setLogLevel(loglevel) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the Log Level.                                                                                         |
| **Parameters**                                       |  * loglevel - can be 'nothing', 'error', 'warning', 'info', 'debug', or 'verbose'; or a corresponding number between 0 and 5                                       |
| **Returns**                                          |  * None                                                |

