# [docs](index.md) » cp.apple.finalcutpro.main.KeywordField
---

Keyword Text Field Module.

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [KeywordField](#keywordfield)
* Methods - API calls which can only be made on an object returned by a constructor
 * [addKeyword](#addkeyword)
 * [removeKeyword](#removekeyword)

## API Documentation

### Constructors

#### [KeywordField](#keywordfield)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordField(parent, uiFinder) -> KeywordField` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Constructs a new KeywordField. |
| **Parameters**                                       | <ul><li>parent - the parent object.</li><li>uiFinder - The <code>function</code> or <code>cp.prop</code> that provides the axuielement.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>KeywordField</code>.</li></ul> |

### Methods

#### [addKeyword](#addkeyword)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordField:addKeyword(keyword) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Attempts to add the specified keyword. |
| **Parameters**                                       | <ul><li>keyword - The keyword string to add.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the keyword was not present and added, otherwise false.</li></ul> |

#### [removeKeyword](#removekeyword)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.KeywordField:removeKeyword(keyword) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Attempts to remove the specified keyword. |
| **Parameters**                                       | <ul><li>keyword - The keyword string to remove.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the keyword was present and removed, otherwise false.</li></ul> |

