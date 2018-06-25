# [docs](index.md) » cp.i18n.localeID
---

As per [Apple's documentation](https://developer.apple.com/library/content/documentation/MacOSX/Conceptual/BPInternational/LanguageandLocaleIDs/LanguageandLocaleIDs.html#//apple_ref/doc/uid/10000171i-CH15-SW6),
a `local ID` is a code which identifies either a language used across multiple regions,
a dialect from a specific region, a script used in multiple regions, or a combination of all three.
See the [parse](#parse) function for details.

When you parse a code with the [forCode](#forCode) function, it will result in a table that contains a
reference to the approprate `cp.i18n.language` table, and any specified `cp.i18n.region`
or `cp.i18n.script` tables. These contain the full details for each language/regin/script, as appropriate.

You can also convert the resulting table back to the code via `tostring`, or the [code](#code) method.

## API Overview
* Functions - API calls offered directly by the extension
 * [is](#is)
 * [parse](#parse)
* Constructors - API calls which return an object, typically one that offers API methods
 * [forCode](#forcode)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [code](#code)
 * [language](#language)
 * [localName](#localname)
 * [name](#name)
 * [region](#region)
 * [script](#script)
* Methods - API calls which can only be made on an object returned by a constructor
 * [matches](#matches)

## API Documentation

### Functions

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.i18n.localeID.is(other) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the `other` is a `localeID`. |
| **Parameters**                                       | <ul><li>other     - the other value to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if it is a <code>cp.i18n.locale</code>, otherwise <code>false</code>.</li></ul> |

#### [parse](#parse)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.i18n.localeID.parse(code) -> string, string, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Parses a `language ID` into three possible string components: |
| **Parameters**                                       | <ul><li>code      - The <code>locale ID</code> code. Eg. "en_AU".</li></ul> |
| **Returns**                                          | <ul><li>language  - The two-character lower-case alpha language code. * script    - the four-character mixed-case alpha script code. * region    - The two-character upper-case alpha region code.</li></ul> |

### Constructors

#### [forCode](#forcode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.i18n.localeID.forCode(code) -> cp.i18n.localeID or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates, or retrieves from the cache, a `localeID` instance for the specified `code`. |
| **Parameters**                                       | <ul><li>code      - The language ID code.</li></ul> |
| **Returns**                                          | <ul><li>The matching <code>langaugeID</code>, or <code>nil</code>.</li></ul> |

### Fields

#### [code](#code)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.i18n.localeID.code <string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The locale ID code. |

#### [language](#language)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.i18n.localeID.language <cp.i18n.language>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The matching `language` details. |

#### [localName](#localname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.i18n.localeID.localName <string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The local name in it's own language. |

#### [name](#name)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.i18n.localeID.name <string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The locale name in English. |

#### [region](#region)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.i18n.localeID.region <cp.i18n.region>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The matching `region` details, if appropriate. Will be `nil` if no region was specified in the `code`. |

#### [script](#script)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.i18n.localeID.script <cp.i18n.script>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The matching `script` details, if appropriate. Will be `nil` if no script was specified in the `code`. |

### Methods

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.i18n.localeID:matches(otherLocale) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | This compares the `otherLocale` to this locale and returns a number indicating the 'strength' |
| **Parameters**                                       | <ul><li>otherLocale       - The other locale to compare to.</li></ul> |
| **Returns**                                          | <ul><li>A number from <code>0</code> to <code>3</code> indicating the match strength.</li></ul> |

