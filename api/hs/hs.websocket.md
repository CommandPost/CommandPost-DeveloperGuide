# [docs](index.md) » hs.websocket
---

Simple websocket client.

## API Overview
* Functions - API calls offered directly by the extension
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [close](#close)
 * [send](#send)
 * [status](#status)

## API Documentation

### Functions

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.websocket.new(url, callback) -> object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Creates a new websocket connection. |
| **Parameters**                                       | <ul><li>url - The URL to the websocket</li><li>callback - A function that's triggered by websocket actions.</li></ul> |
| **Returns**                                          | <ul><li>The <code>hs.websocket</code> object</li></ul> |
| **Notes**                                            | <ul><li>The callback should accept two parameters.</li><li>The first paramater is a string with the following possible options:</li><li>open - The websocket connection has been opened</li><li>closed - The websocket connection has been closed</li><li>fail - The websocket connection has failed</li><li>received - The websocket has received a message</li><li>pong - A pong request has been received</li><li>The second parameter is a string with the recieved message or an error message.</li><li>Given a path '/mysock' and a port of 8000, the websocket URL is as follows:</li><li>ws://localhost:8000/mysock</li><li>wss://localhost:8000/mysock (if SSL enabled)</li></ul> |

### Methods

#### [close](#close)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.websocket:close() -> object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Closes a websocket connection. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>hs.websocket</code> object</li></ul> |

#### [send](#send)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.websocket:send(message) -> object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sends a message to the websocket client |
| **Parameters**                                       | <ul><li>message - A string containing the message to send</li></ul> |
| **Returns**                                          | <ul><li>The <code>hs.websocket</code> object</li></ul> |

#### [status](#status)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.websocket:status() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the status of a websocket. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string containing one of the following options:</li><li>connecting</li><li>open</li><li>closing</li><li>closed</li><li>unknown</li></ul> |

