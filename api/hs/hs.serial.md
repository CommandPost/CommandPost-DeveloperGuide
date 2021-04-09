# [docs](index.md) » hs.serial
---

Communicate with external devices through a serial port (most commonly RS-232).

Powered by ORSSerialPort. Thrown together by @latenitefilms.

Copyright (c) 2011-2012 Andrew R. Madsen (andrew@openreelsoftware.com)

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

## API Overview
* Functions - API calls offered directly by the extension
 * [availablePortNames](#availableportnames)
 * [availablePortPaths](#availableportpaths)
 * [deviceCallback](#devicecallback)
* Constructors - API calls which return an object, typically one that offers API methods
 * [newFromName](#newfromname)
 * [newFromPath](#newfrompath)
* Methods - API calls which can only be made on an object returned by a constructor
 * [baudRate](#baudrate)
 * [callback](#callback)
 * [close](#close)
 * [dataBits](#databits)
 * [isOpen](#isopen)
 * [name](#name)
 * [open](#open)
 * [parity](#parity)
 * [path](#path)
 * [sendData](#senddata)
 * [shouldEchoReceivedData](#shouldechoreceiveddata)
 * [stopBits](#stopbits)
 * [usesDTRDSRFlowControl](#usesdtrdsrflowcontrol)
 * [usesRTSCTSFlowControl](#usesrtsctsflowcontrol)

## API Documentation

### Functions

#### [availablePortNames](#availableportnames)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.serial.availablePortNames() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a table of currently connected serial ports names. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table containing the names of any connected serial port names as strings.</li></ul> |

#### [availablePortPaths](#availableportpaths)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.serial.availablePortPaths() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a table of currently connected serial ports paths. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table containing the names of any connected serial port paths as strings.</li></ul> |

#### [deviceCallback](#devicecallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.serial.deviceCallback(callbackFn) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | A callback that's triggered when a serial port is added or removed from the system. |
| **Parameters**                                       | <ul><li>callbackFn - the callback function to trigger.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |
| **Notes**                                            | <ul><li>The callback function should expect 1 argument and should not return anything:</li><li><code>devices</code> - A table containing the names of any serial ports connected as strings.</li></ul> |

### Constructors

#### [newFromName](#newfromname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.serial.newFromName(portName) -> serialPortObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `hs.serial` object using the port name. |
| **Parameters**                                       | <ul><li>portName - A string containing the port name.</li></ul> |
| **Returns**                                          | <ul><li>An <code>hs.serial</code> object or <code>nil</code> if an error occured.</li></ul> |
| **Notes**                                            | <ul><li>A valid port name can be found by checking <code>hs.serial.availablePortNames()</code>.</li></ul> |

#### [newFromPath](#newfrompath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.serial.newFromPath(path) -> serialPortObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `hs.serial` object using a path. |
| **Parameters**                                       | <ul><li>path - A string containing the path (i.e. "/dev/cu.usbserial").</li></ul> |
| **Returns**                                          | <ul><li>An <code>hs.serial</code> object or <code>nil</code> if an error occured.</li></ul> |
| **Notes**                                            | <ul><li>A valid port name can be found by checking <code>hs.serial.availablePortPaths()</code>.</li></ul> |

### Methods

#### [baudRate](#baudrate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.serial:baudRate([value], [allowNonStandardBaudRates]) -> number | serialPortObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets or sets the baud rate for the serial port. |
| **Parameters**                                       | <ul><li>value - An optional number to set the baud rate.</li><li>[allowNonStandardBaudRates] - An optional boolean to enable non-standard baud rates. Defaults to <code>false</code>.</li></ul> |
| **Returns**                                          | <ul><li>If a value is specified, then this method returns the serial port object. Otherwise this method returns the baud rate as a number</li></ul> |
| **Notes**                                            | <ul><li>This function supports the following standard baud rates as numbers: 300, 1200, 2400, 4800, 9600, 14400, 19200, 28800, 38400, 57600, 115200, 230400.</li><li>If no baud rate is supplied, it defaults to 115200.</li></ul> |

#### [callback](#callback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.serial:callback(callbackFn) -> serialPortObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets or removes a callback function for the `hs.serial` object. |
| **Parameters**                                       | <ul><li><code>callbackFn</code> - a function to set as the callback for this <code>hs.serial</code> object.  If the value provided is <code>nil</code>, any currently existing callback function is removed.</li></ul> |
| **Returns**                                          | <ul><li>The <code>hs.serial</code> object</li></ul> |
| **Notes**                                            | <ul><li>The callback function should expect 4 arguments and should not return anything:</li><li><code>serialPortObject</code> - The serial port object that triggered the callback.</li><li><code>callbackType</code> - A string containing "opened", "closed", "received", "removed" or "error".</li><li><code>message</code> - If the <code>callbackType</code> is "received", then this will be the data received as a string. If the <code>callbackType</code> is "error", this will be the error message as a string.</li><li><code>hexadecimalString</code> - If the <code>callbackType</code> is "received", then this will be the data received as a hexadecimal string.</li></ul> |

#### [close](#close)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.serial:close() -> serialPortObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Closes the serial port. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>hs.serial</code> object.</li></ul> |

#### [dataBits](#databits)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.serial:dataBits([value]) -> number | serialPortObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets or sets the number of data bits for the serial port. |
| **Parameters**                                       | <ul><li>value - An optional number to set the number of data bits. It can be 5 to 8.</li></ul> |
| **Returns**                                          | <ul><li>If a value is specified, then this method returns the serial port object. Otherwise this method returns the data bits as a number.</li><li>The default value is 8.</li></ul> |

#### [isOpen](#isopen)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.serial:isOpen() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets whether or not a serial port is open. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if open, otherwise <code>false</code>.</li></ul> |

#### [name](#name)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.serial:name() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the name of a `hs.serial` object. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The name as a string.</li></ul> |

#### [open](#open)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.serial:open() -> serialPortObject | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Opens the serial port. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>hs.serial</code> object or <code>nil</code> if the port could not be opened.</li></ul> |

#### [parity](#parity)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.serial:parity([value]) -> string | serialPortObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets or sets the parity for the serial port. |
| **Parameters**                                       | <ul><li>value - An optional string to set the parity. It can be "none", "odd" or "even".</li></ul> |
| **Returns**                                          | <ul><li>If a value is specified, then this method returns the serial port object. Otherwise this method returns a string value of "none", "odd" or "even".</li></ul> |

#### [path](#path)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.serial:path() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the path of a `hs.serial` object. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The path as a string.</li></ul> |

#### [sendData](#senddata)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.serial:sendData(value) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sends data via a serial port. |
| **Parameters**                                       | <ul><li>value - A string of data to send.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [shouldEchoReceivedData](#shouldechoreceiveddata)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.serial:shouldEchoReceivedData([value]) -> boolean | serialPortObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets or sets whether the port should echo received data. |
| **Parameters**                                       | <ul><li>value - An optional boolean.</li></ul> |
| **Returns**                                          | <ul><li>If a value is specified, then this method returns the serial port object. Otherwise this method returns a boolean.</li><li>The default value is <code>false</code>.</li></ul> |

#### [stopBits](#stopbits)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.serial:stopBits([value]) -> number | serialPortObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets or sets the number of stop bits for the serial port. |
| **Parameters**                                       | <ul><li>value - An optional number to set the number of stop bits. It can be 1 or 2.</li></ul> |
| **Returns**                                          | <ul><li>If a value is specified, then this method returns the serial port object. Otherwise this method returns the number of stop bits as a number.</li><li>The default value is 1.</li></ul> |

#### [usesDTRDSRFlowControl](#usesdtrdsrflowcontrol)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.serial:usesDTRDSRFlowControl([value]) -> boolean | serialPortObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets or sets whether the port should use DTR/DSR Flow Control. |
| **Parameters**                                       | <ul><li>value - An optional boolean.</li></ul> |
| **Returns**                                          | <ul><li>If a value is specified, then this method returns the serial port object. Otherwise this method returns a boolean.</li><li>The default value is <code>false</code>.</li></ul> |

#### [usesRTSCTSFlowControl](#usesrtsctsflowcontrol)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.serial:usesRTSCTSFlowControl([value]) -> boolean | serialPortObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets or sets whether the port should use RTS/CTS Flow Control. |
| **Parameters**                                       | <ul><li>value - An optional boolean.</li></ul> |
| **Returns**                                          | <ul><li>If a value is specified, then this method returns the serial port object. Otherwise this method returns a boolean.</li><li>The default value is <code>false</code>.</li></ul> |

