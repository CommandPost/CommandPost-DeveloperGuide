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
 * [validFont](#validfont)
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
| **Notes**                                            | <ul><br /><li>These are useful when defining a styled text object which should be similar to or based on a specific system element type.</li><br /></ul>                                             |

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
| **Notes**                                            | <ul><br /><li>Valid keys are as follows:   * line - the underline or strike-through is applied to an entire line of text   * word - the underline or strike-through is only applied to words and not the spaces in a line of text</li><br /></ul>                                             |

#### [linePatterns](#linepatterns)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext.linePatterns` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A table of patterns which apply to the line for underlining or strike-through.                                                                                         |
| **Notes**                                            | <ul><br /><li>Valid line pattern keys are as follows:   * solid      - a solid line   * dot        - a dotted line   * dash       - a dashed line   * dashDot    - a pattern of a dash followed by a dot   * dashDotDot - a pattern of a dash followed by two dots</li><br /></ul>                                             |

#### [lineStyles](#linestyles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext.lineStyles` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | A table of styles which apply to the line for underlining or strike-through.                                                                                         |
| **Notes**                                            | <ul><br /><li>Valid line style keys are as follows:   * none   - no line style   * single - a single thin line   * thick  - a single thick line (usually double the single line's thickness)   * double - double think lines</li><br /></ul>                                             |

### Functions

#### [convertFont](#convertfont)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext.convertFont(fontTable, trait) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the font which most closely matches the given font and the trait change requested.                                                                                         |
| **Parameters**                                       | <ul><br /><li>font - a string or a table which specifies a font.  If a string is given, the default system font size is assumed.  If a table is provided, it should contain the following keys:   * name - the name of the font (defaults to the system font)   * size - the point size of the font (defaults to the default system font size) * trait - a number corresponding to a trait listed in <code>hs.styledtext.fontTraits</code> you wish to add or remove (unboldFont and unitalicFont) from the given font, or a boolean indicating whether you want a heavier version (true) or a lighter version (false).</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a table containing the name and size of the font which most closely matches the specified font and the trait change requested.  If no such font is available, then the original font is returned unchanged.</li><br /></ul>                                           |

#### [fontInfo](#fontinfo)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext.fontInfo(font) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Get information about the font Specified in the attributes table.                                                                                         |
| **Parameters**                                       | <ul><br /><li>font - a string or a table which specifies a font.  If a string is given, the default system font size is assumed.  If a table is provided, it should contain the following keys:   * name - the name of the font (defaults to the system font)   * size - the point size of the font (defaults to the default system font size)</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a table containing the following keys:   * fontName           - The font's internally recognized name.   * familyName         - The font's family name.   * displayName        - The font’s display name is typically localized for the user’s language.   * fixedPitch         - A boolean value indicating whether all glyphs in the font have the same advancement.   * ascender           - The top y-coordinate, offset from the baseline, of the font’s longest ascender.   * boundingRect       - A table containing the font’s bounding rectangle, scaled to the font’s size.  This rectangle is the union of the bounding rectangles of every glyph in the font.   * capHeight          - The cap height of the font.   * descender          - The bottom y-coordinate, offset from the baseline, of the font’s longest descender.   * italicAngle        - The number of degrees that the font is slanted counterclockwise from the vertical. (read-only)   * leading            - The leading value of the font.   * maximumAdvancement - A table containing the maximum advance of any of the font’s glyphs.   * numberOfGlyphs     - The number of glyphs in the font.   * pointSize          - The point size of the font.   * underlinePosition  - The baseline offset to use when drawing underlines with the font.   * underlineThickness - The thickness to use when drawing underlines with the font.   * xHeight            - The x-height of the font.</li><br /></ul>                                           |

#### [fontNames](#fontnames)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext.fontNames() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the names of all installed fonts for the system.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a table containing the names of every font installed for the system.  The individual names are strings which can be used in the <code>hs.drawing:setTextFont(fontname)</code> method.</li><br /></ul>                                           |

#### [fontNamesWithTraits](#fontnameswithtraits)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext.fontNamesWithTraits(fontTraitMask) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the names of all installed fonts for the system with the specified traits.                                                                                         |
| **Parameters**                                       | <ul><br /><li>traits - a number, specifying the fontTraitMask, or a table containing traits listed in <code>hs.styledtext.fontTraits</code> which are logically 'OR'ed together to create the fontTraitMask used.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a table containing the names of every font installed for the system which matches the fontTraitMask specified.  The individual names are strings which can be used in the <code>hs.drawing:setTextFont(fontname)</code> method.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>specifying 0 or an empty table will match all fonts that are neither italic nor bold.  This would be the same list as you'd get with { hs.styledtext.fontTraits.unBold, hs.styledtext.fontTraits.unItalic } as the parameter.</li><br /></ul>                                             |

#### [validFont](#validfont)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext.validFont(font) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if a font is valid.                                                                                         |
| **Parameters**                                       | <ul><br /><li>font - a string containing the name of the font you want to check.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if valid, otherwise <code>false</code>.</li><br /></ul>                                           |

### Constructors

#### [ansi](#ansi)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext.ansi(string, [attributes]) -> styledText object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Create an `hs.styledtext` object from the string provided, converting ANSI SGR color and some font sequences into the appropriate attributes.  Attributes to apply to the resulting string may also be optionally provided.                                                                                         |
| **Parameters**                                       | <ul><br /><li>string     - The string containing the text with ANSI SGR sequences to be converted. * attributes - an optional table containing attribute key-value pairs to apply to the entire <code>hs.styledtext</code> object to be returned.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>an <code>hs.styledtext</code> object</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>Because a font is required for the SGR sequences indicating Bold and Italic, the base font is determined using the following logic:<em>  * if no <code>attributes</code> table is provided, the font is assumed to be the default for <code>hs.drawing</code> as returned by the <code>hs.drawing.defaultTextStyle</code> function</em>  * if an <code>attributes</code> table is provided and it defines a <code>font</code> attribute, this font is used.*  * if an <code>attributes</code> table is provided, but it does not provide a <code>font</code> attribute, the NSAttributedString default of Helvetica at 12 points is used. * As the most common use of this constructor is likely to be from the output of a terminal shell command, you will most likely want to specify a fixed-pitch (monospace) font.  You can get a list of installed fixed-pitch fonts by typing <code>hs.styledtext.fontNamesWithTraits(hs.styledtext.fontTraits.fixedPitchFont)</code> into the Hammerspoon console.</li><br /></ul>                                             |

#### [getStyledTextFromData](#getstyledtextfromdata)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext.getStyledTextFromData(data, [type]) -> styledText object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Converts the provided data into a styled text string.                                                                                         |
| **Parameters**                                       | <ul><br /><li>data          - the data, as a lua string, which contains the raw data to be converted to a styledText object * type          - a string indicating the format of the contents in <code>data</code>.  Defaults to "html".  The string may be one of the following (not all formats may be fully representable as a simple string container - see also <code>hs.styledtext.setTextFromFile</code>):   * "text"      - Plain text document.   * "rtf"        - Rich text format document.   * "rtfd"       - Rich text format with attachments document.   * "simpleText" - Macintosh SimpleText document.   * "html"       - Hypertext Markup Language (HTML) document.   * "word"       - Microsoft Word document.   * "wordXML"    - Microsoft Word XML (WordML schema) document.   * "webArchive" - Web Kit WebArchive document.   * "openXML"    - ECMA Office Open XML text document format.   * "open"       - OASIS Open Document text document format.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>the styledText object</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>See also <code>hs.styledtext.getStyledTextFromFile</code></li><br /></ul>                                             |

#### [getStyledTextFromFile](#getstyledtextfromfile)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext.getStyledTextFromFile(file, [type]) -> styledText object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Converts the data in the specified file into a styled text string.                                                                                         |
| **Parameters**                                       | <ul><br /><li>file          - the path to the file to use as the source for the data to convert into a styledText object * type          - a string indicating the format of the contents in <code>data</code>.  Defaults to "html".  The string may be one of the following (not all formats may be fully representable as a simple string container - see also <code>hs.styledtext.setTextFromFile</code>):   * "text"      - Plain text document.   * "rtf"        - Rich text format document.   * "rtfd"       - Rich text format with attachments document.   * "simpleText" - Macintosh SimpleText document.   * "html"       - Hypertext Markup Language (HTML) document.   * "word"       - Microsoft Word document.   * "wordXML"    - Microsoft Word XML (WordML schema) document.   * "webArchive" - Web Kit WebArchive document.   * "openXML"    - ECMA Office Open XML text document format.   * "open"       - OASIS Open Document text document format.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>the styledText object</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>See also <code>hs.styledtext.getStyledTextFromData</code></li><br /></ul>                                             |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext.new(string, [attributes]) -> styledText object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Create an `hs.styledtext` object from the string or table representation provided.  Attributes to apply to the resulting string may also be optionally provided.                                                                                         |
| **Parameters**                                       | <ul><br /><li>string     - a string, table, or <code>hs.styledtext</code> object to create a new <code>hs.styledtext</code> object from. * attributes - an optional table containing attribute key-value pairs to apply to the entire <code>hs.styledtext</code> object to be returned.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>an <code>hs.styledtext</code> object</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>See <code>hs.styledtext:asTable</code> for a description of the table representation of an <code>hs.styledtext</code> object * See the module description documentation (<code>help.hs.styledtext</code>) for a description of the attributes table format which can be provided for the optional second argument.</li><br /></ul>                                             |

### Methods

#### [asTable](#astable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext:asTable([starts], [ends]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the table representation of the `hs.styledtext` object or its specified substring.                                                                                         |
| **Parameters**                                       | <ul><br /><li>starts - an optional index position within the text of the <code>hs.styledtext</code> object indicating the beginning of the substring to return the table for.  Defaults to 1, the beginning of the objects text.  If this number is negative, it is counted backwards from the end of the object's text (i.e. -1 would be the last character position). * ends   - an optional index position within the text of the <code>hs.styledtext</code> object indicating the end of the substring to return the table for.  Defaults to the length of the objects text.  If this number is negative, it is counted backwards from the end of the object's text.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a table representing the <code>hs.styledtext</code> object.  The table will be an array with the following structure:   * index 1             - the text of the <code>hs.styledtext</code> object as a Lua String.   * index 2+            - a table with the following keys:     * starts            - the index position in the original styled text object where this list of attributes is first applied     * ends              - the index position in the original styled text object where the application of this list of attributes ends     * attributes        - a table of attribute key-value pairs that apply to the string between the positions of <code>starts</code> and <code>ends</code>     * unsupportedFields - this field only exists, and will be set to <code>true</code> when an attribute that was included in the attributes table that this module cannot modify.  A best effort will be made to render the attributes assigned value in the attributes table, but modifying the attribute and re-applying it with <code>hs.styledtext:setStyle</code> will be silently ignored.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li><code>starts</code> and <code>ends</code> follow the conventions of <code>i</code> and <code>j</code> for Lua's <code>string.sub</code> function. * The attribute which contains an attachment (image) for a converted RTFD or other document is known to set the <code>unsupportedFields</code> flag.</li><br /></ul>                                             |

#### [byte](#byte)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext:byte([starts], [ends]) -> integer, ...` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the internal numerical representation of the characters in the `hs.styledtext` object specified by the given indicies.  Mimics the Lua `string.byte` function.                                                                                         |
| **Parameters**                                       | <ul><br /><li>starts - an optional index position within the text of the <code>hs.styledtext</code> object indicating the beginning of the substring to return numerical values for.  Defaults to 1, the beginning of the objects text.  If this number is negative, it is counted backwards from the end of the object's text (i.e. -1 would be the last character position). * ends   - an optional index position within the text of the <code>hs.styledtext</code> object indicating the end of the substring to return numerical values for.  Defaults to the value of <code>starts</code>.  If this number is negative, it is counted backwards from the end of the object's text.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a list of integers representing the internal numeric representation of the characters in the <code>hs.styledtext</code> object specified by the given indicies.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li><code>starts</code> and <code>ends</code> follow the conventions of <code>i</code> and <code>j</code> for Lua's <code>string.sub</code> function.</li><br /></ul>                                             |

#### [convert](#convert)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext:convert([type]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Converts the styledtext object into the data format specified.                                                                                         |
| **Parameters**                                       | <ul><br /><li>type          - a string indicating the format to convert the styletext object into.  Defaults to "html".  The string may be one of the following:   * "text"      - Plain text document.   * "rtf"        - Rich text format document.   * "rtfd"       - Rich text format with attachments document.   * "html"       - Hypertext Markup Language (HTML) document.   * "word"       - Microsoft Word document.   * "wordXML"    - Microsoft Word XML (WordML schema) document.   * "webArchive" - Web Kit WebArchive document.   * "openXML"    - ECMA Office Open XML text document format.   * "open"       - OASIS Open Document text document format.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a string containing the converted data</li><br /></ul>                                           |

#### [copy](#copy)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext:copy(styledText) -> styledText object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Create a copy of the `hs.styledtext` object.                                                                                         |
| **Parameters**                                       | <ul><br /><li>styledText - an <code>hs.styledtext</code> object</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a copy of the styledText object</li><br /></ul>                                           |

#### [find](#find)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext:find(pattern, [init, [plain]]) -> start, end, ... | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the indicies of the first occurrence of the specified pattern in the text of the `hs.styledtext` object.  Mimics the Lua `string.find` function.                                                                                         |
| **Parameters**                                       | <ul><br /><li>pattern  - a string containing the pattern to locate.  See the Lua manual, section 6.4.1 (<code>help.lua._man._6_4_1</code>) for more details. * init     - an optional integer specifying the location within the text to start the pattern search * plain    - an optional boolean specifying whether or not to treat the pattern as plain text (i.e. an exact match).  Defaults to false.  If you wish to specify this argument, you must also specify init.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>if a match is found, <code>start</code> and <code>end</code> will be the indices where the pattern was first located.  If captures were specified in the pattern, they will also be returned as additional arguments after <code>start</code> and <code>end</code>.  If the pattern was not found in the text, then this method returns nil.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>Any captures returned are returned as Lua Strings, not as <code>hs.styledtext</code> objects.</li><br /></ul>                                             |

#### [getString](#getstring)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext:getString([starts], [ends]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the text of the `hs.styledtext` object as a Lua String                                                                                         |
| **Parameters**                                       | <ul><br /><li>starts - an optional index position within the text of the <code>hs.styledtext</code> object indicating the beginning of the substring to return the string for.  Defaults to 1, the beginning of the objects text.  If this number is negative, it is counted backwards from the end of the object's text (i.e. -1 would be the last character position). * ends   - an optional index position within the text of the <code>hs.styledtext</code> object indicating the end of the substring to return the string for.  Defaults to the length of the objects text.  If this number is negative, it is counted backwards from the end of the object's text.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a string containing the text of the <code>hs.styledtext</code> object specified</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li><code>starts</code> and <code>ends</code> follow the conventions of <code>i</code> and <code>j</code> for Lua's <code>string.sub</code> function.</li><br /></ul>                                             |

#### [gmatch](#gmatch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext:gmatch(pattern) -> iterator-function` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns an iterator function which will return the captures (or the entire pattern) of the next match of the specified pattern in the text of the `hs.styledtext` object each time it is called.  Mimics the Lua `string.gmatch` function.                                                                                         |
| **Parameters**                                       | <ul><br /><li>pattern  - a string containing the pattern to locate.  See the Lua manual, section 6.4.1 (<code>help.lua._man._6_4_1</code>) for more details.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>an iterator function which will return the captures (or the entire pattern) of the next match of the specified pattern in the text of the <code>hs.styledtext</code> object each time it is called.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>Any captures (or the entire pattern) returned by the iterator are returned as Lua Strings, not as <code>hs.styledtext</code> objects.</li><br /></ul>                                             |

#### [isIdentical](#isidentical)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext:isIdentical(styledText) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Determine if the `styledText` object is identical to the one specified.                                                                                         |
| **Parameters**                                       | <ul><br /><li>styledText - an <code>hs.styledtext</code> object</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a boolean value indicating whether or not the styled text objects are identical, both in text content and attributes specified.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>comparing two <code>hs.styledtext</code> objects with the <code>==</code> operator only compares whether or not the string values are identical.  This method also compares their attributes.</li><br /></ul>                                             |

#### [len](#len)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext:len() -> integer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the length of the text of the `hs.styledtext` object.  Mimics the Lua `string.len` function.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>an integer which is the length of the text of the <code>hs.styledtext</code> object.</li><br /></ul>                                           |

#### [lower](#lower)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext:lower() -> styledText object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a copy of the `hs.styledtext` object with all alpha characters converted to lower case.  Mimics the Lua `string.lower` function.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a copy of the <code>hs.styledtext</code> object with all alpha characters converted to lower case</li><br /></ul>                                           |

#### [match](#match)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext:match(pattern, [init]) -> match ... | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the first occurrence of the captures in the specified pattern (or the complete pattern, if no captures are specified) in the text of the `hs.styledtext` object.  Mimics the Lua `string.match` function.                                                                                         |
| **Parameters**                                       | <ul><br /><li>pattern  - a string containing the pattern to locate.  See the Lua manual, section 6.4.1 (<code>help.lua._man._6_4_1</code>) for more details. * init     - an optional integer specifying the location within the text to start the pattern search</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>if a match is found, the captures in the specified pattern (or the complete pattern, if no captures are specified).  If the pattern was not found in the text, then this method returns nil.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>Any captures (or the entire pattern) returned are returned as Lua Strings, not as <code>hs.styledtext</code> objects.</li><br /></ul>                                             |

#### [removeStyle](#removestyle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext:removeStyle(attributes, [starts], [ends]) -> styledText object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Return a copy of the `hs.styledtext` object containing the changes to its attributes specified in the `attributes` table.                                                                                         |
| **Parameters**                                       | <ul><br /><li>attributes - an array of attribute labels to remove (set to <code>nil</code>) from the <code>hs.styledtext</code> object. * starts     - an optional index position within the text of the <code>hs.styledtext</code> object indicating the beginning of the substring to remove attributes for.  Defaults to 1, the beginning of the object's text.  If this number is negative, it is counted backwards from the end of the object's text (i.e. -1 would be the last character position). * ends       - an optional index position within the text of the <code>hs.styledtext</code> object indicating the end of the substring to remove attributes for.  Defaults to the length of the object's text.  If this number is negative, it is counted backwards from the end of the object's text.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a copy of the <code>hs.styledtext</code> object with the attributes specified removed from the given range of the original object.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li><code>starts</code> and <code>ends</code> follow the conventions of <code>i</code> and <code>j</code> for Lua's <code>string.sub</code> function.</li><br /></ul>                                             |

#### [rep](#rep)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext:rep(n, [separator]) -> styledText object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns an `hs.styledtext` object which contains `n` repetitions of the `hs.styledtext` object, optionally with `separator` between each repetition.  Mimics the Lua `string.rep` function.                                                                                         |
| **Parameters**                                       | <ul><br /><li>n         - the number of times to repeat the <code>hs.styledtext</code> object. * separator - an optional string or <code>hs.styledtext</code> object to insert between repetitions.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>an <code>hs.styledtext</code> object which contains <code>n</code> repitions of the object, including <code>separator</code> between repetitions, if it is specified.</li><br /></ul>                                           |

#### [setString](#setstring)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext:setString(string, [starts], [ends], [clear]) -> styledText object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Return a copy of the `hs.styledtext` object containing the changes to its attributes specified in the `attributes` table.                                                                                         |
| **Parameters**                                       | <ul><br /><li>string     - a string, table, or <code>hs.styledtext</code> object to insert or replace the substring specified. * starts     - an optional index position within the text of the <code>hs.styledtext</code> object indicating the beginning of the destination for the specified string.  Defaults to 1, the beginning of the objects text.  If this number is negative, it is counted backwards from the end of the object's text (i.e. -1 would be the last character position). * ends       - an optional index position within the text of the <code>hs.styledtext</code> object indicating the end of destination for the specified string.  Defaults to the length of the objects text.  If this number is negative, it is counted backwards from the end of the object's text.  If this number is 0, then the substring is inserted at the index specified by <code>starts</code> rather than replacing it. * clear      - an optional boolean indicating whether or not the attributes of the new string should be included (true) or whether the new substring should inherit the attributes of the first character replaced (false).  Defaults to false if <code>string</code> is a Lua String or number; otherwise defaults to true.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a copy of the <code>hs.styledtext</code> object with the specified substring replacement to the original object, or nil if an error occurs</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li><code>starts</code> and <code>ends</code> follow the conventions of <code>i</code> and <code>j</code> for Lua's <code>string.sub</code> function except that <code>starts</code> must refer to an index preceding or equal to <code>ends</code>, even after negative and out-of-bounds indices are adjusted for.</li><br /></ul>                                             |

#### [setStyle](#setstyle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext:setStyle(attributes, [starts], [ends], [clear]) -> styledText object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Return a copy of the `hs.styledtext` object containing the changes to its attributes specified in the `attributes` table.                                                                                         |
| **Parameters**                                       | <ul><br /><li>attributes - a table of attribute key-value pairs to apply to the object between the positions of <code>starts</code> and <code>ends</code> * starts     - an optional index position within the text of the <code>hs.styledtext</code> object indicating the beginning of the substring to set attributes for.  Defaults to 1, the beginning of the objects text.  If this number is negative, it is counted backwards from the end of the object's text (i.e. -1 would be the last character position). * ends       - an optional index position within the text of the <code>hs.styledtext</code> object indicating the end of the substring to set attributes for.  Defaults to the length of the objects text.  If this number is negative, it is counted backwards from the end of the object's text. * clear      - an optional boolean indicating whether or not the attributes specified should completely replace the existing attributes (true) or be added to/modify them (false).  Defaults to false.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a copy of the <code>hs.styledtext</code> object with the attributes specified applied to the given range of the original object.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li><code>starts</code> and <code>ends</code> follow the conventions of <code>i</code> and <code>j</code> for Lua's <code>string.sub</code> function.</li><br /></ul>                                             |

#### [sub](#sub)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext:sub(starts, [ends]) -> styledText object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a substring, including the style attributes, specified by the given indicies from the `hs.styledtext` object.  Mimics the Lua `string.sub` function.                                                                                         |
| **Parameters**                                       | <ul><br /><li>starts - the index position within the text of the <code>hs.styledtext</code> object indicating the beginning of the substring to return.  If this number is negative, it is counted backwards from the end of the object's text (i.e. -1 would be the last character position). * ends   - an optional index position within the text of the <code>hs.styledtext</code> object indicating the end of the substring to return.  Defaults to the length of the objects text.  If this number is negative, it is counted backwards from the end of the object's text.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>an <code>hs.styledtext</code> object containing the specified substring.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li><code>starts</code> and <code>ends</code> follow the conventions of <code>i</code> and <code>j</code> for Lua's <code>string.sub</code> function.</li><br /></ul>                                             |

#### [upper](#upper)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.styledtext:upper() -> styledText object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a copy of the `hs.styledtext` object with all alpha characters converted to upper case.  Mimics the Lua `string.upper` function.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a copy of the <code>hs.styledtext</code> object with all alpha characters converted to upper case</li><br /></ul>                                           |

