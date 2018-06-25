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
| **Parameters**                                       | <ul><br /><li><code>result</code>      - The result from the chooser.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [activeChoices](#activechoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:activeChoices() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a table with active choices. If [showHidden](#showHidden) is set to `true`  hidden                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>Table of choices that can be displayed by an <code>hs.chooser</code>.</li><br /></ul>                                           |

#### [allChoices](#allchoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:allChoices() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a table of all available choices, even if hidden. Choices from                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>Table of choices that can be displayed by an <code>hs.chooser</code>.</li><br /></ul>                                           |

#### [allowHandlers](#allowhandlers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:allowHandlers(...) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Specifies that only the handlers with the specified IDs will be active in                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>...</code>     - The list of Handler ID strings to allow.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if the handlers were found.</li><br /></ul>                                           |

#### [disableAllHandlers](#disableallhandlers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:disableAllHandlers() -> nothing` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Disables the all allowed handlers.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>Nothing</li><br /></ul>                                           |

#### [disableHandler](#disablehandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:disableHandler(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Disables the handler with the specified ID.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>id</code>      - The unique action handler ID.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if the handler exists and was disabled.</li><br /></ul>                                           |

#### [enableAllHandlers](#enableallhandlers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:enableAllHandlers() -> nothing` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Enables the all allowed handlers.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>Nothing</li><br /></ul>                                           |

#### [enableHandler](#enablehandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:enableHandler(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Enables the handler with the specified ID.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>id</code>      - The unique action handler ID.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if the handler exists and was enabled.</li><br /></ul>                                           |

#### [favoriteChoice](#favoritechoice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:favoriteChoice(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Marks the choice with the specified ID as a favorite.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>id</code>          - The choice ID to favorite.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if successfully favorited otherwise <code>false</code>.</li><br /></ul>                                           |

#### [findChoice](#findchoice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:findChoice(id) -> choice` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets a choice                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>id</code>          - The choice ID.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The choice or <code>nil</code> if not found</li><br /></ul>                                           |

#### [getActiveHandler](#getactivehandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:getActiveHandler(id) -> handler` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the active handler with the specified ID, or `nil` if not available.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>id</code>      - The Handler ID</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The action handler, or <code>nil</code>.</li><br /></ul>                                           |

#### [getPopularity](#getpopularity)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:getPopularity(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the popularity of the specified choice.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>id</code>          - The choice ID to retrieve.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The number of times the choice has been executed.</li><br /></ul>                                           |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:hide()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides a chooser listing the available actions.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [hideChoice](#hidechoice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:hideChoice(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides the choice with the specified ID.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>id</code>          - The choice ID to hide.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if successfully hidden otherwise <code>false</code>.</li><br /></ul>                                           |

#### [id](#id)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:id() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the activator's unique ID.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The activator ID.</li><br /></ul>                                           |

#### [incPopularity](#incpopularity)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:incPopularity(choice, id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Increases the popularity of the specified choice.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>choice</code>      - The choice. * <code>id</code>          - The choice ID to popularise.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if successfully unfavourited, otherwise <code>false</code>.</li><br /></ul>                                           |

#### [isDisabledHandler](#isdisabledhandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:isDisabledHandler(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns `true` if the specified handler is disabled.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>id</code>          - The handler ID.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if the handler is disabled.</li><br /></ul>                                           |

#### [isHiddenChoice](#ishiddenchoice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:isHiddenChoice(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Checks if the specified choice is hidden.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>id</code>          - The choice ID to check.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if currently hidden.</li><br /></ul>                                           |

#### [onActivate](#onactivate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:onActivate(activateFn) -> activator` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Registers the provided function to handle 'activate' actions, when the user selects                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>activateFn</code>      - The function to call when an item is activated.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The activator.</li><br /></ul>                                           |

#### [preloadChoices](#preloadchoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:preloadChoices([afterSeconds]) -> activator` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Indicates the activator should preload the choices after a number of seconds.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>afterSeconds</code>    - The number of seconds to wait before preloading.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The activator.</li><br /></ul>                                           |

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
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [rightClickAction](#rightclickaction)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:rightClickAction(index) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Triggered when a user right clicks on a chooser.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>index</code>      - The row the right click occurred in or 0 if there is currently no selectable row where the right click occurred.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [rightClickMain](#rightclickmain)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:rightClickMain(index) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Triggered when a user right clicks on a chooser.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>index</code>      - The row the right click occurred in or 0 if there is currently no selectable row where the right click occurred.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:show()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows a chooser listing the available actions. When selected by the user,                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [sortChoices](#sortchoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:sortChoices() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sorts the current set of choices in the activator. It takes into account                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if the action executed successfully, otherwise <code>false</code>.</li><br /></ul>                                           |

#### [unfavoriteChoice](#unfavoritechoice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:unfavoriteChoice(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Marks the choice with the specified ID as not a favorite.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>id</code>          - The choice ID to unfavorite.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if successfully unfavorited.</li><br /></ul>                                           |

#### [unhiddenChoices](#unhiddenchoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:unhiddenChoices() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a table with visible choices.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>Table of choices that can be displayed by an <code>hs.chooser</code>.</li><br /></ul>                                           |

#### [unhideChoice](#unhidechoice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:unhideChoice(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Reveals the choice with the specified ID.                                                                                         |
| **Parameters**                                       | <ul><br /><li><code>id</code>          - The choice ID to hide.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if successfully unhidden otherwise <code>false</code>.</li><br /></ul>                                           |

