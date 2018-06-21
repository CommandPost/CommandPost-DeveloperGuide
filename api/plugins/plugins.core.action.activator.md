# [docs](index.md) » plugins.core.action.activator
---

This module provides provides a way of activating choices provided by action handlers.
It also provide support for making a particular action a favourite, returning
results based on popularity, and completely hiding particular actions, or categories of action.

Activators are accessed via the [action manager](plugins.core.action.manager.md) like so:

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
 * [reducedTransparency](#reducedtransparency)
* Methods - API calls which can only be made on an object returned by a constructor
 * [activate](#activate)
 * [activeChoices](#activechoices)
 * [allChoices](#allchoices)
 * [allowHandlers](#allowhandlers)
 * [disableAllHandlers](#disableallhandlers)
 * [disableHandler](#disablehandler)
 * [enableAllHandlers](#enableallhandlers)
 * [enableHandler](#enablehandler)
 * [favoriteChoice](#favoritechoice)
 * [findChoice](#findchoice)
 * [getActiveHandler](#getactivehandler)
 * [getPopularity](#getpopularity)
 * [hide](#hide)
 * [hideChoice](#hidechoice)
 * [id](#id)
 * [incPopularity](#incpopularity)
 * [isDisabledHandler](#isdisabledhandler)
 * [isHiddenChoice](#ishiddenchoice)
 * [onActivate](#onactivate)
 * [preloadChoices](#preloadchoices)
 * [refresh](#refresh)
 * [refreshChooser](#refreshchooser)
 * [rightClickAction](#rightclickaction)
 * [rightClickMain](#rightclickmain)
 * [show](#show)
 * [sortChoices](#sortchoices)
 * [unfavoriteChoice](#unfavoritechoice)
 * [unhiddenChoices](#unhiddenchoices)
 * [unhideChoice](#unhidechoice)

## API Documentation

### Fields

#### [reducedTransparency](#reducedtransparency)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator.reducedTransparency <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | A property which will be true if the 'reduce transparency' mode is enabled.                                                                                         |

### Methods

#### [activate](#activate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:activate(result) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Triggered when the chooser is closed.                                                                                         |
| **Parameters**                                       |  * `result`      - The result from the chooser.                                       |
| **Returns**                                          |  * None                                                |

#### [activeChoices](#activechoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:activeChoices() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a table with active choices. If [showHidden](#showHidden) is set to `true`  hidden                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * Table of choices that can be displayed by an `hs.chooser`.                                                |

#### [allChoices](#allchoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:allChoices() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a table of all available choices, even if hidden. Choices from                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * Table of choices that can be displayed by an `hs.chooser`.                                                |

#### [allowHandlers](#allowhandlers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:allowHandlers(...) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Specifies that only the handlers with the specified IDs will be active in                                                                                         |
| **Parameters**                                       |  * `...`     - The list of Handler ID strings to allow.                                       |
| **Returns**                                          |  * `true` if the handlers were found.                                                |

#### [disableAllHandlers](#disableallhandlers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:disableAllHandlers() -> nothing` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Disables the all allowed handlers.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * Nothing                                                |

#### [disableHandler](#disablehandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:disableHandler(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Disables the handler with the specified ID.                                                                                         |
| **Parameters**                                       |  * `id`      - The unique action handler ID.                                       |
| **Returns**                                          |  * `true` if the handler exists and was disabled.                                                |

#### [enableAllHandlers](#enableallhandlers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:enableAllHandlers() -> nothing` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Enables the all allowed handlers.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * Nothing                                                |

#### [enableHandler](#enablehandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:enableHandler(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Enables the handler with the specified ID.                                                                                         |
| **Parameters**                                       |  * `id`      - The unique action handler ID.                                       |
| **Returns**                                          |  * `true` if the handler exists and was enabled.                                                |

#### [favoriteChoice](#favoritechoice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:favoriteChoice(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Marks the choice with the specified ID as a favorite.                                                                                         |
| **Parameters**                                       |  * `id`          - The choice ID to favorite.                                       |
| **Returns**                                          |  * `true` if successfully favorited otherwise `false`.                                                |

#### [findChoice](#findchoice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:findChoice(id) -> choice` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets a choice                                                                                         |
| **Parameters**                                       |  * `id`          - The choice ID.                                       |
| **Returns**                                          |  * The choice or `nil` if not found                                                |

#### [getActiveHandler](#getactivehandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:getActiveHandler(id) -> handler` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the active handler with the specified ID, or `nil` if not available.                                                                                         |
| **Parameters**                                       |  * `id`      - The Handler ID                                       |
| **Returns**                                          |  * The action handler, or `nil`.                                                |

#### [getPopularity](#getpopularity)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:getPopularity(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the popularity of the specified choice.                                                                                         |
| **Parameters**                                       |  * `id`          - The choice ID to retrieve.                                       |
| **Returns**                                          |  * The number of times the choice has been executed.                                                |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:hide()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides a chooser listing the available actions.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [hideChoice](#hidechoice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:hideChoice(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides the choice with the specified ID.                                                                                         |
| **Parameters**                                       |  * `id`          - The choice ID to hide.                                       |
| **Returns**                                          |  * `true` if successfully hidden otherwise `false`.                                                |

#### [id](#id)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:id() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the activator's unique ID.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The activator ID.                                                |

#### [incPopularity](#incpopularity)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:incPopularity(choice, id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Increases the popularity of the specified choice.                                                                                         |
| **Parameters**                                       |  * `choice`      - The choice. * `id`          - The choice ID to popularise.                                       |
| **Returns**                                          |  * `true` if successfully unfavourited, otherwise `false`.                                                |

#### [isDisabledHandler](#isdisabledhandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:isDisabledHandler(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns `true` if the specified handler is disabled.                                                                                         |
| **Parameters**                                       |  * `id`          - The handler ID.                                       |
| **Returns**                                          |  * `true` if the handler is disabled.                                                |

#### [isHiddenChoice](#ishiddenchoice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:isHiddenChoice(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Checks if the specified choice is hidden.                                                                                         |
| **Parameters**                                       |  * `id`          - The choice ID to check.                                       |
| **Returns**                                          |  * `true` if currently hidden.                                                |

#### [onActivate](#onactivate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:onActivate(activateFn) -> activator` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Registers the provided function to handle 'activate' actions, when the user selects                                                                                         |
| **Parameters**                                       |  * `activateFn`      - The function to call when an item is activated.                                       |
| **Returns**                                          |  * The activator.                                                |

#### [preloadChoices](#preloadchoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:preloadChoices([afterSeconds]) -> activator` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Indicates the activator should preload the choices after a number of seconds.                                                                                         |
| **Parameters**                                       |  * `afterSeconds`    - The number of seconds to wait before preloading.                                       |
| **Returns**                                          |  * The activator.                                                |

#### [refresh](#refresh)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:refresh()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Clears the existing set of choices and requests new ones from enabled action handlers.                                                                                         |

#### [refreshChooser](#refreshchooser)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:refreshChooser()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Refreshes a Chooser.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [rightClickAction](#rightclickaction)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:rightClickAction(index) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Triggered when a user right clicks on a chooser.                                                                                         |
| **Parameters**                                       |  * `index`      - The row the right click occurred in or 0 if there is currently no selectable row where the right click occurred.                                       |
| **Returns**                                          |  * None                                                |

#### [rightClickMain](#rightclickmain)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:rightClickMain(index) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Triggered when a user right clicks on a chooser.                                                                                         |
| **Parameters**                                       |  * `index`      - The row the right click occurred in or 0 if there is currently no selectable row where the right click occurred.                                       |
| **Returns**                                          |  * None                                                |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:show()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows a chooser listing the available actions. When selected by the user,                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [sortChoices](#sortchoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:sortChoices() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sorts the current set of choices in the activator. It takes into account                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `true` if the action executed successfully, otherwise `false`.                                                |

#### [unfavoriteChoice](#unfavoritechoice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:unfavoriteChoice(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Marks the choice with the specified ID as not a favorite.                                                                                         |
| **Parameters**                                       |  * `id`          - The choice ID to unfavorite.                                       |
| **Returns**                                          |  * `true` if successfully unfavorited.                                                |

#### [unhiddenChoices](#unhiddenchoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:unhiddenChoices() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a table with visible choices.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * Table of choices that can be displayed by an `hs.chooser`.                                                |

#### [unhideChoice](#unhidechoice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:unhideChoice(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Reveals the choice with the specified ID.                                                                                         |
| **Parameters**                                       |  * `id`          - The choice ID to hide.                                       |
| **Returns**                                          |  * `true` if successfully unhidden otherwise `false`.                                                |

