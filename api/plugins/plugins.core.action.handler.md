# [docs](index.md) » plugins.core.action.handler
---

A support class for handler handlers. It is not used directly, rather
it is a 'super class' that provides common functionality.

Instances of the class primarily need to provide functions for the following:

```lua
local handler = actionManager:addHandler("foobar")
:onChoices(function(choices) ... end)
:onExecute(function(action) ... end)
```

The choices added to the `choices` should have the `params` value set to a table
containing the details of the action to execute if the choice is selected.

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [cached](#cached)
 * [choices](#choices)
* Methods - API calls which can only be made on an object returned by a constructor
 * [actionId](#actionid)
 * [execute](#execute)
 * [group](#group)
 * [id](#id)
 * [onActionId](#onactionid)
 * [onChoices](#onchoices)
 * [onExecute](#onexecute)
 * [reset](#reset)

## API Documentation

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.handler.new(id, group) -> handler` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new handler with the specified ID.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>id</code>      - The unique ID of the action handler.* <code>group</code>   - The group the handler belongs to.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The new action handler instance.</li><br /></ul>                                           |

### Fields

#### [cached](#cached)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.handler.cached <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | If set to `true` (the default), any choices created will be cached until [reset] is called.                                                                                         |

#### [choices](#choices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.handler.choices <cp.prop: cp.choices; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Provides `cp.choices` instance for the handler. May be watched/monitored/etc.                                                                                         |

### Methods

#### [actionId](#actionid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.handler:actionId(action) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a string that can be used as a unique ID for the action details.                                                                                         |

#### [execute](#execute)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.handler:execute(action) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Executes the action, based on values in the table.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>action</code>      - A table of details about the action.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if the execution succeeded.</li><br /></ul>                                           |

#### [group](#group)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.handler:group() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the group for this handler.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>Group as string.</li><br /></ul>                                           |

#### [id](#id)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.handler:id() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the ID for this handler.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The ID string.</li><br /></ul>                                           |

#### [onActionId](#onactionid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.handler:onActionId(actionFn) -> handler` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Configures a function to handle converting an action to unique ID.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>actionFn</code>    - The function with a signature of <code>function(action) -&gt; string</code></li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>This action handler.</li><br /></ul>                                           |

#### [onChoices](#onchoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.handler:onChoices(choicesFn) -> handler` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a callback function which will receive the `cp.choices` instance to add                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>choicesFn</code>       - The function with the signature of <code>function(choices) -&gt; nothing</code></li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>This action handler.</li><br /></ul>                                           |

#### [onExecute](#onexecute)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.handler:onExecute(executeFn) -> handler` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Configures the function to call when a choice is executed. This will be passed                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>executeFn</code>       - The function to call when executing.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>This action handler.</li><br /></ul>                                           |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.handler:reset([updateNow]) -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Resets the handler, clearing any cached result and requesting new ones.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>updateNow</code>   - (optional) If <code>true</code>, the choices will update immediately, otherwise they will update when the choices are next requested.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>Nothing</li><br /></ul>                                           |

