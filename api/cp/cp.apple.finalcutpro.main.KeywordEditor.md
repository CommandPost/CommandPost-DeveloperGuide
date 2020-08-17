# [docs](index.md) » cp.apple.finalcutpro.main.KeywordEditor
---

Keyword Editor Module.

## API Overview
* Constants - Useful values which cannot be changed
 * [NUMBER_OF_SHORTCUTS](#number_of_shortcuts)
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [KeywordEditor](#keywordeditor)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [isShowing](#isshowing)
 * [keyboardShortcuts](#keyboardshortcuts)
 * [keywords](#keywords)
 * [resetButton](#resetbutton)
 * [shortcutButtons](#shortcutbuttons)
 * [shortcutFields](#shortcutfields)
* Methods - API calls which can only be made on an object returned by a constructor
 * [doHide](#dohide)
 * [doShow](#doshow)
 * [hide](#hide)
 * [parent](#parent)
 * [show](#show)

## API Documentation

### Constants

#### [NUMBER_OF_SHORTCUTS](#number_of_shortcuts)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor.NUMBER_OF_SHORTCUTS -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The number of Keyword Keyboard shortcuts available. |

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks to see if an `hs._asm.axuielement` object matches a Keyword Editor window |
| **Parameters**                                       | <ul><li>element - the <code>hs._asm.axuielement</code> object you want to check</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if a match otherwise <code>false</code></li></ul> |

### Constructors

#### [KeywordEditor](#keywordeditor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor(parent) -> KeywordEditor object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new KeywordEditor object |
| **Parameters**                                       | <ul><li><code>parent</code>     - The parent</li></ul> |
| **Returns**                                          | <ul><li>A KeywordEditor object</li></ul> |

### Fields

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor.isShowing <cp.prop: boolean; live?>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Indicates whether or not the Keyword Editor is currently showing. |

#### [keyboardShortcuts](#keyboardshortcuts)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor.keyboardShortcuts <cp.ui.DisclosureWindow>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `DisclosureTriangle` that shows/hides the keyboard shortcuts configuration. |

#### [keywords](#keywords)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor.keywords <cp.ui.TextField>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | A `TextField` that contains the current keywords. The value is a `table` of `string` values for each individual keyword. |

#### [resetButton](#resetbutton)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor.resetButton <cp.ui.Button>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `Button` that resets the current keywords to blank. |

#### [shortcutButtons](#shortcutbuttons)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor.shortcutButtons <table of cp.ui.Button>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The list of keyboard shortcut `Button`s. The button for `Cmd+1` is accessed via `shortcutButtons[1]`, and so on. |

#### [shortcutFields](#shortcutfields)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor.shortcutFields <table of KeywordField>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The list of keyboard shortcut `KeywordField`s. The field for `Cmd+1` is accessed via `shortcutFields[1]`, and so on. |

### Methods

#### [doHide](#dohide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor:doHide() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A `Statement` that hides the Keyword Editor. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code></li></ul> |

#### [doShow](#doshow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor:doShow() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A `Statement` that shows the Keyword Editor. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code></li></ul> |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor:hide() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Hides the Keyword Editor. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>KeywordEditor object</li><li><code>true</code> if successful otherwise <code>false</code></li></ul> |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor:parent() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the KeywordEditor's parent table |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The parent object as a table</li></ul> |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordEditor:show() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Shows the Keyword Editor. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>KeywordEditor object</li><li><code>true</code> if successful otherwise <code>false</code></li></ul> |

