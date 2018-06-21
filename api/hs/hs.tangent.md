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
| **Parameters**                                       | <ul><li>callbackFn - a function to set as the callback for <code>hs.tangent</code>. If the value provided is <code>nil</code>, any currently existing callback function is removed.</li></ul>   |
| **Returns**                                          | <ul><li><code>true</code> if successful otherwise <code>false</code></li></ul>            |
| **Notes**                                            | <ul><li>Full documentation for the Tangent API can be downloaded <a href="http://www.tangentwave.co.uk/download/developer-support-pack/">here</a>.</li></ul><ul><li>The callback function should expect 2 arguments and should not return anything:</li></ul><ul><li>id - the message ID of the incoming message</li></ul><ul><li>metadata - A table of data for the Tangent command (see below).</li></ul><ul><li>The metadata table will return the following, depending on the <code>id</code> for the callback:</li></ul><ul><li><code>CONNECTED</code> - Connection To Tangent Hub successfully established.</li></ul><ul><li><code>INITIATE_COMMS</code> - Initiates communication between the Hub and the application.</li></ul><pre><code> * `protocolRev` - The revision number of the protocol.</code></pre><pre><code> * `numPanels` - The number of panels connected.</code></pre><pre><code> * `panels`</code></pre><pre><code>   * `panelID` - The ID of the panel.</code></pre><pre><code>   * `panelType` - The type of panel connected.</code></pre><pre><code> * `data` - The raw data from the Tangent Hub</code></pre><ul><li><code>PARAMETER_CHANGE</code> - Requests that the application increment a parameter.</li></ul><pre><code> * `paramID` - The ID value of the parameter.</code></pre><pre><code> * `increment` - The incremental value which should be applied to the parameter.</code></pre><pre><code> * `data` - The raw data from the Tangent Hub</code></pre><ul><li><code>PARAMETER_RESET</code> - Requests that the application changes a parameter to its reset value.</li></ul><pre><code> * `paramID` - The ID value of the parameter.</code></pre><pre><code> * `data` - The raw data from the Tangent Hub</code></pre><ul><li><code>PARAMETER_VALUE_REQUEST</code> - Requests that the application sends a <code>ParameterValue (0x82)</code> command to the Hub.</li></ul><pre><code> * `paramID` - The ID value of the parameter.</code></pre><pre><code> * `data` - The raw data from the Tangent Hub</code></pre><ul><li><code>MENU_CHANGE</code> - Requests the application change a menu index by +1 or -1.</li></ul><pre><code> * `menuID` - The ID value of the menu.</code></pre><pre><code> * `increment` - The incremental amount by which the menu index should be changed which will always be an integer value of +1 or -1.</code></pre><pre><code> * `data` - The raw data from the Tangent Hub</code></pre><ul><li><code>MENU_RESET</code> - Requests that the application changes a menu to its reset value.</li></ul><pre><code> * `menuID` - The ID value of the menu.</code></pre><pre><code> * `data` - The raw data from the Tangent Hub</code></pre><ul><li><code>MENU_STRING_REQUEST</code> - Requests that the application sends a <code>MenuString (0x83)</code> command to the Hub.</li></ul><pre><code> * `menuID` - The ID value of the menu.</code></pre><pre><code> * `data` - The raw data from the Tangent Hub</code></pre><ul><li><code>ACTION_ON</code> - Requests that the application performs the specified action.</li></ul><pre><code> * `actionID` - The ID value of the action.</code></pre><pre><code> * `data` - The raw data from the Tangent Hub</code></pre><ul><li><code>MODE_CHANGE</code> - Requests that the application changes to the specified mode.</li></ul><pre><code> * `modeID` - The ID value of the mode.</code></pre><pre><code> * `data` - The raw data from the Tangent Hub</code></pre><ul><li><code>TRANSPORT</code> - Requests the application to move the currently active transport.</li></ul><pre><code> * `jogValue` - The number of jog steps to move the transport.</code></pre><pre><code> * `shuttleValue` - An incremental value to add to the shuttle speed.</code></pre><pre><code> * `data` - The raw data from the Tangent Hub</code></pre><ul><li><code>ACTION_OFF</code> - Requests that the application cancels the specified action.</li></ul><pre><code> * `actionID` - The ID value of the action.</code></pre><pre><code> * `data` - The raw data from the Tangent Hub</code></pre><ul><li><code>UNMANAGED_PANEL_CAPABILITIES</code> - Only used when working in Unmanaged panel mode. Sent in response to a <code>UnmanagedPanelCapabilitiesRequest (0xA0)</code> command.</li></ul><pre><code> * `panelID` - The ID of the panel as reported in the `InitiateComms` command.</code></pre><pre><code> * `numButtons` - The number of buttons on the panel.</code></pre><pre><code> * `numEncoders` - The number of encoders on the panel.</code></pre><pre><code> * `numDisplays` - The number of displays on the panel.</code></pre><pre><code> * `numDisplayLines` - The number of lines for each display on the panel.</code></pre><pre><code> * `numDisplayChars` - The number of characters on each line of each display on the panel.</code></pre><pre><code> * `data` - The raw data from the Tangent Hub</code></pre><ul><li><code>UNMANAGED_BUTTON_DOWN</code> - Only used when working in Unmanaged panel mode. Issued when a button has been pressed.</li></ul><pre><code> * `panelID` - The ID of the panel as reported in the `InitiateComms` command.</code></pre><pre><code> * `buttonID` - The hardware ID of the button</code></pre><pre><code> * `data` - The raw data from the Tangent Hub.</code></pre><ul><li><code>UNMANAGED_BUTTON_UP</code> - Only used when working in Unmanaged panel mode. Issued when a button has been released.</li></ul><pre><code> * `panelID` - The ID of the panel as reported in the `InitiateComms` command.</code></pre><pre><code> * `buttonID` - The hardware ID of the button.</code></pre><pre><code> * `data` - The raw data from the Tangent Hub</code></pre><ul><li><code>UNMANAGED_ENCODER_CHANGE</code> - Only used when working in Unmanaged panel mode. Issued when an encoder has been moved.</li></ul><pre><code> * `panelID` - The ID of the panel as reported in the `InitiateComms` command.</code></pre><pre><code> * `paramID` - The hardware ID of the encoder.</code></pre><pre><code> * `increment` - The incremental value.</code></pre><pre><code> * `data` - The raw data from the Tangent Hub</code></pre><ul><li><code>UNMANAGED_DISPLAY_REFRESH</code> - Only used when working in Unmanaged panel mode. Issued when a panel has been connected or the focus of the panel has been returned to your application.</li></ul><pre><code> * `panelID` - The ID of the panel as reported in the `InitiateComms` command.</code></pre><pre><code> * `data` - The raw data from the Tangent Hub</code></pre><ul><li><code>PANEL_CONNECTION_STATE</code></li></ul><pre><code> * `panelID` - The ID of the panel as reported in the `InitiateComms` command.</code></pre><pre><code> * `state` - The connected state of the panel, `true` if connected, `false` if disconnected.</code></pre><pre><code> * `data` - The raw data from the Tangent Hub</code></pre>                 |

#### [connect](#connect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.connect(applicationName, systemPath[, userPath]) -> boolean, errorMessage` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Connects to the Tangent Hub.                                                                                         |
| **Parameters**                                       | <ul><li>applicationName - Your application name as a string</li></ul><ul><li>systemPath - A string containing the absolute path of the directory that contains the Controls and Default Map XML files.</li></ul><ul><li>[userPath] - An optional string containing the absolute path of the directory that contains the User’s Default Map XML files.</li></ul>   |
| **Returns**                                          | <ul><li>success - <code>true</code> on success, otherwise <code>nil</code></li></ul><ul><li>errorMessage - The error messages as a string or <code>nil</code> if <code>success</code> is <code>true</code>.</li></ul>            |

#### [connected](#connected)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.connected() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see whether or not you're successfully connected to the Tangent Hub.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li><code>true</code> if connected, otherwise <code>false</code></li></ul>            |

#### [disconnect](#disconnect)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.disconnect() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Disconnects from the Tangent Hub.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

#### [isTangentHubInstalled](#istangenthubinstalled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.isTangentHubInstalled() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see whether or not the Tangent Hub software is installed.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li><code>true</code> if Tangent Hub is installed otherwise <code>false</code>.</li></ul>            |

#### [send](#send)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.send(id, metadata) -> boolean, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sends a message to the Tangent Hub.                                                                                         |
| **Parameters**                                       | <ul><li>id - The ID of the message you want to send as defined in <code>hs.tangent.APP_MESSAGE</code></li></ul><ul><li>metadata - A table of values as explained below.</li></ul>   |
| **Returns**                                          | <ul><li>success - <code>true</code> if connected, otherwise <code>false</code></li></ul><ul><li>errorMessage - An error message if an error occurs, as a string</li></ul>            |
| **Notes**                                            | <ul><li>Full documentation for the Tangent API can be downloaded <a href="http://www.tangentwave.co.uk/download/developer-support-pack/">here</a>.</li></ul><ul><li>The metadata table will accept the following, depending on the <code>id</code> provided:</li></ul><ul><li><code>APPLICATION_DEFINITION</code> - This is sent in response to the <code>InitiateComms (0x01)</code> command and establishes communication between the application and the hub.</li></ul><pre><code> * `applicationName` - An string containing the name of the application.</code></pre><pre><code> * `systemPath` - A string containing the absolute path of the directory that contains the Controls and Default Map XML files.</code></pre><pre><code> * `userPath` - A string containing the absolute path of the directory that contains the User’s Default Map XML files.</code></pre><ul><li><code>PARAMETER_VALUE</code> - Updates the Hub with a parameter value.</li></ul><pre><code> * `paramID` - The ID value of the parameter.</code></pre><pre><code> * `value` - The current value of the parameter.</code></pre><pre><code> * `atDefault` - `true` if the value represents the default, otherwise `false`.</code></pre><ul><li><code>MENU_STRING</code> - Updates the Hub with a menu value.</li></ul><pre><code> * `menuID` - The ID value of the menu.</code></pre><pre><code> * `valueStr` - The current ‘value’ of the parameter represented as a string.</code></pre><pre><code> * `atDefault` - `true` if the value represents the default, otherwise `false`.</code></pre><ul><li><code>ALL_CHANGE</code> - Tells the Hub that a large number of software-controls have changed.</li></ul><ul><li><code>MODE_VALUE</code></li></ul><pre><code> * `modeID` - The ID value of the mode.</code></pre><ul><li><code>DISPLAY_TEXT</code></li></ul><pre><code> * `stringOne` - A line of status text.</code></pre><pre><code> * `stringOneDoubleHeight` - `true` if the string is to be printed double height, otherwise `false`.</code></pre><pre><code> * [`stringTwo`] - An optional line of status text.</code></pre><pre><code> * [`stringTwoDoubleHeight`] - `true` if the string is to be printed double height, otherwise `false` (required if `stringTwo` is supplied).</code></pre><pre><code> * [`stringThree`] - An optional line of status text.</code></pre><pre><code> * [`stringThreeDoubleHeight`] - `true` if the string is to be printed double height, otherwise `false` (required if `stringThree` is supplied).</code></pre><ul><li><code>UNMANAGED_PANEL_CAPABILITIES_REQUEST</code></li></ul><pre><code> * `panelID` - The ID of the panel as reported in the `InitiateComms` command.</code></pre><ul><li><code>UNMANAGED_DISPLAY_WRITE</code></li></ul><pre><code> * `panelID` - The ID of the panel as reported in the `InitiateComms` command.</code></pre><pre><code> * `displayID` - The ID of the display to be written to.</code></pre><pre><code> * `lineNum` - The line number of the display to be written to with 0 as the top line.</code></pre><pre><code> * `pos` - The position on the line to start writing from with 0 as the first column.</code></pre><pre><code> * `dispStr` - A line of text.</code></pre><ul><li><code>RENAME_CONTROL</code></li></ul><pre><code> * `targetID` - The id of any application defined Parameter, Menu, Action or Mode.</code></pre><pre><code> * `nameStr` - The new name string.</code></pre><ul><li><code>HIGHLIGHT_CONTROL</code></li></ul><pre><code> * `targetID` - The id of any application defined Parameter, Menu, Action or Mode.</code></pre><pre><code> * `state` - The state to set, `true` for highlighted, `false` for clear.</code></pre><ul><li><code>INDICATE_CONTROL</code></li></ul><pre><code> * `targetID` - The id of any application defined Action or Mode.</code></pre><pre><code> * `state` - The state to set, `true` for indicated, `false` for clear.</code></pre><ul><li><code>REQUEST_PANEL_CONNECTION_STATES</code> - Requests the Hub to respond with a sequence of PanelConnectionState (0x35) commands to report the connected/disconnected status of each configured panel.</li></ul>                 |

#### [setLogLevel](#setloglevel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tangent.setLogLevel(loglevel) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the Log Level.                                                                                         |
| **Parameters**                                       | <ul><li>loglevel - can be 'nothing', 'error', 'warning', 'info', 'debug', or 'verbose'; or a corresponding number between 0 and 5</li></ul>   |
| **Returns**                                          | <ul><li>None</li></ul>            |

