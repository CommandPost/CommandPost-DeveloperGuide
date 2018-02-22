# [docs](index.md) » cp.apple.finalcutpro.content.Clip
---

Represents a clip of media inside FCP.

## API Overview
* Constants - Useful values which cannot be changed
 * [filmstrip](#filmstrip)
 * [row](#row)
* Functions - API calls offered directly by the extension
 * [is](#is)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [getTitle](#gettitle)
 * [getType](#gettype)
 * [UI](#ui)

## API Documentation

### Constants

#### [filmstrip](#filmstrip)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.content.Clip.type.filmstrip` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A constant for clips which are represented by a filmstrip.                                                                                         |

#### [row](#row)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.content.Clip.type.row` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A constant for clips which are represented by a table row.                                                                                         |

### Functions

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.content.Clip.is(thing) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the specified `thing` is a `Clip` instance.                                                                                         |
| **Parameters**                                       | <ul><li>`thing`  - The thing to check.</li></ul> |
| **Returns**                                          | <ul><li>`true` if the `thing` is a `Clip`, otherwise returns `false`.</li></ul>          |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.content.Clip.new(element[, options]) -> Clip` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `Clip` pointing at the specified element, with the specified options.                                                                                         |
| **Parameters**                                       | <ul><li>`element`        - The `axuielement` the clip represents.</li><li>`options`        - A table containing the options for the clip.</li></ul> |
| **Returns**                                          | <ul><li>The new `Clip`.</li></ul>          |
| **Notes**                                            | <ul><li>The options may be:</li><li> ** `columnIndex`   - A number which will be used to specify the column number to find the title in, if relevant.</li></ul>                |

### Methods

#### [getTitle](#gettitle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.content.Clip:getTitle() -> String` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the title of the clip.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The clip title.</li></ul>          |

#### [getType](#gettype)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.content.Clip:getType() -> Clip.type` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the type of clip (one of the `Clip.type` values)                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The `Clip.type` value (e.g. `Clip.type.row` or Clip.type.filmstrip`)</li></ul>          |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.content.Clip:UI() -> axuielement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `axuielement` for the clip.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The `axuielement` for the clip.</li></ul>          |

