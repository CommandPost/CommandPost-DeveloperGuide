# [docs](index.md) » cp.spec.Message
---

Provides an Message message, which can be thrown via the `error` function.

## API Overview
* Functions - API calls offered directly by the extension
 * [is](#is)
* Constructors - API calls which return an object, typically one that offers API methods
 * [Message](#message)
* Methods - API calls which can only be made on an object returned by a constructor
 * [traceback](#traceback)

## API Documentation

### Functions

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Message.is(other) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the `other` is an instance of the `Message` class. |

### Constructors

#### [Message](#message)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Message(message)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new Message message. |
| **Parameters**                                       | <ul><li>message   - the message to send.</li></ul> |

### Methods

#### [traceback](#traceback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.spec.Message:traceback()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Stores the `debug.traceback` result at the present time. Can be retrieved via `stacktrace` |

