# [docs](index.md) » hs.utf8
---

Functions providing basic support for UTF-8 encodings

Prior to upgrading Hammerspoon's Lua interpreter to 5.3, UTF8 support was provided by including the then beta version of Lua 5.3's utf8 library as a Hammerspoon module.  This is no longer necessary, but to maintain compatibility, the Lua utf8 library can still be accessed through `hs.utf8`.  The documentation for the utf8 library can be found at http://www.lua.org/manual/5.3/ or from the Hammerspoon console via the help command: `help.lua.utf8`. This affects the following functions and variables:

  * hs.utf8.char          - help available via `help.lua.utf8.char`
  * hs.utf8.charPattern   - help available via `help.lua.utf8.charpattern`
  * hs.utf8.codepoint     - help available via `help.lua.utf8.codepoint`
  * hs.utf8.codes         - help available via `help.lua.utf8.codes`
  * hs.utf8.len           - help available via `help.lua.utf8.len`
  * hs.utf8.offset        - help available via `help.lua.utf8.offset`

Additional functions that are specific to Hammerspoon which provide expanded support for UTF8 are documented here.


## API Overview
* Variables - Configurable values
 * [registeredKeys](#registeredkeys)
* Functions - API calls offered directly by the extension
 * [asciiOnly](#asciionly)
 * [codepointToUTF8](#codepointtoutf8)
 * [fixUTF8](#fixutf8)
 * [hexDump](#hexdump)
 * [registerCodepoint](#registercodepoint)
 * [registeredLabels](#registeredlabels)

## API Documentation

### Variables

#### [registeredKeys](#registeredkeys)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.utf8.registeredKeys[]` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | A collection of UTF-8 characters already converted from codepoint and available as convient key-value pairs.  UTF-8 printable versions of common Apple and OS X special keys are predefined and others can be added with `hs.utf8.registerCodepoint(label, codepoint)` for your own use. |
| **Notes**                                            | <ul><li>This table has a __tostring() metamethod which allows listing it's contents in the Hammerspoon console by typing <code>hs.utf8.registeredKeys</code>.</li><li>For parity with <code>hs.utf8.registeredLabels</code>, this can also invoked as a function, i.e. <code>hs.utf8.registeredKeys["cmd"]</code> is equivalent to <code>hs.utf8.registeredKeys("cmd")</code></li></ul> |

### Functions

#### [asciiOnly](#asciionly)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.utf8.asciiOnly(string[, all]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the provided string with all non-printable ascii characters escaped, except Return, Linefeed, and Tab. |
| **Parameters**                                       | <ul><li>string - The input string which is to have all non-printable ascii characters escaped as \x## (a single byte hexadecimal number).</li><li>all    - an optional boolean parameter (default false) indicating whether or not Return, Linefeed, and Tab should also be considered "non-printable"</li></ul> |
| **Returns**                                          | <ul><li>The cleaned up string, with non-printable characters escaped.</li></ul> |
| **Notes**                                            | <ul><li>Because Unicode characters outside of the basic ascii alphabet are multi-byte characters, any UTF8 or other Unicode encoded character will be broken up into their individual bytes and likely escaped by this function.</li><li>This function is useful for displaying binary data in a human readable way that might otherwise be inexpressible in the Hammerspoon console or other destination.  For example:</li><li><code>utf8.charpattern</code>, which contains the regular expression for matching valid UTF8 encoded sequences, results in <code>(null)</code> in the Hammerspoon console, but <code>hs.utf8.asciiOnly(utf8.charpattern)</code> will display <code>[\x00-\x7F\xC2-\xF4][\x80-\xBF]*</code>.</li></ul> |

#### [codepointToUTF8](#codepointtoutf8)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.utf8.codepointToUTF8(...) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Wrapper to `utf8.char(...)` which ensures that all codepoints return valid UTF8 characters. |
| **Parameters**                                       | <ul><li>codepoints - A series of numeric Unicode code points to be converted to a UTF-8 byte sequences.  If a codepoint is a string (and does not start with U+, it is used as a key for lookup in <code>hs.utf8.registeredKeys[]</code></li></ul> |
| **Returns**                                          | <ul><li>A string containing the UTF-8 byte sequences corresponding to provided codepoints as a combined string.</li></ul> |
| **Notes**                                            | <ul><li>Valid codepoint values are from 0x0000 - 0x10FFFF (0 - 1114111)</li><li>If the codepoint provided is a string that starts with U+, then the 'U+' is converted to a '0x' so that lua can properly treat the value as numeric.</li><li>Invalid codepoints are returned as the Unicode Replacement Character (U+FFFD)</li><li>This includes out of range codepoints as well as the Unicode Surrogate codepoints (U+D800 - U+DFFF)</li></ul> |

#### [fixUTF8](#fixutf8)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.utf8.fixUTF8(inString[, replacementChar]) -> outString, posTable` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Replace invalid UTF8 character sequences in `inString` with `replacementChar` so it can be safely displayed in the console or other destination which requires valid UTF8 encoding. |
| **Parameters**                                       | <ul><li>inString - String of characters which may contain invalid UTF8 byte sequences</li><li>replacementChar - optional parameter to replace invalid byte sequences in <code>inString</code>.  If this parameter is not provided, the default UTF8 replacement character, U+FFFD, is used.</li></ul> |
| **Returns**                                          | <ul><li>outString - The contents of <code>inString</code> with all invalid UTF8 byte sequences replaced by the <code>replacementChar</code>.</li><li>posTable - a table of indexes in <code>outString</code> corresponding indicating where <code>replacementChar</code> has been used.</li></ul> |
| **Notes**                                            | <ul><li>This function is a slight modification to code found at http://notebook.kulchenko.com/programming/fixing-malformed-utf8-in-lua.</li><li>If <code>replacementChar</code> is a multi-byte character (like U+FFFD) or multi character string, then the string length of <code>outString</code> will be longer than the string length of <code>inString</code>.  The character positions in <code>posTable</code> will reflect these new positions in <code>outString</code>.</li><li>To calculate the character position of the invalid characters in <code>inString</code>, use something like the following:</li></ul> |

#### [hexDump](#hexdump)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.utf8.hexDump(inputString [, count]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a hex dump of the provided string.  This is primarily useful for examining the exact makeup of binary data contained in a Lua String as individual bytes for debugging purposes. |
| **Parameters**                                       | <ul><li>inputString - the data to be rendered as individual hexadecimal bytes for examination.</li><li>count - an optional parameter specifying the number of bytes to display per line (default 16)</li></ul> |
| **Returns**                                          | <ul><li>a string containing the hex dump of the input string.</li></ul> |
| **Notes**                                            | <ul><li>Like hs.utf8.asciiOnly, this function will break up Unicode characters into their individual bytes.</li><li>As an example:     <code>hs.utf8.hexDump(utf8.charpattern)</code> will return     <code>00 : 5B 00 2D 7F C2 2D F4 5D 5B 80 2D BF 5D 2A        : [.-..-.][.-.]*</code></li></ul> |

#### [registerCodepoint](#registercodepoint)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.utf8.registerCodepoint(label, codepoint) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Registers a Unicode codepoint under the given label as a UTF-8 string of bytes which can be referenced by the label later in your code as `hs.utf8.registeredKeys[label]` for convenience and readability. |
| **Parameters**                                       | <ul><li>label - a string label to use as a human-readable reference when getting the UTF-8 byte sequence for use in other strings and output functions.</li><li>codepoint - a Unicode codepoint in numeric or <code>U+xxxx</code> format to register with the given label.</li></ul> |
| **Returns**                                          | <ul><li>Returns the UTF-8 byte sequence for the Unicode codepoint registered.</li></ul> |
| **Notes**                                            | <ul><li>If a codepoint label was previously registered, this will overwrite the previous value with a new one.  Because many of the special keys you may want to register have different variants, this allows you to easily modify the existing predefined defaults to suite your preferences.</li><li>The return value is merely syntactic sugar and you do not need to save it locally; it can be safely ignored -- future access to the pre-converted codepoint should be retrieved as <code>hs.utf8.registeredKeys[label]</code> in your code.  It looks good when invoked from the console, though ☺.</li></ul> |

#### [registeredLabels](#registeredlabels)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.utf8.registeredLabels(utf8char) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the label name for a UTF8 character, as it is registered in `hs.utf8.registeredKeys[]`. |
| **Parameters**                                       | <ul><li>utf8char -- the character to lookup in <code>hs.utf8.registeredKeys[]</code></li></ul> |
| **Returns**                                          | <ul><li>The string label for the UTF8 character or a string in the format of "U+XXXX", if it is not defined in <code>hs.utf8.registeredKeys[]</code>, or nil, if utf8char is not a valid UTF8 character.</li></ul> |
| **Notes**                                            | <ul><li>For parity with <code>hs.utf8.registeredKeys</code>, this can also be invoked as if it were an array: i.e. <code>hs.utf8.registeredLabels(char)</code> is equivalent to <code>hs.utf8.registeredLabels[char]</code></li></ul> |

