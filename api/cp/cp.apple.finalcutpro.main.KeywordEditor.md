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
| **Parameters**                                       |  * element - the `hs._asm.axuielement` object you want to check                                       |
| **Returns**                                          |  * `true` if a match otherwise `false`                                                |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor.new(parent) -> KeywordEditor object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new KeywordEditor object                                                                                         |
| **Parameters**                                       |  * `parent`     - The parent                                       |
| **Returns**                                          |  * A KeywordEditor object                                                |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor:app() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `cp.apple.finalcutpro` app table                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The application object as a table                                                |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor:hide() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides the Keyword Editor.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * KeywordEditor object * `true` if successful otherwise `false`                                                |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor:isShowing() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets whether or not the Keyword Editor is currently showing.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `true` if showing otherwise `false`                                                |

#### [keyword](#keyword)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor:keyword(value) -> string | table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets or gets the main Keyword Textbox value.                                                                                         |
| **Parameters**                                       |  * value - The value you want to set the keyword textbox to. This can either be a string, with the tags separated by a comma, or a table of tags.                                       |
| **Returns**                                          |  * `value` if successful otherwise `false`                                                |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor:parent() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the KeywordEditor's parent table                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The parent object as a table                                                |

#### [removeKeyword](#removekeyword)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor:removeKeyword(keyword) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Removes a keyword from the main Keyword Textbox.                                                                                         |
| **Parameters**                                       |  * keyword - The keyword you want to remove as a string.                                       |
| **Returns**                                          |  * `true` if successful otherwise `false`                                                |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor:show() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Shows the Keyword Editor.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * KeywordEditor object * `true` if successful otherwise `false`                                                |

#### [toolbarCheckBoxUI](#toolbarcheckboxui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor:toolbarCheckBoxUI() -> hs._asm.axuielement object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `hs._asm.axuielement` object for the Keyword Editor button in the toolbar                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A `hs._asm.axuielement` object                                                |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor:UI() -> hs._asm.axuielement object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `hs._asm.axuielement` object for the Keyword Editor window                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A `hs._asm.axuielement` object                                                |

