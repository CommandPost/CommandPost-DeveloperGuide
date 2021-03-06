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
 * [activeHandlers](#activehandlers)
 * [allowedHandlers](#allowedhandlers)
 * [configurable](#configurable)
 * [favoriteChoices](#favoritechoices)
 * [hiddenChoices](#hiddenchoices)
 * [lastQueryRemembered](#lastqueryremembered)
 * [lastQueryValue](#lastqueryvalue)
 * [popularChoices](#popularchoices)
 * [query](#query)
 * [reducedTransparency](#reducedtransparency)
 * [searchSubText](#searchsubtext)
 * [showHidden](#showhidden)
* Methods - API calls which can only be made on an object returned by a constructor
 * [activate](#activate)
 * [activeChoices](#activechoices)
 * [allChoices](#allchoices)
 * [allowHandlers](#allowhandlers)
 * [chooser](#chooser)
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
 * [isVisible](#isvisible)
 * [onActivate](#onactivate)
 * [preloadChoices](#preloadchoices)
 * [refresh](#refresh)
 * [refreshChooser](#refreshchooser)
 * [rightClickAction](#rightclickaction)
 * [rightClickMain](#rightclickmain)
 * [show](#show)
 * [sortChoices](#sortchoices)
 * [toggle](#toggle)
 * [toolbarIcons](#toolbaricons)
 * [unfavoriteChoice](#unfavoritechoice)
 * [unhideChoice](#unhidechoice)
 * [updateSelectedToolbarIcon](#updateselectedtoolbaricon)

## API Documentation

### Fields

#### [activeHandlers](#activehandlers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator.activeHandlers <cp.prop: table of handlers>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Contains the table of active handlers. A handler is active if it is both allowed and enabled. |

#### [allowedHandlers](#allowedhandlers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:allowedHandlers <cp.prop: table of handlers; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Contains all handlers that are allowed in this activator. |

#### [configurable](#configurable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator.configurable <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | If `true` (the default), the activator can be configured by right-clicking on the main chooser. |

#### [favoriteChoices](#favoritechoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator.favoriteChoices <cp.prop: table of booleans>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Contains the set of choice IDs which are favorites in this activator, mapped to a boolean value. |

#### [hiddenChoices](#hiddenchoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator.hiddenChoices <cp.prop: table of booleans>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Contains the set of choice IDs which are hidden in this activator, mapped to a boolean value. |

#### [lastQueryRemembered](#lastqueryremembered)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator.lastQueryRemembered <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | If `true`, remember the last query. |

#### [lastQueryValue](#lastqueryvalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator.lastQueryValue <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The last query value. |

#### [popularChoices](#popularchoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator.popularChoices <cp.prop: table of integers>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Keeps track of how popular particular choices are. Returns a table of choice IDs |

#### [query](#query)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator.query <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The current "query" value for the activator. |

#### [reducedTransparency](#reducedtransparency)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator.reducedTransparency <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A property which will be true if the 'reduce transparency' mode is enabled. |

#### [searchSubText](#searchsubtext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator.searchSubText <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | If `true`, allow users to search the subtext value. |

#### [showHidden](#showhidden)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator.showHidden <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | If `true`, hidden items are shown. |

### Methods

#### [activate](#activate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:activate(result) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Triggered when the chooser is closed. |
| **Parameters**                                       | <ul><li><code>result</code>      - The result from the chooser.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [activeChoices](#activechoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:activeChoices() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a table with active choices. If a `query` is set, only choices containing the provided substring are returned. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Table of choices that can be displayed by an <code>hs.chooser</code>.</li></ul> |

#### [allChoices](#allchoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:allChoices() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a table of all available choices, even if hidden. Choices from |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Table of choices that can be displayed by an <code>hs.chooser</code>.</li></ul> |

#### [allowHandlers](#allowhandlers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:allowHandlers(...) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Specifies that only the handlers with the specified IDs will be active in |
| **Parameters**                                       | <ul><li><code>...</code>     - The list of Handler ID strings to allow.</li></ul> |
| **Returns**                                          | <ul><li>Self</li></ul> |

#### [chooser](#chooser)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:chooser() -> `hs.chooser` object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets a hs.chooser |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A <code>hs.chooser</code> object</li></ul> |

#### [disableAllHandlers](#disableallhandlers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:disableAllHandlers([groupID]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Disables the all allowed handlers. |
| **Parameters**                                       | <ul><li>groupID - An optional group ID to only disable all handlers of a specific group</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [disableHandler](#disablehandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:disableHandler(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Disables the handler with the specified ID. |
| **Parameters**                                       | <ul><li><code>id</code>      - The unique action handler ID.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the handler exists and was disabled.</li></ul> |

#### [enableAllHandlers](#enableallhandlers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:enableAllHandlers([groupID]]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Enables the all allowed handlers. |
| **Parameters**                                       | <ul><li>groupID - An optional group ID to only enable all handlers of a specific group</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [enableHandler](#enablehandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:enableHandler(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Enables the handler with the specified ID. |
| **Parameters**                                       | <ul><li><code>id</code>      - The unique action handler ID.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the handler exists and was enabled.</li></ul> |

#### [favoriteChoice](#favoritechoice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:favoriteChoice(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Marks the choice with the specified ID as a favorite. |
| **Parameters**                                       | <ul><li><code>id</code>          - The choice ID to favorite.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successfully favorited otherwise <code>false</code>.</li></ul> |

#### [findChoice](#findchoice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:findChoice(id) -> choice` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets a choice |
| **Parameters**                                       | <ul><li><code>id</code>          - The choice ID.</li></ul> |
| **Returns**                                          | <ul><li>The choice or <code>nil</code> if not found</li></ul> |

#### [getActiveHandler](#getactivehandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:getActiveHandler(id) -> handler` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the active handler with the specified ID, or `nil` if not available. |
| **Parameters**                                       | <ul><li><code>id</code>      - The Handler ID</li></ul> |
| **Returns**                                          | <ul><li>The action handler, or <code>nil</code>.</li></ul> |

#### [getPopularity](#getpopularity)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:getPopularity(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the popularity of the specified choice. |
| **Parameters**                                       | <ul><li><code>id</code>          - The choice ID to retrieve.</li></ul> |
| **Returns**                                          | <ul><li>The number of times the choice has been executed.</li></ul> |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:hide() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Hides a chooser listing the available actions. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [hideChoice](#hidechoice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:hideChoice(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Hides the choice with the specified ID. |
| **Parameters**                                       | <ul><li><code>id</code>          - The choice ID to hide.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successfully hidden otherwise <code>false</code>.</li></ul> |

#### [id](#id)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:id() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the activator's unique ID. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The activator ID.</li></ul> |

#### [incPopularity](#incpopularity)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:incPopularity(choice, id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Increases the popularity of the specified choice. |
| **Parameters**                                       | <ul><li><code>choice</code>      - The choice.</li><li><code>id</code>          - The choice ID to popularise.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successfully unfavourited, otherwise <code>false</code>.</li></ul> |

#### [isDisabledHandler](#isdisabledhandler)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:isDisabledHandler(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns `true` if the specified handler is disabled. |
| **Parameters**                                       | <ul><li><code>id</code>          - The handler ID.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the handler is disabled.</li></ul> |

#### [isHiddenChoice](#ishiddenchoice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:isHiddenChoice(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Checks if the specified choice is hidden. |
| **Parameters**                                       | <ul><li><code>id</code>          - The choice ID to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if currently hidden.</li></ul> |

#### [isVisible](#isvisible)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:isVisible() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Checks if the chooser is currently displayed. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A boolean, <code>true</code> if the chooser is displayed on screen, <code>false</code> if not.</li></ul> |

#### [onActivate](#onactivate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:onActivate(activateFn) -> activator` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Registers the provided function to handle 'activate' actions, when the user selects |
| **Parameters**                                       | <ul><li><code>activateFn</code>      - The function to call when an item is activated.</li></ul> |
| **Returns**                                          | <ul><li>The activator.</li></ul> |

#### [preloadChoices](#preloadchoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:preloadChoices([afterSeconds]) -> activator` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Indicates the activator should preload the choices after a number of seconds. |
| **Parameters**                                       | <ul><li><code>afterSeconds</code>    - The number of seconds to wait before preloading.</li></ul> |
| **Returns**                                          | <ul><li>The activator.</li></ul> |

#### [refresh](#refresh)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:refresh() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Clears the existing set of choices and requests new ones from enabled action handlers. |

#### [refreshChooser](#refreshchooser)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:refreshChooser() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Refreshes a Chooser. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [rightClickAction](#rightclickaction)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:rightClickAction(index) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Triggered when a user right clicks on a chooser. |
| **Parameters**                                       | <ul><li><code>index</code>      - The row the right click occurred in or 0 if there is currently no selectable row where the right click occurred.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [rightClickMain](#rightclickmain)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:rightClickMain(index) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Triggered when a user right clicks on a chooser. |
| **Parameters**                                       | <ul><li><code>index</code>      - The row the right click occurred in or 0 if there is currently no selectable row where the right click occurred.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:show() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Shows a chooser listing the available actions. When selected by the user, |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful</li></ul> |

#### [sortChoices](#sortchoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:sortChoices() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sorts the current set of choices in the activator. It takes into account |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the action executed successfully, otherwise <code>false</code>.</li></ul> |

#### [toggle](#toggle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:toggle() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Shows or hides the chooser. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [toolbarIcons](#toolbaricons)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:toolbarIcons(table) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets which sections have an icon on the toolbar. |
| **Parameters**                                       | <ul><li>table - A table containing paths to all the toolbar icons. The key should be           the handler ID, and the value should be the path to the icon.</li></ul> |
| **Returns**                                          | <ul><li>Self</li></ul> |

#### [unfavoriteChoice](#unfavoritechoice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:unfavoriteChoice(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Marks the choice with the specified ID as not a favorite. |
| **Parameters**                                       | <ul><li><code>id</code>          - The choice ID to unfavorite.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successfully unfavorited.</li></ul> |

#### [unhideChoice](#unhidechoice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:unhideChoice(id) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Reveals the choice with the specified ID. |
| **Parameters**                                       | <ul><li><code>id</code>          - The choice ID to hide.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successfully unhidden otherwise <code>false</code>.</li></ul> |

#### [updateSelectedToolbarIcon](#updateselectedtoolbaricon)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.action.activator:updateSelectedToolbarIcon() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Updates the selected toolbar icon. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

