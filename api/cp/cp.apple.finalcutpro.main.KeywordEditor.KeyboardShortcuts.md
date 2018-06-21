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
| **Parameters**                                       | <ul><li>parent - The parent object.</li></ul>   |
| **Returns**                                          | <ul><li>A <code>KeyboardShortcuts</code> object</li></ul>            |

### Methods

#### [apply](#apply)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor.KeyboardShortcuts:apply(item) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Applies a Keyword Shortcut.                                                                                         |
| **Parameters**                                       | <ul><li>item - The textbox you want to update. This can be a number between 1 and 9.</li></ul>   |
| **Returns**                                          | <ul><li><code>true</code> if successful otherwise <code>false</code></li></ul>            |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor.KeyboardShortcuts:hide() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides the Keyword Editor's Keyboard Shortcuts section.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li><code>true</code> if successful otherwise <code>false</code></li></ul>            |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor.KeyboardShortcuts:isShowing() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets whether or not the Keyword Editor's Keyboard Shortcuts section is currently showing.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li><code>true</code> if showing otherwise <code>false</code></li></ul>            |

#### [keyword](#keyword)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor.KeyboardShortcuts:keyword(item, value) -> string | table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets or gets a specific Keyboard Shortcut Keyword Textbox value.                                                                                         |
| **Parameters**                                       | <ul><li>item - The textbox you want to update. This can be a number between 1 and 9.</li></ul><ul><li>value - The value you want to set the keyword textbox to. This can either be a string, with the tags separated by a comma, or a table of tags.</li></ul>   |
| **Returns**                                          | <ul><li><code>value</code> if successful otherwise <code>false</code></li></ul>            |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor.KeyboardShortcuts:parent() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the KeywordShortcuts's parent table                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The parent object as a table</li></ul>            |

#### [removeAllKeywords](#removeallkeywords)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor.KeyboardShortcuts:removeAllKeywords() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Triggers the "Remove all Keywords" button.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li><code>true</code> if successful otherwise <code>false</code></li></ul>            |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor.KeyboardShortcuts:show() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows the Keyword Editor's Keyboard Shortcuts section.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li><code>true</code> if successful otherwise <code>false</code></li></ul>            |

