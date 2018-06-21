# [docs](index.md) » cp.apple.finalcutpro.main.KeywordEditor.KeyboardShortcuts
---

Keyboard Shortcuts

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [apply](#apply)
 * [hide](#hide)
 * [isShowing](#isshowing)
 * [keyword](#keyword)
 * [parent](#parent)
 * [removeAllKeywords](#removeallkeywords)
 * [show](#show)

## API Documentation

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor.KeyboardShortcuts.new(parent) -> KeyboardShortcuts` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `KeyboardShortcuts` object                                                                                         |
| **Parameters**                                       |  * parent - The parent object.                                       |
| **Returns**                                          |  * A `KeyboardShortcuts` object                                                |

### Methods

#### [apply](#apply)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor.KeyboardShortcuts:apply(item) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Applies a Keyword Shortcut.                                                                                         |
| **Parameters**                                       |  * item - The textbox you want to update. This can be a number between 1 and 9.                                       |
| **Returns**                                          |  * `true` if successful otherwise `false`                                                |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor.KeyboardShortcuts:hide() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides the Keyword Editor's Keyboard Shortcuts section.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `true` if successful otherwise `false`                                                |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor.KeyboardShortcuts:isShowing() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets whether or not the Keyword Editor's Keyboard Shortcuts section is currently showing.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `true` if showing otherwise `false`                                                |

#### [keyword](#keyword)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor.KeyboardShortcuts:keyword(item, value) -> string | table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets or gets a specific Keyboard Shortcut Keyword Textbox value.                                                                                         |
| **Parameters**                                       |  * item - The textbox you want to update. This can be a number between 1 and 9. * value - The value you want to set the keyword textbox to. This can either be a string, with the tags separated by a comma, or a table of tags.                                       |
| **Returns**                                          |  * `value` if successful otherwise `false`                                                |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor.KeyboardShortcuts:parent() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the KeywordShortcuts's parent table                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The parent object as a table                                                |

#### [removeAllKeywords](#removeallkeywords)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor.KeyboardShortcuts:removeAllKeywords() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Triggers the "Remove all Keywords" button.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `true` if successful otherwise `false`                                                |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor.KeyboardShortcuts:show() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows the Keyword Editor's Keyboard Shortcuts section.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `true` if successful otherwise `false`                                                |

