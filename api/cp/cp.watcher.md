# [docs](index.md) » cp.watcher
---

This extension provides support for setting up 'event watchers'.

For example, if you want to allow interested parties to watch for 'update'
events, you might have something like this:

```lua
local thing = {}

thing.watchers = watcher.new('update')

thing.watch(events)
	return thing.watchers:watch(events)
end

thing.update(value)
	thing.value = value
	thing.watchers:notify('update', value)
end
```

Then, your other code could get notifications like so:

```lua
thing.watch({
	update = function(value) print "New value is "..value end
})
```

Then, whenever `thing.update(xxx)` is called, the watcher will output `"New value is xxx"`.

## API Overview
* Functions - API calls offered directly by the extension
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [events](#events)
 * [getCount](#getcount)
 * [notify](#notify)
 * [unwatch](#unwatch)
 * [watch](#watch)

## API Documentation

### Functions

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.watcher.new(...) -> watcher` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Constructs a new watcher instance.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>...</code> - The list of event name strings supported by the watcher.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a new watcher instance</li><br /></ul>                                           |

### Methods

#### [events](#events)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.watcher:events()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a list of the event names supported by this watcher.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The table of event names.</li><br /></ul>                                           |

#### [getCount](#getcount)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.watcher:getCount()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the number of watchers currently registered.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The number of watchers.</li><br /></ul>                                           |

#### [notify](#notify)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.watcher:notify(type, ...) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Notifies watchers of the specified event type.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>type</code>   - The event type to notify. Must be one of the supported events. * <code>...</code>    - These parameters are passed directly to the event watcher functions.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>Nothing.</li><br /></ul>                                           |

#### [unwatch](#unwatch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.watcher:unwatch(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Removes the watchers which were added with the specified ID.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>id</code>     - The unique ID returned from <code>watch</code>.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if a watcher with the specified ID exists and was successfully removed.</li><br /></ul>                                           |

#### [watch](#watch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.watcher:watch(events) -> id` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a watcher for the specified events.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>events</code>     - A table of functions, one for each event to watch.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A unique ID that can be passed to <code>unwatch</code> to stop watching.</li><br /></ul>                                           |

