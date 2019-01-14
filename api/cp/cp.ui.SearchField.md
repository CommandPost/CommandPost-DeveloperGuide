# [docs](index.md) » cp.ui.SearchField
---

A [TextField](cp.ui.TextField.md) with a subrole of `AXSearchField`.

## API Overview
* Functions - API calls offered directly by the extension
 * [matchesSearch](#matchessearch)
* Methods - API calls which can only be made on an object returned by a constructor
 * [SearchField](#searchfield)

## API Documentation

### Functions

#### [matchesSearch](#matchessearch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.SearchField.matchesSearch(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks to see if an element is a `AXTextField` with a subrole of `AXSearchField`. |
| **Parameters**                                       | <ul><li>element - An <code>axuielementObject</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if matches, otherwise <code>false</code>.</li></ul> |

### Methods

#### [SearchField](#searchfield)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.SearchField(parent, uiFinder[, convertFn]) -> cp.ui.SearchField` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Creates a new SearchField. They have a parent and a finder function. |
| **Parameters**                                       | <ul><li>parent   - The parent object.</li><li>uiFinder - The function will return the <code>axuielement</code> for the SearchField.</li><li>convertFn    - (optional) If provided, will be passed the <code>string</code> value when returning.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>SearchField</code>.</li></ul> |

