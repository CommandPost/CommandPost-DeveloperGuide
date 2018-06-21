# [docs](index.md) » cp.i18n.languageID
---

As per [Apple's documentation](https://developer.apple.com/library/content/documentation/MacOSX/Conceptual/BPInternational/LanguageandLocaleIDs/LanguageandLocaleIDs.html#//apple_ref/doc/uid/10000171i-CH15-SW6),
a `language ID` is a code which identifies either a language used across multiple regions,
a dialect from a specific region, or a script used in multiple regions. See the [parse](#parse) function for details.

When you parse a code with the [forCode](#forCode) function, it will result in a table that contains a
reference to the approprate `cp.i18n.language` table, and up to one of either the matching `cp.i18n.region`
or `cp.i18n.script` tables. These contain the full details for each language/regin/script, as appropriate.

You can also convert the resulting table back to the code via `tostring`, or the [code](#code) method.

## API Overview
* Functions - API calls offered directly by the extension
 * [is](#is)
 * [parse](#parse)
* Constructors - API calls which return an object, typically one that offers API methods
 * [forCode](#forcode)
 * [forLocaleID](#forlocaleid)
 * [forParts](#forparts)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [code](#code)
 * [language](#language)
 * [region](#region)
 * [script](#script)
* Methods - API calls which can only be made on an object returned by a constructor
 * [toLocaleID](#tolocaleid)

## API Documentation

### Functions

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.i18n.languageID.is(thing) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks if the `thing` is a languageID instance.                                                                                         |
| **Parameters**                                       |  * thing     - the thing to check.                                       |
| **Returns**                                          |  * `true` if the `thing` is a `languageID`, otherwise `false`.                                                |

#### [parse](#parse)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.i18n.languageID.parse(code) -> string, string, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Parses a `language ID` into three possible string components:                                                                                         |
| **Parameters**                                       |  * code      - The `language ID` code. Eg. "en-AU".                                       |
| **Returns**                                          |  * language  - The two-character lower-case alpha language code. * script    - the four-character mixed-case alpha script code. * region    - The two-character upper-case alpha region code.                                                |

### Constructors

#### [forCode](#forcode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.i18n.languageID.forCode(code) -> cp.i18n.languageID, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates, or retrieves from the cache, a `languageID` instance for the specified `code`.                                                                                         |
| **Parameters**                                       |  * code      - The language ID code.                                       |
| **Returns**                                          |  * The matching `languageID`, or `nil` if the language ID couldn't be found. * The error message, or `nil` if there was no problem.                                                |

#### [forLocaleID](#forlocaleid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.i18n.languageID.forLocaleID(code[, prioritiseScript]) -> cp.i18n.languageID, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates, or retrieves from the cache, a `languageID` instance for the specified `cp.i18n.localeID`.                                                                                         |
| **Parameters**                                       |  * locale            - The `localeID` to convert * prioritiseScript  - If set to `true` and the locale has both a region and script then the script code will be used.                                       |
| **Returns**                                          |  * The `languageID` for the `locale`, or `nil` * The error message if there was a problem.                                                |

#### [forParts](#forparts)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.i18n.languageID.forParts(languageCode[, scriptCode[, regionCode]]) -> cp.i18n.languageID` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Returns a `languageID` with the specified parts.                                                                                         |
| **Parameters**                                       |  * languageCode - Language code * scriptCode - Optional Script code * regionCode - Optional Region Code                                       |
| **Returns**                                          |  * A `cp.i18n.languageID` object.                                                |

### Fields

#### [code](#code)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.i18n.languageID.code <string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The language ID code.                                                                                         |

#### [language](#language)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.i18n.languageID.language <cp.i18n.language>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The matching `language` details.                                                                                         |

#### [region](#region)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.i18n.languageID.region <cp.i18n.region>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The matching `region` details, if appropriate. Will be `nil` if no region was specified in the `code`.                                                                                         |

#### [script](#script)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.i18n.languageID.script <cp.i18n.script>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | The matching `script` details, if appropriate. Will be `nil` if no script was specified in the `code`.                                                                                         |

### Methods

#### [toLocaleID](#tolocaleid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.i18n.languageID:toLocaleID() -> cp.i18n.localeID` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `cp.i18n.localeID` equivalent for this `languageID`.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The matching `localeID`.                                                |

