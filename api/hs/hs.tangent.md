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
| **Parameters**                                       | <ul><li>callbackFn - a function to set as the callback for `hs.tangent`. If the value provided is `nil`, any currently existing callback function is removed.</li></ul> |
| **Returns**                                          | <ul><li>`true` if successful otherwise `false`</li></ul>          |
| **Notes**                                            | <ul><li>Full documentation for the Tangent API can be downloaded [here](http://www.tangentwave.co.uk/download/developer-support-pack/).</li><li>The callback function should expect 2 arguments and should not return anything:</li><li>  id - the message ID of the incoming message</li><li>  metadata - A table of data for the Tangent command (see below).</li><li>The metadata table will return the following, depending on the `id` for the callback:</li><li>  `CONNECTED` - Connection To Tangent Hub successfully established.</li><li>  `INITIATE_COMMS` - Initiates communication between the Hub and the application.</li><li>    `protocolRev` - The revision number of the protocol.</li><li>    `numPanels` - The number of panels connected.</li><li>    `panels`</li><li>      `panelID` - The ID of the panel.</li><li>      `panelType` - The type of panel connected.</li><li>    `data` - The raw data from the Tangent Hub</li><li>  `PARAMETER_CHANGE` - Requests that the application increment a parameter.</li><li>    `paramID` - The ID value of the parameter.</li><li>    `increment` - The incremental value which should be applied to the parameter.</li><li>    `data` - The raw data from the Tangent Hub</li><li>  `PARAMETER_RESET` - Requests that the application changes a parameter to its reset value.</li><li>    `paramID` - The ID value of the parameter.</li><li>    `data` - The raw data from the Tangent Hub</li><li>  `PARAMETER_VALUE_REQUEST` - Requests that the application sends a `ParameterValue (0x82)` command to the Hub.</li><li>    `paramID` - The ID value of the parameter.</li><li>    `data` - The raw data from the Tangent Hub</li><li>  `MENU_CHANGE` - Requests the application change a menu index by +1 or -1.</li><li>    `menuID` - The ID value of the menu.</li><li>    `increment` - The incremental amount by which the menu index should be changed which will always be an integer value of +1 or -1.</li><li>    `data` - The raw data from the Tangent Hub</li><li>  `MENU_RESET` - Requests that the application changes a menu to its reset value.</li><li>    `menuID` - The ID value of the menu.</li><li>    `data` - The raw data from the Tangent Hub</li><li>  `MENU_STRING_REQUEST` - Requests that the application sends a `MenuString (0x83)` command to the Hub.</li><li>    `menuID` - The ID value of the menu.</li><li>    `data` - The raw data from the Tangent Hub</li><li>  `ACTION_ON` - Requests that the application performs the specified action.</li><li>    `actionID` - The ID value of the action.</li><li>    `data` - The raw data from the Tangent Hub</li><li>  `MODE_CHANGE` - Requests that the application changes to the specified mode.</li><li>    `modeID` - The ID value of the mode.</li><li>    `data` - The raw data from the Tangent Hub</li><li>  `TRANSPORT` - Requests the application to move the currently active transport.</li><li>    `jogValue` - The number of jog steps to move the transport.</li><li>    `shuttleValue` - An incremental value to add to the shuttle speed.</li><li>    `data` - The raw data from the Tangent Hub</li><li>  `ACTION_OFF` - Requests that the application cancels the specified action.</li><li>    `actionID` - The ID value of the action.</li><li>    `data` - The raw data from the Tangent Hub</li><li>  `UNMANAGED_PANEL_CAPABILITIES` - Only used when working in Unmanaged panel mode. Sent in response to a `UnmanagedPanelCapabilitiesRequest (0xA0)` command.</li><li>    `panelID` - The ID of the panel as reported in the `InitiateComms` command.</li><li>    `numButtons` - The number of buttons on the panel.</li><li>    `numEncoders` - The number of encoders on the panel.</li><li>    `numDisplays` - The number of displays on the panel.</li><li>    `numDisplayLines` - The number of lines for each display on the panel.</li><li>    `numDisplayChars` - The number of characters on each line of each display on the panel.</li><li>    `data` - The raw data from the Tangent Hub</li><li>  `UNMANAGED_BUTTON_DOWN` - Only used when working in Unmanaged panel mode. Issued when a button has been pressed.</li><li>    `panelID` - The ID of the panel as reported in the `InitiateComms` command.</li><li>    `buttonID` - The hardware ID of the button</li><li>    `data` - The raw data from the Tangent Hub.</li><li>  `UNMANAGED_BUTTON_UP` - Only used when working in Unmanaged panel mode. Issued when a button has been released.</li><li>    `panelID` - The ID of the panel as reported in the `InitiateComms` command.</li><li>    `buttonID` - The hardware ID of the button.</li><li>    `data` - The raw data from the Tangent Hub</li><li>  `UNMANAGED_ENCODER_CHANGE` - Only used when working in Unmanaged panel mode. Issued when an encoder has been moved.</li><li>    `panelID` - The ID of the panel as reported in the `InitiateComms` command.</li><li>    `paramID` - The hardware ID of the encoder.</li><li>    `increment` - The incremental value.</li><li>    `data` - The raw data from the Tangent Hub</li><li>  `UNMANAGED_DISPLAY_REFRESH` - Only used when working in Unmanaged panel mode. Issued when a panel has been connected or the focus of the panel has been returned to your application.</li><li>    `panelID` - The ID of the panel as reported in the `InitiateComms` command.</li><li>    `data` - The raw data from the Tangent Hub</li><li>  `PANEL_CONNECTION_STATE`</li><li>    `panelID` - The ID of the panel as reported in the `InitiateComms` command.</li><li>    `state` - The connected state of the panel, `true` if connected, `false` if disconnected.</li><li>    `data` - The raw data from the Tangent Hub</li></ul>                |

#### [connect](#connect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.connect(applicationName, systemPath[, userPath]) -> boolean, errorMessage` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Connects to the Tangent Hub.                                                                                         |
| **Parameters**                                       | <ul><li>applicationName - Your application name as a string</li><li>systemPath - A string containing the absolute path of the directory that contains the Controls and Default Map XML files.</li><li>[userPath] - An optional string containing the absolute path of the directory that contains the User’s Default Map XML files.</li></ul> |
| **Returns**                                          | <ul><li>success - `true` on success, otherwise `nil`</li><li>errorMessage - The error messages as a string or `nil` if `success` is `true`.</li></ul>          |

#### [connected](#connected)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.connected() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see whether or not you're successfully connected to the Tangent Hub.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>`true` if connected, otherwise `false`</li></ul>          |

#### [disconnect](#disconnect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.disconnect() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Disconnects from the Tangent Hub.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [isTangentHubInstalled](#istangenthubinstalled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.isTangentHubInstalled() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see whether or not the Tangent Hub software is installed.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>`true` if Tangent Hub is installed otherwise `false`.</li></ul>          |

#### [send](#send)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.send(id, metadata) -> boolean, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sends a message to the Tangent Hub.                                                                                         |
| **Parameters**                                       | <ul><li>id - The ID of the message you want to send as defined in `hs.tangent.APP_MESSAGE`</li><li>metadata - A table of values as explained below.</li></ul> |
| **Returns**                                          | <ul><li>success - `true` if connected, otherwise `false`</li><li>errorMessage - An error message if an error occurs, as a string</li></ul>          |
| **Notes**                                            | <ul><li>Full documentation for the Tangent API can be downloaded [here](http://www.tangentwave.co.uk/download/developer-support-pack/).</li><li>The metadata table will accept the following, depending on the `id` provided:</li><li>  `APPLICATION_DEFINITION` - This is sent in response to the `InitiateComms (0x01)` command and establishes communication between the application and the hub.</li><li>    `applicationName` - An string containing the name of the application.</li><li>    `systemPath` - A string containing the absolute path of the directory that contains the Controls and Default Map XML files.</li><li>    `userPath` - A string containing the absolute path of the directory that contains the User’s Default Map XML files.</li><li>  `PARAMETER_VALUE` - Updates the Hub with a parameter value.</li><li>    `paramID` - The ID value of the parameter.</li><li>    `value` - The current value of the parameter.</li><li>    `atDefault` - `true` if the value represents the default, otherwise `false`.</li><li>  `MENU_STRING` - Updates the Hub with a menu value.</li><li>    `menuID` - The ID value of the menu.</li><li>    `valueStr` - The current ‘value’ of the parameter represented as a string.</li><li>    `atDefault` - `true` if the value represents the default, otherwise `false`.</li><li>  `ALL_CHANGE` - Tells the Hub that a large number of software-controls have changed.</li><li>  `MODE_VALUE`</li><li>    `modeID` - The ID value of the mode.</li><li>  `DISPLAY_TEXT`</li><li>    `stringOne` - A line of status text.</li><li>    `stringOneDoubleHeight` - `true` if the string is to be printed double height, otherwise `false`.</li><li>    [`stringTwo`] - An optional line of status text.</li><li>    [`stringTwoDoubleHeight`] - `true` if the string is to be printed double height, otherwise `false` (required if `stringTwo` is supplied).</li><li>    [`stringThree`] - An optional line of status text.</li><li>    [`stringThreeDoubleHeight`] - `true` if the string is to be printed double height, otherwise `false` (required if `stringThree` is supplied).</li><li>  `UNMANAGED_PANEL_CAPABILITIES_REQUEST`</li><li>    `panelID` - The ID of the panel as reported in the `InitiateComms` command.</li><li>  `UNMANAGED_DISPLAY_WRITE`</li><li>    `panelID` - The ID of the panel as reported in the `InitiateComms` command.</li><li>    `displayID` - The ID of the display to be written to.</li><li>    `lineNum` - The line number of the display to be written to with 0 as the top line.</li><li>    `pos` - The position on the line to start writing from with 0 as the first column.</li><li>    `dispStr` - A line of text.</li><li>  `RENAME_CONTROL`</li><li>    `targetID` - The id of any application defined Parameter, Menu, Action or Mode.</li><li>    `nameStr` - The new name string.</li><li>  `HIGHLIGHT_CONTROL`</li><li>    `targetID` - The id of any application defined Parameter, Menu, Action or Mode.</li><li>    `state` - The state to set, `true` for highlighted, `false` for clear.</li><li>  `INDICATE_CONTROL`</li><li>    `targetID` - The id of any application defined Action or Mode.</li><li>    `state` - The state to set, `true` for indicated, `false` for clear.</li><li>  `REQUEST_PANEL_CONNECTION_STATES` - Requests the Hub to respond with a sequence of PanelConnectionState (0x35) commands to report the connected/disconnected status of each configured panel.</li></ul>                |

#### [setLogLevel](#setloglevel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.setLogLevel(loglevel) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the Log Level.                                                                                         |
| **Parameters**                                       | <ul><li>loglevel - can be 'nothing', 'error', 'warning', 'info', 'debug', or 'verbose'; or a corresponding number between 0 and 5</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

