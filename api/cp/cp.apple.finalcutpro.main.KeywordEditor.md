# [docs](index.md) » cp.apple.finalcutpro.main.KeywordEditor
---

Keyword Editor Module.

## Submodules
 * [cp.apple.finalcutpro.main.KeywordEditor.KeyboardShortcuts](cp.apple.finalcutpro.main.KeywordEditor.KeyboardShortcuts.md)

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [hide](#hide)
 * [isShowing](#isshowing)
 * [keyword](#keyword)
 * [parent](#parent)
 * [removeKeyword](#removekeyword)
 * [show](#show)
 * [toolbarCheckBoxUI](#toolbarcheckboxui)
 * [UI](#ui)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if an `hs._asm.axuielement` object matches a Keyword Editor window                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">element - the `hs._asm.axuielement` object you want to check</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`true` if a match otherwise `false`</li></ul>          |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor.new(parent) -> KeywordEditor object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new KeywordEditor object                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">`parent`     - The parent</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A KeywordEditor object</li></ul>          |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor:app() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `cp.apple.finalcutpro` app table                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The application object as a table</li></ul>          |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor:hide() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides the Keyword Editor.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">KeywordEditor object</li><li markdown="1">`true` if successful otherwise `false`</li></ul>          |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor:isShowing() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets whether or not the Keyword Editor is currently showing.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`true` if showing otherwise `false`</li></ul>          |

#### [keyword](#keyword)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor:keyword(value) -> string | table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets or gets the main Keyword Textbox value.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">value - The value you want to set the keyword textbox to. This can either be a string, with the tags separated by a comma, or a table of tags.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`value` if successful otherwise `false`</li></ul>          |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor:parent() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the KeywordEditor's parent table                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The parent object as a table</li></ul>          |

#### [removeKeyword](#removekeyword)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor:removeKeyword(keyword) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Removes a keyword from the main Keyword Textbox.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">keyword - The keyword you want to remove as a string.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">`true` if successful otherwise `false`</li></ul>          |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor:show() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows the Keyword Editor.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">KeywordEditor object</li><li markdown="1">`true` if successful otherwise `false`</li></ul>          |

#### [toolbarCheckBoxUI](#toolbarcheckboxui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor:toolbarCheckBoxUI() -> hs._asm.axuielement object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `hs._asm.axuielement` object for the Keyword Editor button in the toolbar                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A `hs._asm.axuielement` object</li></ul>          |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor:UI() -> hs._asm.axuielement object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `hs._asm.axuielement` object for the Keyword Editor window                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">A `hs._asm.axuielement` object</li></ul>          |

