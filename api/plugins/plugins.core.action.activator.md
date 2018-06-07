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
| **Parameters**                                       | <ul><li>`result`      - The result from the chooser.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [activeChoices](#activechoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:activeChoices() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a table with active choices. If [showHidden](#showHidden) is set to `true`  hidden                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Table of choices that can be displayed by an `hs.chooser`.</li></ul>          |

#### [allChoices](#allchoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:allChoices() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a table of all available choices, even if hidden. Choices from                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Table of choices that can be displayed by an `hs.chooser`.</li></ul>          |

#### [allowHandlers](#allowhandlers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:allowHandlers(...) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Specifies that only the handlers with the specified IDs will be active in                                                                                         |
| **Parameters**                                       | <ul><li>`...`     - The list of Handler ID strings to allow.</li></ul> |
| **Returns**                                          | <ul><li>`true` if the handlers were found.</li></ul>          |

#### [disableAllHandlers](#disableallhandlers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:disableAllHandlers() -> nothing` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Disables the all allowed handlers.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Nothing</li></ul>          |

#### [disableHandler](#disablehandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:disableHandler(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Disables the handler with the specified ID.                                                                                         |
| **Parameters**                                       | <ul><li>`id`      - The unique action handler ID.</li></ul> |
| **Returns**                                          | <ul><li>`true` if the handler exists and was disabled.</li></ul>          |

#### [enableAllHandlers](#enableallhandlers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:enableAllHandlers() -> nothing` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Enables the all allowed handlers.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Nothing</li></ul>          |

#### [enableHandler](#enablehandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:enableHandler(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Enables the handler with the specified ID.                                                                                         |
| **Parameters**                                       | <ul><li>`id`      - The unique action handler ID.</li></ul> |
| **Returns**                                          | <ul><li>`true` if the handler exists and was enabled.</li></ul>          |

#### [favoriteChoice](#favoritechoice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:favoriteChoice(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Marks the choice with the specified ID as a favorite.                                                                                         |
| **Parameters**                                       | <ul><li>`id`          - The choice ID to favorite.</li></ul> |
| **Returns**                                          | <ul><li>`true` if successfully favorited otherwise `false`.</li></ul>          |

#### [findChoice](#findchoice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:findChoice(id) -> choice` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets a choice                                                                                         |
| **Parameters**                                       | <ul><li>`id`          - The choice ID.</li></ul> |
| **Returns**                                          | <ul><li>The choice or `nil` if not found</li></ul>          |

#### [getActiveHandler](#getactivehandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:getActiveHandler(id) -> handler` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the active handler with the specified ID, or `nil` if not available.                                                                                         |
| **Parameters**                                       | <ul><li>`id`      - The Handler ID</li></ul> |
| **Returns**                                          | <ul><li>The action handler, or `nil`.</li></ul>          |

#### [getPopularity](#getpopularity)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:getPopularity(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the popularity of the specified choice.                                                                                         |
| **Parameters**                                       | <ul><li>`id`          - The choice ID to retrieve.</li></ul> |
| **Returns**                                          | <ul><li>The number of times the choice has been executed.</li></ul>          |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:hide()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides a chooser listing the available actions.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [hideChoice](#hidechoice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:hideChoice(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides the choice with the specified ID.                                                                                         |
| **Parameters**                                       | <ul><li>`id`          - The choice ID to hide.</li></ul> |
| **Returns**                                          | <ul><li>`true` if successfully hidden otherwise `false`.</li></ul>          |

#### [id](#id)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:id() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the activator's unique ID.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The activator ID.</li></ul>          |

#### [incPopularity](#incpopularity)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:incPopularity(choice, id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Increases the popularity of the specified choice.                                                                                         |
| **Parameters**                                       | <ul><li>`choice`      - The choice.</li><li>`id`          - The choice ID to popularise.</li></ul> |
| **Returns**                                          | <ul><li>`true` if successfully unfavourited, otherwise `false`.</li></ul>          |

#### [isDisabledHandler](#isdisabledhandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:isDisabledHandler(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns `true` if the specified handler is disabled.                                                                                         |
| **Parameters**                                       | <ul><li>`id`          - The handler ID.</li></ul> |
| **Returns**                                          | <ul><li>`true` if the handler is disabled.</li></ul>          |

#### [isHiddenChoice](#ishiddenchoice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:isHiddenChoice(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Checks if the specified choice is hidden.                                                                                         |
| **Parameters**                                       | <ul><li>`id`          - The choice ID to check.</li></ul> |
| **Returns**                                          | <ul><li>`true` if currently hidden.</li></ul>          |

#### [onActivate](#onactivate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:onActivate(activateFn) -> activator` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Registers the provided function to handle 'activate' actions, when the user selects                                                                                         |
| **Parameters**                                       | <ul><li>`activateFn`      - The function to call when an item is activated.</li></ul> |
| **Returns**                                          | <ul><li>The activator.</li></ul>          |

#### [preloadChoices](#preloadchoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:preloadChoices([afterSeconds]) -> activator` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Indicates the activator should preload the choices after a number of seconds.                                                                                         |
| **Parameters**                                       | <ul><li>`afterSeconds`    - The number of seconds to wait before preloading.</li></ul> |
| **Returns**                                          | <ul><li>The activator.</li></ul>          |

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
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [rightClickAction](#rightclickaction)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:rightClickAction(index) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Triggered when a user right clicks on a chooser.                                                                                         |
| **Parameters**                                       | <ul><li>`index`      - The row the right click occurred in or 0 if there is currently no selectable row where the right click occurred.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [rightClickMain](#rightclickmain)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:rightClickMain(index) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Triggered when a user right clicks on a chooser.                                                                                         |
| **Parameters**                                       | <ul><li>`index`      - The row the right click occurred in or 0 if there is currently no selectable row where the right click occurred.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:show()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows a chooser listing the available actions. When selected by the user,                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [sortChoices](#sortchoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:sortChoices() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sorts the current set of choices in the activator. It takes into account                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>`true` if the action executed successfully, otherwise `false`.</li></ul>          |

#### [unfavoriteChoice](#unfavoritechoice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:unfavoriteChoice(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Marks the choice with the specified ID as not a favorite.                                                                                         |
| **Parameters**                                       | <ul><li>`id`          - The choice ID to unfavorite.</li></ul> |
| **Returns**                                          | <ul><li>`true` if successfully unfavorited.</li></ul>          |

#### [unhiddenChoices](#unhiddenchoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:unhiddenChoices() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a table with visible choices.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Table of choices that can be displayed by an `hs.chooser`.</li></ul>          |

#### [unhideChoice](#unhidechoice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:unhideChoice(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Reveals the choice with the specified ID.                                                                                         |
| **Parameters**                                       | <ul><li>`id`          - The choice ID to hide.</li></ul> |
| **Returns**                                          | <ul><li>`true` if successfully unhidden otherwise `false`.</li></ul>          |

