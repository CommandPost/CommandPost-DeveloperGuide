# [docs](index.md) » plugins.finalcutpro.action.activator
---

This module provides provides a way of activating choices provided by action handlers.
It also provide support for making a particular action a favourite, returning
results based on popularity, and completely hiding particular actions, or categories of action.

Activators are accessed via the [action manager](plugins.finalcutpro.action.manager.md) like so:

```lua
local activator = actionManager.getActivator("foobar")
activator:disableHandler("videoEffect")
activator:show()
```

Any changes made to the settings of a finder (such as calling `disableHandler` above) will
be preserved for future loads of the finder with the same ID. They are also local
to instances of this activator, so disabling "videoEffect" in the "foobar" activator
will not affect the "yadayada" activator.

## API Overview
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [activeHandlers](#activehandlers)
 * [allowedHandlers](#allowedhandlers)
 * [hiddenChoices](#hiddenchoices)
* Methods - API calls which can only be made on an object returned by a constructor
 * [activeChoices](#activechoices)
 * [allChoices](#allchoices)
 * [allowHandlers](#allowhandlers)
 * [disableAllHandlers](#disableallhandlers)
 * [disableHandler](#disablehandler)
 * [enableAllHandlers](#enableallhandlers)
 * [enableHandler](#enablehandler)
 * [favoriteChoice](#favoritechoice)
 * [getActiveHandler](#getactivehandler)
 * [getPopularity](#getpopularity)
 * [hideChoice](#hidechoice)
 * [id](#id)
 * [incPopularity](#incpopularity)
 * [isDisabledHandler](#isdisabledhandler)
 * [isHiddenChoice](#ishiddenchoice)
 * [onActivate](#onactivate)
 * [preloadChoices](#preloadchoices)
 * [refresh](#refresh)
 * [show](#show)
 * [sortChoices](#sortchoices)
 * [unfavoriteChoice](#unfavoritechoice)
 * [unhiddenChoices](#unhiddenchoices)
 * [unhideChoice](#unhidechoice)

## API Documentation

### Fields

#### [activeHandlers](#activehandlers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.action.activator.activeHandlers <cp.prop: table of handlers>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Contains the table of active handlers. A handler is active if it is both allowed and enabled.                                                                                         |

#### [allowedHandlers](#allowedhandlers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.action.activator:allowedHandlers <cp.prop: table of handlers; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Contains all handlers that are allowed in this activator.                                                                                         |

#### [hiddenChoices](#hiddenchoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.action.activator.hiddenChoices <cp.prop: table of booleans>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Contains the set of choice IDs which are hidden in this activator, mapped to a boolean value.                                                                                         |

### Methods

#### [activeChoices](#activechoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.action.activator:activeChoices() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a table with active choices. If [showHidden](#showHidden) is set to `true`  hidden                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* Table of choices that can be displayed by an `hs.chooser`.</li></ul>          |

#### [allChoices](#allchoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.action.activator:allChoices() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a table of all available choices, even if hidden. Choices from                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* Table of choices that can be displayed by an `hs.chooser`.</li></ul>          |

#### [allowHandlers](#allowhandlers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.action.activator:allowHandlers(...) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Specifies that only the handlers with the specified IDs will be active in                                                                                         |
| **Parameters**                                       | <ul><li>* `...`		- The list of Handler ID strings to allow.</li></ul> |
| **Returns**                                          | <ul><li>* `true` if the handlers were found.</li></ul>          |

#### [disableAllHandlers](#disableallhandlers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.action.activator:disableAllHandlers() -> nothing` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Disables the all allowed handlers.                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* Nothing</li></ul>          |

#### [disableHandler](#disablehandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.action.activator:disableHandler(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Disables the handler with the specified ID.                                                                                         |
| **Parameters**                                       | <ul><li>* `id`		- The unique action handler ID.</li></ul> |
| **Returns**                                          | <ul><li>* `true` if the handler exists and was disabled.</li></ul>          |

#### [enableAllHandlers](#enableallhandlers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.action.activator:enableAllHandlers() -> nothing` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Enables the all allowed handlers.                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* Nothing</li></ul>          |

#### [enableHandler](#enablehandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.action.activator:enableHandler(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Enables the handler with the specified ID.                                                                                         |
| **Parameters**                                       | <ul><li>* `id`		- The unique action handler ID.</li></ul> |
| **Returns**                                          | <ul><li>* `true` if the handler exists and was enabled.</li></ul>          |

#### [favoriteChoice](#favoritechoice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.action.activator:favoriteChoice(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Marks the choice with the specified ID as a favorite.                                                                                         |
| **Parameters**                                       | <ul><li>* `id`			- The choice ID to favorite.</li></ul> |
| **Returns**                                          | <ul><li>* `true` if successfully favorited.</li></ul>          |

#### [getActiveHandler](#getactivehandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.action.activator:getActiveHandler(id) -> handler` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the active handler with the specified ID, or `nil` if not available.                                                                                         |
| **Parameters**                                       | <ul><li>* `id`		- The Handler ID</li></ul> |
| **Returns**                                          | <ul><li>* The action handler, or `nil`.</li></ul>          |

#### [getPopularity](#getpopularity)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.action.activator:getPopularity(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the popularity of the specified choice.                                                                                         |
| **Parameters**                                       | <ul><li>* `id`			- The choice ID to retrieve.</li></ul> |
| **Returns**                                          | <ul><li>* The number of times the choice has been executed.</li></ul>          |

#### [hideChoice](#hidechoice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.action.activator:hideChoice(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides the choice with the specified ID.                                                                                         |
| **Parameters**                                       | <ul><li>* `id`			- The choice ID to hide.</li></ul> |
| **Returns**                                          | <ul><li>* `true` if successfully hidden.</li></ul>          |

#### [id](#id)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.action.activator:id() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the activator's unique ID.                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* The activator ID.</li></ul>          |

#### [incPopularity](#incpopularity)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.action.activator:incPopularity(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Marks the choice with the specified ID as not a favorite.                                                                                         |
| **Parameters**                                       | <ul><li>* `id`			- The choice ID to unfavorite.</li></ul> |
| **Returns**                                          | <ul><li>* `true` if successfully unfavorited.</li></ul>          |

#### [isDisabledHandler](#isdisabledhandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.action.activator:isDisabledHandler(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns `true` if the specified handler is disabled.                                                                                         |
| **Parameters**                                       | <ul><li>* `id`			- The handler ID.</li></ul> |
| **Returns**                                          | <ul><li>* `true` if the handler is disabled.</li></ul>          |

#### [isHiddenChoice](#ishiddenchoice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.action.activator:isHiddenChoice(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Checks if the specified choice is hidden.                                                                                         |
| **Parameters**                                       | <ul><li>* `id`			- The choice ID to check.</li></ul> |
| **Returns**                                          | <ul><li>* `true` if currently hidden.</li></ul>          |

#### [onActivate](#onactivate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.action.activator:onActivate(activateFn) -> activator` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Registers the provided function to handle 'activate' actions, when the user selects                                                                                         |
| **Parameters**                                       | <ul><li>* `activateFn`		- The function to call when an item is activated.</li></ul> |
| **Returns**                                          | <ul><li>* The activator.</li></ul>          |

#### [preloadChoices](#preloadchoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.action.activator:preloadChoices([afterSeconds]) -> activator` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Indicates the activator should preload the choices after a number of seconds.                                                                                         |
| **Parameters**                                       | <ul><li>* `afterSeconds`	- The number of seconds to wait before preloading.</li></ul> |
| **Returns**                                          | <ul><li>* The activator.</li></ul>          |

#### [refresh](#refresh)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.action.activator:refresh()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Clears the existing set of choices and requests new ones from enabled action handlers.                                                                                         |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.action.activator:show()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows a chooser listing the available actions. When selected by the user,                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* Nothing</li></ul>          |

#### [sortChoices](#sortchoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.action.activator:sortChoices() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sorts the current set of choices in the activator. It takes into account                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* `true` if the action executed successfully.</li></ul>          |

#### [unfavoriteChoice](#unfavoritechoice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.action.activator:unfavoriteChoice(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Marks the choice with the specified ID as not a favorite.                                                                                         |
| **Parameters**                                       | <ul><li>* `id`			- The choice ID to unfavorite.</li></ul> |
| **Returns**                                          | <ul><li>* `true` if successfully unfavorited.</li></ul>          |

#### [unhiddenChoices](#unhiddenchoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.action.activator:unhiddenChoices() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a table with visible choices.                                                                                         |
| **Parameters**                                       | <ul><li>* None</li></ul> |
| **Returns**                                          | <ul><li>* Table of choices that can be displayed by an `hs.chooser`.</li></ul>          |

#### [unhideChoice](#unhidechoice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.action.activator:unhideChoice(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Reveals the choice with the specified ID.                                                                                         |
| **Parameters**                                       | <ul><li>* `id`			- The choice ID to hide.</li></ul> |
| **Returns**                                          | <ul><li>* `true` if successfully unhidden.</li></ul>          |

