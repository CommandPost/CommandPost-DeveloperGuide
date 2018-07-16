# [docs](index.md) » cp.rx.go.Throw
---

A [Statement](cp.rx.go.Statement.md) that will throw the provided message.

Example:

```lua
Throw("There was an error: %s", errorMessage)
```

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [Throw](#throw)

## API Documentation

### Constructors

#### [Throw](#throw)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.rx.go.Throw([message[, ...]]) -> Throw` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `Throw` `Statement` that will throw the message when executed. |
| **Parameters**                                       | <ul><li>message  - The optional message to return. May contain <code>string.format</code> tokens * ...      - The optional list of parameters to inject into the message.</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code> which will send the provided error message.</li></ul> |

