# [docs](index.md) » cp.collect.Queue
---

A "double-ended queue" implementation. This allows pushing and popping
values to the left or right side of the queue. This can be used for
classic 'stack' and 'queue' uses - for a stack, push and pop from one end,
for a queue, push and pop from opposite ends.

`#` will always return the size of the queue.

The left-most item in the queue wil always be at index `1`, the right-most
will be at index `#`.

You can iterate via `ipairs`, but as with all tables, the queue contains any
`nil` values, it will stop at that point. To iterate the whole queue, you
need to use the `#` operator. Eg:

```lua
local q = Queue(1, nil, 3)
for i,v in ipairs(q) do print(v) end  -- Outputs "1"
for i = 1, #q do print(v) end -- Outputs "1", "nil", "3"
```

## API Overview
* Functions - API calls offered directly by the extension
 * [len](#len)
 * [peekLeft](#peekleft)
 * [peekRight](#peekright)
 * [popLeft](#popleft)
 * [popRight](#popright)
 * [pushLeft](#pushleft)
 * [pushRight](#pushright)
 * [removeItem](#removeitem)
 * [removeItem](#removeitem)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [len](#len)
 * [peekLeft](#peekleft)
 * [peekRight](#peekright)
 * [popLeft](#popleft)
 * [popRight](#popright)
 * [pushLeft](#pushleft)
 * [pushRight](#pushright)

## API Documentation

### Functions

#### [len](#len)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.Queue.len(queue) -> anything` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the number of items in the queue. |
| **Parameters**                                       | <ul><li>queue        - The queue to check.</li></ul> |
| **Returns**                                          | <ul><li>The total number of items.</li></ul> |

#### [peekLeft](#peekleft)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.Queue.peekLeft(queue) -> anything` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the left-most value from the `queue` without removig it. |
| **Parameters**                                       | <ul><li>queue        - The queue to peek into.</li></ul> |
| **Returns**                                          | <ul><li>The left-most value of the <code>Queue</code>.</li></ul> |

#### [peekRight](#peekright)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.Queue.peekRight(queue) -> anything` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the right-most value from the `queue` without removig it. |
| **Parameters**                                       | <ul><li>queue        - The queue to peek into.</li></ul> |
| **Returns**                                          | <ul><li>The right-most value of the <code>Queue</code>.</li></ul> |

#### [popLeft](#popleft)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.Queue.popLeft(queue) -> anything` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Removes the left-most value from the `queue` and returns it. |
| **Parameters**                                       | <ul><li>queue        - The queue to pop from.</li></ul> |
| **Returns**                                          | <ul><li>The left-most value of the <code>Queue</code>.</li></ul> |

#### [popRight](#popright)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.Queue.popRight(queue) -> anything` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Removes the right-most value from the `queue` and returns it. |
| **Parameters**                                       | <ul><li>queue        - The queue to pop from.</li></ul> |
| **Returns**                                          | <ul><li>The right-most value of the <code>Queue</code>.</li></ul> |

#### [pushLeft](#pushleft)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.Queue.pushLeft(queue, ...) -> cp.collect.Queue` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Pushes the values to the left side of the `queue`. |
| **Parameters**                                       | <ul><li>queue        - The queue to push into. * ...          - The values to push.</li></ul> |
| **Returns**                                          | <ul><li>The same <code>Queue</code> instance.</li></ul> |

#### [pushRight](#pushright)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.Queue.pushRight(queue, ...) -> cp.collect.Queue` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Pushes the values to the right side of the `queue`. |
| **Parameters**                                       | <ul><li>queue        - The queue to push into. * ...          - The values to push.</li></ul> |
| **Returns**                                          | <ul><li>The same <code>Queue</code> instance.</li></ul> |

#### [removeItem](#removeitem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.Queue:removeItem(item) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Attempts to remove the specified item from the queue. |
| **Parameters**                                       | <ul><li>item         - The item to remove, if present.</li></ul> |
| **Returns**                                          | <ul><li>The index of the item, or <code>nil</code> if not found.</li></ul> |

#### [removeItem](#removeitem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.Queue.removeItem(queue, item) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Attempts to remove the specified item from the queue. |
| **Parameters**                                       | <ul><li>queue        - The queue to modify. * item         - The item to remove, if present.</li></ul> |
| **Returns**                                          | <ul><li>The index of the item, or <code>nil</code> if not found.</li></ul> |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.Queue.new([...]) -> cp.collect.Queue` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new Queue. |
| **Parameters**                                       | <ul><li>...      - The optional list of values to add to the right of the queue.</li></ul> |
| **Returns**                                          | <ul><li>the new <code>Queue</code>.</li></ul> |
| **Notes**                                            | <ul><li>You can also create a new queue by calling <code>Queue(..)</code> directly.</li></ul> |

### Methods

#### [len](#len)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.Queue:len(queue) -> anything` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the number of items in the queue. |
| **Parameters**                                       | <ul><li>queue        - The queue to check.</li></ul> |
| **Returns**                                          | <ul><li>The total number of items.</li></ul> |

#### [peekLeft](#peekleft)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.Queue:peekLeft() -> anything` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the left-most value from the `queue` without removig it. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The left-most value of the <code>Queue</code>.</li></ul> |

#### [peekRight](#peekright)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.Queue:peekRight() -> anything` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the right-most value from the `queue` without removig it. |
| **Parameters**                                       | <ul><li>queue        - The queue to peek into.</li></ul> |
| **Returns**                                          | <ul><li>The right-most value of the <code>Queue</code>.</li></ul> |

#### [popLeft](#popleft)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.Queue:popLeft() -> anything` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Removes the left-most value from the `queue` and returns it. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The left-most value of the <code>Queue</code>.</li></ul> |

#### [popRight](#popright)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.Queue:popRight() -> anything` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Removes the right-most value from the `queue` and returns it. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The right-most value of the <code>Queue</code>.</li></ul> |

#### [pushLeft](#pushleft)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.Queue:pushLeft(...) -> cp.collect.Queue` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Pushes the values to the left side of the `queue`. |
| **Parameters**                                       | <ul><li>...          - The values to push.</li></ul> |
| **Returns**                                          | <ul><li>The same <code>Queue</code> instance.</li></ul> |

#### [pushRight](#pushright)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.Queue:pushRight(...) -> cp.collect.Queue` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Pushes the values to the right side of the `queue`. |
| **Parameters**                                       | <ul><li>...          - The values to push.</li></ul> |
| **Returns**                                          | <ul><li>The same <code>Queue</code> instance.</li></ul> |

