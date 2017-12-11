# [docs](index.md) » hs.styledtext
---

This module adds support for controlling the style of the text in Hammerspoon.

More detailed documentation is being worked on and will be provided in the Hammerspoon Wiki at https://github.com/Hammerspoon/hammerspoon/wiki.  The documentation here is a condensed version provided for use within the Hammerspoon Dash docset and the inline help provided by the `help` console command within Hammerspoon.

The following list of attributes key-value pairs are recognized by this module and can be adjusted, set, or removed for objects by the various methods provided by this module.  The list of attributes is provided here for reference; anywhere in the documentation you see a reference to the `attributes key-value pairs`, refer back to here for specifics:

* `font`               - A table containing the font name and size, specified by the keys `name` and `size`.  Default is the System Font at 27 points for `hs.drawing` text objects; otherwise the default is Helvetica at 12 points.  You may also specify this as a string, which will be taken as the font named in the string at the default size, when setting this attribute.
* `color`              - A table indicating the color of the text as described in `hs.drawing.color`.  Default is white for hs.drawing text objects; otherwise the default is black.
* `backgroundColor`    - Default nil, no background color (transparent).
* `underlineColor`     - Default nil, same as `color`.
* `strikethroughColor` - Default nil, same as `color`.
* `strokeColor`        - Default nil, same as `color`.
* `strokeWidth`        - Default 0, no stroke; positive, stroke alone; negative, stroke and fill (a typical value for outlined text would be 3.0)
* `paragraphStyle`     - A table containing the paragraph style.  This table may contain any number of the following keys:
    * `alignment`                     - A string indicating the texts alignment.  The string may contain a value of "left", "right", "center", "justified", or "natural". Default is "natural".
    * `lineBreak`                     - A string indicating how text that doesn't fit into the drawingObjects rectangle should be handled.  The string may be one of "wordWrap", "charWrap", "clip", "truncateHead", "truncateTail", or "truncateMiddle".  Default is "wordWrap".
    * `baseWritingDirection`          - A string indicating the base writing direction for the lines of text.  The string may be one of "natural", "leftToRight", or "rightToLeft".  Default is "natural".
    * `tabStops`                      - An array of defined tab stops.  Default is an array of 12 left justified tab stops 28 points apart.  Each element of the array may contain the following keys:
        * `location`                      - A floating point number indicating the number of points the tab stap is located from the line's starting margin (see baseWritingDirection).
        * `tabStopType`                   - A string indicating the type of the tab stop: "left", "right", "center", or "decimal"
    * `defaultTabInterval`            - A positive floating point number specifying the default tab stop distance in points after the last assigned stop in the tabStops field.
    * `firstLineHeadIndent`           - A positive floating point number specifying the distance, in points, from the leading margin of a frame to the beginning of the paragraph's first line.  Default 0.0.
    * `headIndent`                    - A positive floating point number specifying the distance, in points, from the leading margin of a text container to the beginning of lines other than the first.  Default 0.0.
    * `tailIndent`                    - A floating point number specifying the distance, in points, from the margin of a frame to the end of lines. If positive, this value is the distance from the leading margin (for example, the left margin in left-to-right text). If 0 or negative, it's the distance from the trailing margin.  Default 0.0.
    * `maximumLineHeight`             - A positive floating point number specifying the maximum height that any line in the frame will occupy, regardless of the font size. Glyphs exceeding this height will overlap neighboring lines. A maximum height of 0 implies no line height limit. Default 0.0.
    * `minimumLineHeight`             - A positive floating point number specifying the minimum height that any line in the frame will occupy, regardless of the font size.  Default 0.0.
    * `lineSpacing`                   - A positive floating point number specifying the space in points added between lines within the paragraph (commonly known as leading). Default 0.0.
    * `paragraphSpacing`              - A positive floating point number specifying the space added at the end of the paragraph to separate it from the following paragraph.  Default 0.0.
    * `paragraphSpacingBefore`        - A positive floating point number specifying the distance between the paragraph's top and the beginning of its text content.  Default 0.0.
    * `lineHeightMultiple`            - A positive floating point number specifying the line height multiple. The natural line height of the receiver is multiplied by this factor (if not 0) before being constrained by minimum and maximum line height.  Default 0.0.
    * `hyphenationFactor`             - The hyphenation factor, a value ranging from 0.0 to 1.0 that controls when hyphenation is attempted. By default, the value is 0.0, meaning hyphenation is off. A factor of 1.0 causes hyphenation to be attempted always.
    * `tighteningFactorForTruncation` - A floating point number.  When the line break mode specifies truncation, the system attempts to tighten inter character spacing as an alternative to truncation, provided that the ratio of the text width to the line fragment width does not exceed 1.0 + the value of tighteningFactorForTruncation. Otherwise the text is truncated at a location determined by the line break mode. The default value is 0.05.
    * `allowsTighteningForTruncation` - A boolean indicating whether the system may tighten inter-character spacing before truncating text. Only available in macOS 10.11 or newer. Default true.
    * `headerLevel`                   - An integer number from 0 to 6 inclusive which specifies whether the paragraph is to be treated as a header, and at what level, for purposes of HTML generation.  Defaults to 0.
* `superscript`        - An integer indicating if the text is to be displayed as a superscript (positive) or a subscript (negative) or normal (0).
* `ligature`           - An integer. Default 1, standard ligatures; 0, no ligatures; 2, all ligatures.
* `strikethroughStyle` - An integer representing the strike-through line style.  See `hs.styledtext.lineStyles`, `hs.styledtext.linePatterns` and `hs.styledtext.lineAppliesTo`.
* `underlineStyle`     - An integer representing the underline style.  See `hs.styledtext.lineStyles`, `hs.styledtext.linePatterns` and `hs.styledtext.lineAppliesTo`.
* `baselineOffset`     - A floating point value, as points offset from baseline. Default 0.0.
* `kerning`            - A floating point value, as points by which to modify default kerning.  Default nil to use default kerning specified in font file; 0.0, kerning off; non-zero, points by which to modify default kerning.
* `obliqueness`        - A floating point value, as skew to be applied to glyphs.  Default 0.0, no skew.
* `expansion`          - A floating point value, as log of expansion factor to be applied to glyphs.  Default 0.0, no expansion.
* `shadow`             - Default nil, indicating no drop shadow.  A table describing the drop shadow effect for the text.  The table may contain any of the following keys:
    * `offset`             - A table with `h` and `w` keys (a size structure) which specify horizontal and vertical offsets respectively for the shadow.  Positive values always extend down and to the right from the user's perspective.
    * `blurRadius`         - A floating point value specifying the shadow's blur radius.  A value of 0 indicates no blur, while larger values produce correspondingly larger blurring. The default value is 0.
    * `color`              - The default shadow color is black with an alpha of 1/3. If you set this property to nil, the shadow is not drawn.

To make the `hs.styledtext` objects easier to use, in addition to the module specific functions and methods defined, some of the Lua String library has been reproduced to perform similar functions on these objects.  See the help section for each method for more information on their use:

* `hs.styledtext:byte`
* `hs.styledtext:find`
* `hs.styledtext:gmatch`
* `hs.styledtext:len`
* `hs.styledtext:lower`
* `hs.styledtext:match`
* `hs.styledtext:rep`
* `hs.styledtext:sub`
* `hs.styledtext:upper`

In addition, the following metamethods have been included:

* concat:
    * `string`..`object` yields the string values concatenated
    * `object`..`string` yields a new `hs.styledtext` object with `string` appended
    * two `hs.styledtext` objects yields a new `hs.styledtext` object containing the concatenation of the two objects
* len:     #object yields the length of the text contained in the object
* eq:      object ==/~= object yields a boolean indicating if the text of the two objects is equal or not.  Use `hs.styledtext:isIdentical` if you need to compare attributes as well.
* lt, le:  allows &lt;, &gt;, &lt;=, and &gt;= comparisons between objects and strings in which the text of an object is compared with the text of another or a Lua string.

Note that due to differences in the way Lua determines when to use metamethods for equality comparisons versus relative-position comparisons, ==/~= cannot compare an object to a Lua string (it will always return false because the types are different).  You must use object:getString() ==/~= `string`.  (see `hs.styledtext:getString`)

## API Overview
* Constants - Useful values which cannot be changed
 * [defaultFonts](#defaultfonts)
 * [fontTraits](#fonttraits)
 * [lineAppliesTo](#lineappliesto)
 * [linePatterns](#linepatterns)
 * [lineStyles](#linestyles)
* Functions - API calls offered directly by the extension
 * [convertFont](#convertfont)
 * [fontInfo](#fontinfo)
 * [fontNames](#fontnames)
 * [fontNamesWithTraits](#fontnameswithtraits)
* Constructors - API calls which return an object, typically one that offers API methods
 * [ansi](#ansi)
 * [getStyledTextFromData](#getstyledtextfromdata)
 * [getStyledTextFromFile](#getstyledtextfromfile)
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [asTable](#astable)
 * [byte](#byte)
 * [convert](#convert)
 * [copy](#copy)
 * [find](#find)
 * [getString](#getstring)
 * [gmatch](#gmatch)
 * [isIdentical](#isidentical)
 * [len](#len)
 * [lower](#lower)
 * [match](#match)
 * [removeStyle](#removestyle)
 * [rep](#rep)
 * [setString](#setstring)
 * [setStyle](#setstyle)
 * [sub](#sub)
 * [upper](#upper)

## API Documentation

### Constants

#### [defaultFonts](#defaultfonts)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext.defaultFonts` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A table containing the system default fonts and sizes.                                                                                         |
| **Notes**                                            | <ul><li>These are useful when defining a styled text object which should be similar to or based on a specific system element type.</li></ul>                |

#### [fontTraits](#fonttraits)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext.fontTraits -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A table for containing Font Trait masks for use with `hs.styledtext.fontNamesWithTraits(...)`                                                                                         |

#### [lineAppliesTo](#lineappliesto)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext.lineAppliesTo` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A table of values indicating how the line for underlining or strike-through are applied to the text.                                                                                         |
| **Notes**                                            | <ul><li>Valid keys are as follows:</li><li>  line - the underline or strike-through is applied to an entire line of text</li><li>  word - the underline or strike-through is only applied to words and not the spaces in a line of text</li></ul>                |

#### [linePatterns](#linepatterns)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext.linePatterns` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A table of patterns which apply to the line for underlining or strike-through.                                                                                         |
| **Notes**                                            | <ul><li>Valid line pattern keys are as follows:</li><li>  solid      - a solid line</li><li>  dot        - a dotted line</li><li>  dash       - a dashed line</li><li>  dashDot    - a pattern of a dash followed by a dot</li><li>  dashDotDot - a pattern of a dash followed by two dots</li></ul>                |

#### [lineStyles](#linestyles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext.lineStyles` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A table of styles which apply to the line for underlining or strike-through.                                                                                         |
| **Notes**                                            | <ul><li>Valid line style keys are as follows:</li><li>  none   - no line style</li><li>  single - a single thin line</li><li>  thick  - a single thick line (usually double the single line's thickness)</li><li>  double - double think lines</li></ul>                |

### Functions

#### [convertFont](#convertfont)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext.convertFont(fontTable, trait) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the font which most closely matches the given font and the trait change requested.                                                                                         |
| **Parameters**                                       | <ul><li>font - a string or a table which specifies a font.  If a string is given, the default system font size is assumed.  If a table is provided, it should contain the following keys:</li><li>  name - the name of the font (defaults to the system font)</li><li>  size - the point size of the font (defaults to the default system font size)</li><li>trait - a number corresponding to a trait listed in `hs.styledtext.fontTraits` you wish to add or remove (unboldFont and unitalicFont) from the given font, or a boolean indicating whether you want a heavier version (true) or a lighter version (false).</li></ul> |
| **Returns**                                          | <ul><li>a table containing the name and size of the font which most closely matches the specified font and the trait change requested.  If no such font is available, then the original font is returned unchanged.</li></ul>          |

#### [fontInfo](#fontinfo)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext.fontInfo(font) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Get information about the font Specified in the attributes table.                                                                                         |
| **Parameters**                                       | <ul><li>font - a string or a table which specifies a font.  If a string is given, the default system font size is assumed.  If a table is provided, it should contain the following keys:</li><li>  name - the name of the font (defaults to the system font)</li><li>  size - the point size of the font (defaults to the default system font size)</li></ul> |
| **Returns**                                          | <ul><li>a table containing the following keys:</li><li>  fontName           - The font's internally recognized name.</li><li>  familyName         - The font's family name.</li><li>  displayName        - The font’s display name is typically localized for the user’s language.</li><li>  fixedPitch         - A boolean value indicating whether all glyphs in the font have the same advancement.</li><li>  ascender           - The top y-coordinate, offset from the baseline, of the font’s longest ascender.</li><li>  boundingRect       - A table containing the font’s bounding rectangle, scaled to the font’s size.  This rectangle is the union of the bounding rectangles of every glyph in the font.</li><li>  capHeight          - The cap height of the font.</li><li>  descender          - The bottom y-coordinate, offset from the baseline, of the font’s longest descender.</li><li>  italicAngle        - The number of degrees that the font is slanted counterclockwise from the vertical. (read-only)</li><li>  leading            - The leading value of the font.</li><li>  maximumAdvancement - A table containing the maximum advance of any of the font’s glyphs.</li><li>  numberOfGlyphs     - The number of glyphs in the font.</li><li>  pointSize          - The point size of the font.</li><li>  underlinePosition  - The baseline offset to use when drawing underlines with the font.</li><li>  underlineThickness - The thickness to use when drawing underlines with the font.</li><li>  xHeight            - The x-height of the font.</li></ul>          |

#### [fontNames](#fontnames)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext.fontNames() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the names of all installed fonts for the system.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a table containing the names of every font installed for the system.  The individual names are strings which can be used in the `hs.drawing:setTextFont(fontname)` method.</li></ul>          |

#### [fontNamesWithTraits](#fontnameswithtraits)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext.fontNamesWithTraits(fontTraitMask) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the names of all installed fonts for the system with the specified traits.                                                                                         |
| **Parameters**                                       | <ul><li>traits - a number, specifying the fontTraitMask, or a table containing traits listed in `hs.styledtext.fontTraits` which are logically 'OR'ed together to create the fontTraitMask used.</li></ul> |
| **Returns**                                          | <ul><li>a table containing the names of every font installed for the system which matches the fontTraitMask specified.  The individual names are strings which can be used in the `hs.drawing:setTextFont(fontname)` method.</li></ul>          |
| **Notes**                                            | <ul><li>specifying 0 or an empty table will match all fonts that are neither italic nor bold.  This would be the same list as you'd get with { hs.styledtext.fontTraits.unBold, hs.styledtext.fontTraits.unItalic } as the parameter.</li></ul>                |

### Constructors

#### [ansi](#ansi)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext.ansi(string, [attributes]) -> styledText object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Create an `hs.styledtext` object from the string provided, converting ANSI SGR color and some font sequences into the appropriate attributes.  Attributes to apply to the resulting string may also be optionally provided.                                                                                         |
| **Parameters**                                       | <ul><li>string     - The string containing the text with ANSI SGR sequences to be converted.</li><li>attributes - an optional table containing attribute key-value pairs to apply to the entire `hs.styledtext` object to be returned.</li></ul> |
| **Returns**                                          | <ul><li>an `hs.styledtext` object</li></ul>          |
| **Notes**                                            | <ul><li>Because a font is required for the SGR sequences indicating Bold and Italic, the base font is determined using the following logic:</li><li>* if no `attributes` table is provided, the font is assumed to be the default for `hs.drawing` as returned by the `hs.drawing.defaultTextStyle` function</li><li>* if an `attributes` table is provided and it defines a `font` attribute, this font is used.</li><li>* if an `attributes` table is provided, but it does not provide a `font` attribute, the NSAttributedString default of Helvetica at 12 points is used.</li><li>As the most common use of this constructor is likely to be from the output of a terminal shell command, you will most likely want to specify a fixed-pitch (monospace) font.  You can get a list of installed fixed-pitch fonts by typing `hs.styledtext.fontNamesWithTraits(hs.styledtext.fontTraits.fixedPitchFont)` into the Hammerspoon console.</li></ul>                |

#### [getStyledTextFromData](#getstyledtextfromdata)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext.getStyledTextFromData(data, [type]) -> styledText object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Converts the provided data into a styled text string.                                                                                         |
| **Parameters**                                       | <ul><li>data          - the data, as a lua string, which contains the raw data to be converted to a styledText object</li><li>type          - a string indicating the format of the contents in `data`.  Defaults to "html".  The string may be one of the following (not all formats may be fully representable as a simple string container - see also `hs.styledtext.setTextFromFile`):</li><li>  "text"      - Plain text document.</li><li>  "rtf"        - Rich text format document.</li><li>  "rtfd"       - Rich text format with attachments document.</li><li>  "simpleText" - Macintosh SimpleText document.</li><li>  "html"       - Hypertext Markup Language (HTML) document.</li><li>  "word"       - Microsoft Word document.</li><li>  "wordXML"    - Microsoft Word XML (WordML schema) document.</li><li>  "webArchive" - Web Kit WebArchive document.</li><li>  "openXML"    - ECMA Office Open XML text document format.</li><li>  "open"       - OASIS Open Document text document format.</li></ul> |
| **Returns**                                          | <ul><li>the styledText object</li></ul>          |
| **Notes**                                            | <ul><li>See also `hs.styledtext.getStyledTextFromFile`</li></ul>                |

#### [getStyledTextFromFile](#getstyledtextfromfile)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext.getStyledTextFromFile(file, [type]) -> styledText object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Converts the data in the specified file into a styled text string.                                                                                         |
| **Parameters**                                       | <ul><li>file          - the path to the file to use as the source for the data to convert into a styledText object</li><li>type          - a string indicating the format of the contents in `data`.  Defaults to "html".  The string may be one of the following (not all formats may be fully representable as a simple string container - see also `hs.styledtext.setTextFromFile`):</li><li>  "text"      - Plain text document.</li><li>  "rtf"        - Rich text format document.</li><li>  "rtfd"       - Rich text format with attachments document.</li><li>  "simpleText" - Macintosh SimpleText document.</li><li>  "html"       - Hypertext Markup Language (HTML) document.</li><li>  "word"       - Microsoft Word document.</li><li>  "wordXML"    - Microsoft Word XML (WordML schema) document.</li><li>  "webArchive" - Web Kit WebArchive document.</li><li>  "openXML"    - ECMA Office Open XML text document format.</li><li>  "open"       - OASIS Open Document text document format.</li></ul> |
| **Returns**                                          | <ul><li>the styledText object</li></ul>          |
| **Notes**                                            | <ul><li>See also `hs.styledtext.getStyledTextFromData`</li></ul>                |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext.new(string, [attributes]) -> styledText object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Create an `hs.styledtext` object from the string or table representation provided.  Attributes to apply to the resulting string may also be optionally provided.                                                                                         |
| **Parameters**                                       | <ul><li>string     - a string, table, or `hs.styledtext` object to create a new `hs.styledtext` object from.</li><li>attributes - an optional table containing attribute key-value pairs to apply to the entire `hs.styledtext` object to be returned.</li></ul> |
| **Returns**                                          | <ul><li>an `hs.styledtext` object</li></ul>          |
| **Notes**                                            | <ul><li>See `hs.styledtext:asTable` for a description of the table representation of an `hs.styledtext` object</li><li>See the module description documentation (`help.hs.styledtext`) for a description of the attributes table format which can be provided for the optional second argument.</li></ul>                |

### Methods

#### [asTable](#astable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext:asTable([starts], [ends]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the table representation of the `hs.styledtext` object or its specified substring.                                                                                         |
| **Parameters**                                       | <ul><li>starts - an optional index position within the text of the `hs.styledtext` object indicating the beginning of the substring to return the table for.  Defaults to 1, the beginning of the objects text.  If this number is negative, it is counted backwards from the end of the object's text (i.e. -1 would be the last character position).</li><li>ends   - an optional index position within the text of the `hs.styledtext` object indicating the end of the substring to return the table for.  Defaults to the length of the objects text.  If this number is negative, it is counted backwards from the end of the object's text.</li></ul> |
| **Returns**                                          | <ul><li>a table representing the `hs.styledtext` object.  The table will be an array with the following structure:</li><li>  index 1             - the text of the `hs.styledtext` object as a Lua String.</li><li>  index 2+            - a table with the following keys:</li><li>    starts            - the index position in the original styled text object where this list of attributes is first applied</li><li>    ends              - the index position in the original styled text object where the application of this list of attributes ends</li><li>    attributes        - a table of attribute key-value pairs that apply to the string between the positions of `starts` and `ends`</li><li>    unsupportedFields - this field only exists, and will be set to `true` when an attribute that was included in the attributes table that this module cannot modify.  A best effort will be made to render the attributes assigned value in the attributes table, but modifying the attribute and re-applying it with `hs.styledtext:setStyle` will be silently ignored.</li></ul>          |
| **Notes**                                            | <ul><li>`starts` and `ends` follow the conventions of `i` and `j` for Lua's `string.sub` function.</li><li>The attribute which contains an attachment (image) for a converted RTFD or other document is known to set the `unsupportedFields` flag.</li></ul>                |

#### [byte](#byte)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext:byte([starts], [ends]) -> integer, ...` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the internal numerical representation of the characters in the `hs.styledtext` object specified by the given indicies.  Mimics the Lua `string.byte` function.                                                                                         |
| **Parameters**                                       | <ul><li>starts - an optional index position within the text of the `hs.styledtext` object indicating the beginning of the substring to return numerical values for.  Defaults to 1, the beginning of the objects text.  If this number is negative, it is counted backwards from the end of the object's text (i.e. -1 would be the last character position).</li><li>ends   - an optional index position within the text of the `hs.styledtext` object indicating the end of the substring to return numerical values for.  Defaults to the value of `starts`.  If this number is negative, it is counted backwards from the end of the object's text.</li></ul> |
| **Returns**                                          | <ul><li>a list of integers representing the internal numeric representation of the characters in the `hs.styledtext` object specified by the given indicies.</li></ul>          |
| **Notes**                                            | <ul><li>`starts` and `ends` follow the conventions of `i` and `j` for Lua's `string.sub` function.</li></ul>                |

#### [convert](#convert)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext:convert([type]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Converts the styledtext object into the data format specified.                                                                                         |
| **Parameters**                                       | <ul><li>type          - a string indicating the format to convert the styletext object into.  Defaults to "html".  The string may be one of the following:</li><li>  "text"      - Plain text document.</li><li>  "rtf"        - Rich text format document.</li><li>  "rtfd"       - Rich text format with attachments document.</li><li>  "html"       - Hypertext Markup Language (HTML) document.</li><li>  "word"       - Microsoft Word document.</li><li>  "wordXML"    - Microsoft Word XML (WordML schema) document.</li><li>  "webArchive" - Web Kit WebArchive document.</li><li>  "openXML"    - ECMA Office Open XML text document format.</li><li>  "open"       - OASIS Open Document text document format.</li></ul> |
| **Returns**                                          | <ul><li>a string containing the converted data</li></ul>          |

#### [copy](#copy)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext:copy(styledText) -> styledText object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Create a copy of the `hs.styledtext` object.                                                                                         |
| **Parameters**                                       | <ul><li>styledText - an `hs.styledtext` object</li></ul> |
| **Returns**                                          | <ul><li>a copy of the styledText object</li></ul>          |

#### [find](#find)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext:find(pattern, [init, [plain]]) -> start, end, ... | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the indicies of the first occurrence of the specified pattern in the text of the `hs.styledtext` object.  Mimics the Lua `string.find` function.                                                                                         |
| **Parameters**                                       | <ul><li>pattern  - a string containing the pattern to locate.  See the Lua manual, section 6.4.1 (`help.lua._man._6_4_1`) for more details.</li><li>init     - an optional integer specifying the location within the text to start the pattern search</li><li>plain    - an optional boolean specifying whether or not to treat the pattern as plain text (i.e. an exact match).  Defaults to false.  If you wish to specify this argument, you must also specify init.</li></ul> |
| **Returns**                                          | <ul><li>if a match is found, `start` and `end` will be the indices where the pattern was first located.  If captures were specified in the pattern, they will also be returned as additional arguments after `start` and `end`.  If the pattern was not found in the text, then this method returns nil.</li></ul>          |
| **Notes**                                            | <ul><li>Any captures returned are returned as Lua Strings, not as `hs.styledtext` objects.</li></ul>                |

#### [getString](#getstring)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext:getString([starts], [ends]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the text of the `hs.styledtext` object as a Lua String                                                                                         |
| **Parameters**                                       | <ul><li>starts - an optional index position within the text of the `hs.styledtext` object indicating the beginning of the substring to return the string for.  Defaults to 1, the beginning of the objects text.  If this number is negative, it is counted backwards from the end of the object's text (i.e. -1 would be the last character position).</li><li>ends   - an optional index position within the text of the `hs.styledtext` object indicating the end of the substring to return the string for.  Defaults to the length of the objects text.  If this number is negative, it is counted backwards from the end of the object's text.</li></ul> |
| **Returns**                                          | <ul><li>a string containing the text of the `hs.styledtext` object specified</li></ul>          |
| **Notes**                                            | <ul><li>`starts` and `ends` follow the conventions of `i` and `j` for Lua's `string.sub` function.</li></ul>                |

#### [gmatch](#gmatch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext:gmatch(pattern) -> iterator-function` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns an iterator function which will return the captures (or the entire pattern) of the next match of the specified pattern in the text of the `hs.styledtext` object each time it is called.  Mimics the Lua `string.gmatch` function.                                                                                         |
| **Parameters**                                       | <ul><li>pattern  - a string containing the pattern to locate.  See the Lua manual, section 6.4.1 (`help.lua._man._6_4_1`) for more details.</li></ul> |
| **Returns**                                          | <ul><li>an iterator function which will return the captures (or the entire pattern) of the next match of the specified pattern in the text of the `hs.styledtext` object each time it is called.</li></ul>          |
| **Notes**                                            | <ul><li>Any captures (or the entire pattern) returned by the iterator are returned as Lua Strings, not as `hs.styledtext` objects.</li></ul>                |

#### [isIdentical](#isidentical)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext:isIdentical(styledText) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Determine if the `styledText` object is identical to the one specified.                                                                                         |
| **Parameters**                                       | <ul><li>styledText - an `hs.styledtext` object</li></ul> |
| **Returns**                                          | <ul><li>a boolean value indicating whether or not the styled text objects are identical, both in text content and attributes specified.</li></ul>          |
| **Notes**                                            | <ul><li>comparing two `hs.styledtext` objects with the `==` operator only compares whether or not the string values are identical.  This method also compares their attributes.</li></ul>                |

#### [len](#len)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext:len() -> integer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the length of the text of the `hs.styledtext` object.  Mimics the Lua `string.len` function.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>an integer which is the length of the text of the `hs.styledtext` object.</li></ul>          |

#### [lower](#lower)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext:lower() -> styledText object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a copy of the `hs.styledtext` object with all alpha characters converted to lower case.  Mimics the Lua `string.lower` function.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a copy of the `hs.styledtext` object with all alpha characters converted to lower case</li></ul>          |

#### [match](#match)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext:match(pattern, [init]) -> match ... | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the first occurrence of the captures in the specified pattern (or the complete pattern, if no captures are specified) in the text of the `hs.styledtext` object.  Mimics the Lua `string.match` function.                                                                                         |
| **Parameters**                                       | <ul><li>pattern  - a string containing the pattern to locate.  See the Lua manual, section 6.4.1 (`help.lua._man._6_4_1`) for more details.</li><li>init     - an optional integer specifying the location within the text to start the pattern search</li></ul> |
| **Returns**                                          | <ul><li>if a match is found, the captures in the specified pattern (or the complete pattern, if no captures are specified).  If the pattern was not found in the text, then this method returns nil.</li></ul>          |
| **Notes**                                            | <ul><li>Any captures (or the entire pattern) returned are returned as Lua Strings, not as `hs.styledtext` objects.</li></ul>                |

#### [removeStyle](#removestyle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext:removeStyle(attributes, [starts], [ends]) -> styledText object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Return a copy of the `hs.styledtext` object containing the changes to its attributes specified in the `attributes` table.                                                                                         |
| **Parameters**                                       | <ul><li>attributes - an array of attribute labels to remove (set to `nil`) from the `hs.styledtext` object.</li><li>starts     - an optional index position within the text of the `hs.styledtext` object indicating the beginning of the substring to remove attributes for.  Defaults to 1, the beginning of the object's text.  If this number is negative, it is counted backwards from the end of the object's text (i.e. -1 would be the last character position).</li><li>ends       - an optional index position within the text of the `hs.styledtext` object indicating the end of the substring to remove attributes for.  Defaults to the length of the object's text.  If this number is negative, it is counted backwards from the end of the object's text.</li></ul> |
| **Returns**                                          | <ul><li>a copy of the `hs.styledtext` object with the attributes specified removed from the given range of the original object.</li></ul>          |
| **Notes**                                            | <ul><li>`starts` and `ends` follow the conventions of `i` and `j` for Lua's `string.sub` function.</li></ul>                |

#### [rep](#rep)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext:rep(n, [separator]) -> styledText object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns an `hs.styledtext` object which contains `n` repetitions of the `hs.styledtext` object, optionally with `separator` between each repetition.  Mimics the Lua `string.rep` function.                                                                                         |
| **Parameters**                                       | <ul><li>n         - the number of times to repeat the `hs.styledtext` object.</li><li>separator - an optional string or `hs.styledtext` object to insert between repetitions.</li></ul> |
| **Returns**                                          | <ul><li>an `hs.styledtext` object which contains `n` repitions of the object, including `separator` between repetitions, if it is specified.</li></ul>          |

#### [setString](#setstring)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext:setString(string, [starts], [ends], [clear]) -> styledText object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Return a copy of the `hs.styledtext` object containing the changes to its attributes specified in the `attributes` table.                                                                                         |
| **Parameters**                                       | <ul><li>string     - a string, table, or `hs.styledtext` object to insert or replace the substring specified.</li><li>starts     - an optional index position within the text of the `hs.styledtext` object indicating the beginning of the destination for the specified string.  Defaults to 1, the beginning of the objects text.  If this number is negative, it is counted backwards from the end of the object's text (i.e. -1 would be the last character position).</li><li>ends       - an optional index position within the text of the `hs.styledtext` object indicating the end of destination for the specified string.  Defaults to the length of the objects text.  If this number is negative, it is counted backwards from the end of the object's text.  If this number is 0, then the substring is inserted at the index specified by `starts` rather than replacing it.</li><li>clear      - an optional boolean indicating whether or not the attributes of the new string should be included (true) or whether the new substring should inherit the attributes of the first character replaced (false).  Defaults to false if `string` is a Lua String or number; otherwise defaults to true.</li></ul> |
| **Returns**                                          | <ul><li>a copy of the `hs.styledtext` object with the specified substring replacement to the original object, or nil if an error occurs</li></ul>          |
| **Notes**                                            | <ul><li>`starts` and `ends` follow the conventions of `i` and `j` for Lua's `string.sub` function except that `starts` must refer to an index preceding or equal to `ends`, even after negative and out-of-bounds indices are adjusted for.</li></ul>                |

#### [setStyle](#setstyle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext:setStyle(attributes, [starts], [ends], [clear]) -> styledText object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Return a copy of the `hs.styledtext` object containing the changes to its attributes specified in the `attributes` table.                                                                                         |
| **Parameters**                                       | <ul><li>attributes - a table of attribute key-value pairs to apply to the object between the positions of `starts` and `ends`</li><li>starts     - an optional index position within the text of the `hs.styledtext` object indicating the beginning of the substring to set attributes for.  Defaults to 1, the beginning of the objects text.  If this number is negative, it is counted backwards from the end of the object's text (i.e. -1 would be the last character position).</li><li>ends       - an optional index position within the text of the `hs.styledtext` object indicating the end of the substring to set attributes for.  Defaults to the length of the objects text.  If this number is negative, it is counted backwards from the end of the object's text.</li><li>clear      - an optional boolean indicating whether or not the attributes specified should completely replace the existing attributes (true) or be added to/modify them (false).  Defaults to false.</li></ul> |
| **Returns**                                          | <ul><li>a copy of the `hs.styledtext` object with the attributes specified applied to the given range of the original object.</li></ul>          |
| **Notes**                                            | <ul><li>`starts` and `ends` follow the conventions of `i` and `j` for Lua's `string.sub` function.</li></ul>                |

#### [sub](#sub)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext:sub(starts, [ends]) -> styledText object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a substring, including the style attributes, specified by the given indicies from the `hs.styledtext` object.  Mimics the Lua `string.sub` function.                                                                                         |
| **Parameters**                                       | <ul><li>starts - the index position within the text of the `hs.styledtext` object indicating the beginning of the substring to return.  If this number is negative, it is counted backwards from the end of the object's text (i.e. -1 would be the last character position).</li><li>ends   - an optional index position within the text of the `hs.styledtext` object indicating the end of the substring to return.  Defaults to the length of the objects text.  If this number is negative, it is counted backwards from the end of the object's text.</li></ul> |
| **Returns**                                          | <ul><li>an `hs.styledtext` object containing the specified substring.</li></ul>          |
| **Notes**                                            | <ul><li>`starts` and `ends` follow the conventions of `i` and `j` for Lua's `string.sub` function.</li></ul>                |

#### [upper](#upper)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext:upper() -> styledText object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a copy of the `hs.styledtext` object with all alpha characters converted to upper case.  Mimics the Lua `string.upper` function.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a copy of the `hs.styledtext` object with all alpha characters converted to upper case</li></ul>          |

