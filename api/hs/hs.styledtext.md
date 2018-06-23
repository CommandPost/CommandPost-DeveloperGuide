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

<style type="text/css">
	a { text-decoration: none; }
	a:hover { text-decoration: underline; }
	th { background-color: #DDDDDD; vertical-align: top; padding: 3px; }
	td { width: 100%; background-color: #EEEEEE; vertical-align: top; padding: 3px; }
	table { width: 100% ; border: 1px solid #0; text-align: left; }
	section > table table td { width: 0; }
</style>
<link rel="stylesheet" href="../../css/docs.css" type="text/css" media="screen" />
<h3>API Overview</h3>
<ul>
<li>Constants - Useful values which cannot be changed</li>
  <ul>
	<li><a href="#defaultFonts">defaultFonts</a></li>
	<li><a href="#fontTraits">fontTraits</a></li>
	<li><a href="#lineAppliesTo">lineAppliesTo</a></li>
	<li><a href="#linePatterns">linePatterns</a></li>
	<li><a href="#lineStyles">lineStyles</a></li>
  </ul>
<li>Functions - API calls offered directly by the extension</li>
  <ul>
	<li><a href="#convertFont">convertFont</a></li>
	<li><a href="#fontInfo">fontInfo</a></li>
	<li><a href="#fontNames">fontNames</a></li>
	<li><a href="#fontNamesWithTraits">fontNamesWithTraits</a></li>
	<li><a href="#validFont">validFont</a></li>
  </ul>
<li>Constructors - API calls which return an object, typically one that offers API methods</li>
  <ul>
	<li><a href="#ansi">ansi</a></li>
	<li><a href="#getStyledTextFromData">getStyledTextFromData</a></li>
	<li><a href="#getStyledTextFromFile">getStyledTextFromFile</a></li>
	<li><a href="#new">new</a></li>
  </ul>
<li>Methods - API calls which can only be made on an object returned by a constructor</li>
  <ul>
	<li><a href="#asTable">asTable</a></li>
	<li><a href="#byte">byte</a></li>
	<li><a href="#convert">convert</a></li>
	<li><a href="#copy">copy</a></li>
	<li><a href="#find">find</a></li>
	<li><a href="#getString">getString</a></li>
	<li><a href="#gmatch">gmatch</a></li>
	<li><a href="#isIdentical">isIdentical</a></li>
	<li><a href="#len">len</a></li>
	<li><a href="#lower">lower</a></li>
	<li><a href="#match">match</a></li>
	<li><a href="#removeStyle">removeStyle</a></li>
	<li><a href="#rep">rep</a></li>
	<li><a href="#setString">setString</a></li>
	<li><a href="#setStyle">setStyle</a></li>
	<li><a href="#sub">sub</a></li>
	<li><a href="#upper">upper</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Constants</h4>
  <section id="defaultFonts">
	<h5><a href="#defaultFonts">defaultFonts</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.styledtext.defaultFonts</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>A table containing the system default fonts and sizes.</p>
<p>Defined fonts included are:</p>
<ul>
<li>boldSystem     - the system font used for standard interface items that are rendered in boldface type</li>
<li>controlContent - the font used for the content of controls</li>
<li>label          - the font used for standard interface labels</li>
<li>menu           - the font used for menu items</li>
<li>menuBar        - the font used for menu bar items</li>
<li>message        - the font used for standard interface items, such as button labels, menu items, etc.</li>
<li>palette        - the font used for palette window title bars</li>
<li>system         - the system font used for standard interface items, such as button labels, menu items, etc.</li>
<li>titleBar       - the font used for window title bars</li>
<li>toolTips       - the font used for tool tips labels</li>
<li>user           - the font used by default for documents and other text under the user’s control</li>
<li>userFixedPitch - the font used by default for documents and other text under the user’s control when that font should be fixed-pitch</li>
</ul>
<p>Notes:</p>
<ul>
<li><p>These are useful when defining a styled text object which should be similar to or based on a specific system element type.</p>
</li>
<li><p>Because the user can change font defaults while Hammerspoon is running, this table is actually generated dynamically on request.  This should not affect of your use of this constant as a table; however, you can generate a static table if desired by invoking <code>hs.styledtext._defaultFonts()</code> directly instead.</p>
</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="fontTraits">
	<h5><a href="#fontTraits">fontTraits</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.styledtext.fontTraits -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>A table for containing Font Trait masks for use with <code>hs.styledtext.fontNamesWithTraits(...)</code></p>
<ul>
<li>boldFont                    - fonts with the 'Bold' attribute set</li>
<li>compressedFont              - fonts with the 'Compressed' attribute set</li>
<li>condensedFont               - fonts with the 'Condensed' attribute set</li>
<li>expandedFont                - fonts with the 'Expanded' attribute set</li>
<li>fixedPitchFont              - fonts with the 'FixedPitch' attribute set</li>
<li>italicFont                  - fonts with the 'Italic' attribute set</li>
<li>narrowFont                  - fonts with the 'Narrow' attribute set</li>
<li>posterFont                  - fonts with the 'Poster' attribute set</li>
<li>smallCapsFont               - fonts with the 'SmallCaps' attribute set</li>
<li>nonStandardCharacterSetFont - fonts with the 'NonStandardCharacterSet' attribute set</li>
<li>unboldFont                  - fonts that do not have the 'Bold' attribute set</li>
<li>unitalicFont                - fonts that do not have the 'Italic' attribute set</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="lineAppliesTo">
	<h5><a href="#lineAppliesTo">lineAppliesTo</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.styledtext.lineAppliesTo</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>A table of values indicating how the line for underlining or strike-through are applied to the text.</p>
<p>Notes:</p>
<ul>
<li><p>Valid keys are as follows:</p>
<ul>
<li>line - the underline or strike-through is applied to an entire line of text</li>
<li>word - the underline or strike-through is only applied to words and not the spaces in a line of text</li>
</ul>
</li>
<li><p>When specifying a line type for underlining or strike-through, you can combine one entry from each of the following tables:</p>
<ul>
<li>hs.styledtext.lineStyles</li>
<li>hs.styledtext.linePatterns</li>
<li>hs.styledtext.lineAppliesTo</li>
</ul>
</li>
<li><p>The entries chosen should be combined with the <code>or</code> operator to provide a single value. for example:</p>
<ul>
<li>hs.styledtext.lineStyles.single | hs.styledtext.linePatterns.dash | hs.styledtext.lineAppliesToWord</li>
</ul>
</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="linePatterns">
	<h5><a href="#linePatterns">linePatterns</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.styledtext.linePatterns</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>A table of patterns which apply to the line for underlining or strike-through.</p>
<p>Notes:</p>
<ul>
<li><p>Valid line pattern keys are as follows:</p>
<ul>
<li>solid      - a solid line</li>
<li>dot        - a dotted line</li>
<li>dash       - a dashed line</li>
<li>dashDot    - a pattern of a dash followed by a dot</li>
<li>dashDotDot - a pattern of a dash followed by two dots</li>
</ul>
</li>
<li><p>When specifying a line type for underlining or strike-through, you can combine one entry from each of the following tables:</p>
<ul>
<li>hs.styledtext.lineStyles</li>
<li>hs.styledtext.linePatterns</li>
<li>hs.styledtext.lineAppliesTo</li>
</ul>
</li>
<li><p>The entries chosen should be combined with the <code>or</code> operator to provide a single value. for example:</p>
<ul>
<li>hs.styledtext.lineStyles.single | hs.styledtext.linePatterns.dash | hs.styledtext.lineAppliesToWord</li>
</ul>
</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="lineStyles">
	<h5><a href="#lineStyles">lineStyles</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.styledtext.lineStyles</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>A table of styles which apply to the line for underlining or strike-through.</p>
<p>Notes:</p>
<ul>
<li><p>Valid line style keys are as follows:</p>
<ul>
<li>none   - no line style</li>
<li>single - a single thin line</li>
<li>thick  - a single thick line (usually double the single line's thickness)</li>
<li>double - double think lines</li>
</ul>
</li>
<li><p>When specifying a line type for underlining or strike-through, you can combine one entry from each of the following tables:</p>
<ul>
<li>hs.styledtext.lineStyles</li>
<li>hs.styledtext.linePatterns</li>
<li>hs.styledtext.lineAppliesTo</li>
</ul>
</li>
<li><p>The entries chosen should be combined with the <code>or</code> operator to provide a single value. for example:</p>
<ul>
<li>hs.styledtext.lineStyles.single | hs.styledtext.linePatterns.dash | hs.styledtext.lineAppliesToWord</li>
</ul>
</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Functions</h4>
  <section id="convertFont">
	<h5><a href="#convertFont">convertFont</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.styledtext.convertFont(fontTable, trait) -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the font which most closely matches the given font and the trait change requested.</p>
<p>Parameters:</p>
<ul>
<li>font - a string or a table which specifies a font.  If a string is given, the default system font size is assumed.  If a table is provided, it should contain the following keys:<ul>
<li>name - the name of the font (defaults to the system font)</li>
<li>size - the point size of the font (defaults to the default system font size)</li>
</ul>
</li>
<li>trait - a number corresponding to a trait listed in <code>hs.styledtext.fontTraits</code> you wish to add or remove (unboldFont and unitalicFont) from the given font, or a boolean indicating whether you want a heavier version (true) or a lighter version (false).</li>
</ul>
<p>Returns:</p>
<ul>
<li>a table containing the name and size of the font which most closely matches the specified font and the trait change requested.  If no such font is available, then the original font is returned unchanged.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="fontInfo">
	<h5><a href="#fontInfo">fontInfo</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.styledtext.fontInfo(font) -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Get information about the font Specified in the attributes table.</p>
<p>Parameters:</p>
<ul>
<li>font - a string or a table which specifies a font.  If a string is given, the default system font size is assumed.  If a table is provided, it should contain the following keys:<ul>
<li>name - the name of the font (defaults to the system font)</li>
<li>size - the point size of the font (defaults to the default system font size)</li>
</ul>
</li>
</ul>
<p>Returns:</p>
<ul>
<li>a table containing the following keys:<ul>
<li>fontName           - The font's internally recognized name.</li>
<li>familyName         - The font's family name.</li>
<li>displayName        - The font’s display name is typically localized for the user’s language.</li>
<li>fixedPitch         - A boolean value indicating whether all glyphs in the font have the same advancement.</li>
<li>ascender           - The top y-coordinate, offset from the baseline, of the font’s longest ascender.</li>
<li>boundingRect       - A table containing the font’s bounding rectangle, scaled to the font’s size.  This rectangle is the union of the bounding rectangles of every glyph in the font.</li>
<li>capHeight          - The cap height of the font.</li>
<li>descender          - The bottom y-coordinate, offset from the baseline, of the font’s longest descender.</li>
<li>italicAngle        - The number of degrees that the font is slanted counterclockwise from the vertical. (read-only)</li>
<li>leading            - The leading value of the font.</li>
<li>maximumAdvancement - A table containing the maximum advance of any of the font’s glyphs.</li>
<li>numberOfGlyphs     - The number of glyphs in the font.</li>
<li>pointSize          - The point size of the font.</li>
<li>underlinePosition  - The baseline offset to use when drawing underlines with the font.</li>
<li>underlineThickness - The thickness to use when drawing underlines with the font.</li>
<li>xHeight            - The x-height of the font.</li>
</ul>
</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="fontNames">
	<h5><a href="#fontNames">fontNames</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.styledtext.fontNames() -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the names of all installed fonts for the system.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>a table containing the names of every font installed for the system.  The individual names are strings which can be used in the <code>hs.drawing:setTextFont(fontname)</code> method.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="fontNamesWithTraits">
	<h5><a href="#fontNamesWithTraits">fontNamesWithTraits</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.styledtext.fontNamesWithTraits(fontTraitMask) -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the names of all installed fonts for the system with the specified traits.</p>
<p>Parameters:</p>
<ul>
<li>traits - a number, specifying the fontTraitMask, or a table containing traits listed in <code>hs.styledtext.fontTraits</code> which are logically 'OR'ed together to create the fontTraitMask used.</li>
</ul>
<p>Returns:</p>
<ul>
<li>a table containing the names of every font installed for the system which matches the fontTraitMask specified.  The individual names are strings which can be used in the <code>hs.drawing:setTextFont(fontname)</code> method.</li>
</ul>
<p>Notes:</p>
<ul>
<li>specifying 0 or an empty table will match all fonts that are neither italic nor bold.  This would be the same list as you'd get with { hs.styledtext.fontTraits.unBold, hs.styledtext.fontTraits.unItalic } as the parameter.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="validFont">
	<h5><a href="#validFont">validFont</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.styledtext.validFont(font) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Checks to see if a font is valid.</p>
<p>Parameters:</p>
<ul>
<li>font - a string containing the name of the font you want to check.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if valid, otherwise <code>false</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Constructors</h4>
  <section id="ansi">
	<h5><a href="#ansi">ansi</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.styledtext.ansi(string, [attributes]) -&gt; styledText object</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constructor</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Create an <code>hs.styledtext</code> object from the string provided, converting ANSI SGR color and some font sequences into the appropriate attributes.  Attributes to apply to the resulting string may also be optionally provided.</p>
<p>Parameters:</p>
<ul>
<li>string     - The string containing the text with ANSI SGR sequences to be converted.</li>
<li>attributes - an optional table containing attribute key-value pairs to apply to the entire <code>hs.styledtext</code> object to be returned.</li>
</ul>
<p>Returns:</p>
<ul>
<li>an <code>hs.styledtext</code> object</li>
</ul>
<p>Notes:</p>
<ul>
<li>Because a font is required for the SGR sequences indicating Bold and Italic, the base font is determined using the following logic:<ul>
<li><ul>
<li>if no <code>attributes</code> table is provided, the font is assumed to be the default for <code>hs.drawing</code> as returned by the <code>hs.drawing.defaultTextStyle</code> function</li>
</ul>
</li>
<li><ul>
<li>if an <code>attributes</code> table is provided and it defines a <code>font</code> attribute, this font is used.</li>
</ul>
</li>
<li><ul>
<li>if an <code>attributes</code> table is provided, but it does not provide a <code>font</code> attribute, the NSAttributedString default of Helvetica at 12 points is used.</li>
</ul>
</li>
</ul>
</li>
<li><p>As the most common use of this constructor is likely to be from the output of a terminal shell command, you will most likely want to specify a fixed-pitch (monospace) font.  You can get a list of installed fixed-pitch fonts by typing <code>hs.styledtext.fontNamesWithTraits(hs.styledtext.fontTraits.fixedPitchFont)</code> into the Hammerspoon console.</p>
</li>
<li><p>See the module description documentation (<code>help.hs.styledtext</code>) for a description of the attributes table format which can be provided for the optional second argument.</p>
</li>
<li><p>This function was modeled after the ANSIEscapeHelper.m file at <a href="https://github.com/balthamos/geektool-3">https://github.com/balthamos/geektool-3</a> in the /NerdTool/classes directory.</p>
</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getStyledTextFromData">
	<h5><a href="#getStyledTextFromData">getStyledTextFromData</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.styledtext.getStyledTextFromData(data, [type]) -&gt; styledText object</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constructor</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Converts the provided data into a styled text string.</p>
<p>Parameters:</p>
<ul>
<li>data          - the data, as a lua string, which contains the raw data to be converted to a styledText object</li>
<li>type          - a string indicating the format of the contents in <code>data</code>.  Defaults to "html".  The string may be one of the following (not all formats may be fully representable as a simple string container - see also <code>hs.styledtext.setTextFromFile</code>):<ul>
<li>"text"      - Plain text document.</li>
<li>"rtf"        - Rich text format document.</li>
<li>"rtfd"       - Rich text format with attachments document.</li>
<li>"simpleText" - Macintosh SimpleText document.</li>
<li>"html"       - Hypertext Markup Language (HTML) document.</li>
<li>"word"       - Microsoft Word document.</li>
<li>"wordXML"    - Microsoft Word XML (WordML schema) document.</li>
<li>"webArchive" - Web Kit WebArchive document.</li>
<li>"openXML"    - ECMA Office Open XML text document format.</li>
<li>"open"       - OASIS Open Document text document format.</li>
</ul>
</li>
</ul>
<p>Returns:</p>
<ul>
<li>the styledText object</li>
</ul>
<p>Notes:</p>
<ul>
<li>See also <code>hs.styledtext.getStyledTextFromFile</code></li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getStyledTextFromFile">
	<h5><a href="#getStyledTextFromFile">getStyledTextFromFile</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.styledtext.getStyledTextFromFile(file, [type]) -&gt; styledText object</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constructor</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Converts the data in the specified file into a styled text string.</p>
<p>Parameters:</p>
<ul>
<li>file          - the path to the file to use as the source for the data to convert into a styledText object</li>
<li>type          - a string indicating the format of the contents in <code>data</code>.  Defaults to "html".  The string may be one of the following (not all formats may be fully representable as a simple string container - see also <code>hs.styledtext.setTextFromFile</code>):<ul>
<li>"text"      - Plain text document.</li>
<li>"rtf"        - Rich text format document.</li>
<li>"rtfd"       - Rich text format with attachments document.</li>
<li>"simpleText" - Macintosh SimpleText document.</li>
<li>"html"       - Hypertext Markup Language (HTML) document.</li>
<li>"word"       - Microsoft Word document.</li>
<li>"wordXML"    - Microsoft Word XML (WordML schema) document.</li>
<li>"webArchive" - Web Kit WebArchive document.</li>
<li>"openXML"    - ECMA Office Open XML text document format.</li>
<li>"open"       - OASIS Open Document text document format.</li>
</ul>
</li>
</ul>
<p>Returns:</p>
<ul>
<li>the styledText object</li>
</ul>
<p>Notes:</p>
<ul>
<li>See also <code>hs.styledtext.getStyledTextFromData</code></li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="new">
	<h5><a href="#new">new</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.styledtext.new(string, [attributes]) -&gt; styledText object</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constructor</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Create an <code>hs.styledtext</code> object from the string or table representation provided.  Attributes to apply to the resulting string may also be optionally provided.</p>
<p>Parameters:</p>
<ul>
<li>string     - a string, table, or <code>hs.styledtext</code> object to create a new <code>hs.styledtext</code> object from.</li>
<li>attributes - an optional table containing attribute key-value pairs to apply to the entire <code>hs.styledtext</code> object to be returned.</li>
</ul>
<p>Returns:</p>
<ul>
<li>an <code>hs.styledtext</code> object</li>
</ul>
<p>Notes:</p>
<ul>
<li>See <code>hs.styledtext:asTable</code> for a description of the table representation of an <code>hs.styledtext</code> object</li>
<li><p>See the module description documentation (<code>help.hs.styledtext</code>) for a description of the attributes table format which can be provided for the optional second argument.</p>
</li>
<li><p>Passing an <code>hs.styledtext</code> object as the first parameter without specifying an <code>attributes</code> table is the equivalent of invoking <code>hs.styledtext:copy</code>.</p>
</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Methods</h4>
  <section id="asTable">
	<h5><a href="#asTable">asTable</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.styledtext:asTable([starts], [ends]) -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the table representation of the <code>hs.styledtext</code> object or its specified substring.</p>
<p>Parameters:</p>
<ul>
<li>starts - an optional index position within the text of the <code>hs.styledtext</code> object indicating the beginning of the substring to return the table for.  Defaults to 1, the beginning of the objects text.  If this number is negative, it is counted backwards from the end of the object's text (i.e. -1 would be the last character position).</li>
<li>ends   - an optional index position within the text of the <code>hs.styledtext</code> object indicating the end of the substring to return the table for.  Defaults to the length of the objects text.  If this number is negative, it is counted backwards from the end of the object's text.</li>
</ul>
<p>Returns:</p>
<ul>
<li>a table representing the <code>hs.styledtext</code> object.  The table will be an array with the following structure:<ul>
<li>index 1             - the text of the <code>hs.styledtext</code> object as a Lua String.</li>
<li>index 2+            - a table with the following keys:<ul>
<li>starts            - the index position in the original styled text object where this list of attributes is first applied</li>
<li>ends              - the index position in the original styled text object where the application of this list of attributes ends</li>
<li>attributes        - a table of attribute key-value pairs that apply to the string between the positions of <code>starts</code> and <code>ends</code></li>
<li>unsupportedFields - this field only exists, and will be set to <code>true</code> when an attribute that was included in the attributes table that this module cannot modify.  A best effort will be made to render the attributes assigned value in the attributes table, but modifying the attribute and re-applying it with <code>hs.styledtext:setStyle</code> will be silently ignored.</li>
</ul>
</li>
</ul>
</li>
</ul>
<p>Notes:</p>
<ul>
<li><code>starts</code> and <code>ends</code> follow the conventions of <code>i</code> and <code>j</code> for Lua's <code>string.sub</code> function.</li>
<li><p>The attribute which contains an attachment (image) for a converted RTFD or other document is known to set the <code>unsupportedFields</code> flag.</p>
</li>
<li><p>The indexes in the table returned are relative to their position in the original <code>hs.styledtext</code> object.  If you want the table version of a substring which does not start at index position 1 that can be safely fed as a "proper" table version of an <code>hs.styledtext</code> object into another function or constructor, the proper way to generate it is `destination = object:sub(i,j):asTable().</p>
</li>
<li><p>See the module description documentation (<code>help.hs.styledtext</code>) for a description of the attributes table format</p>
</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="byte">
	<h5><a href="#byte">byte</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.styledtext:byte([starts], [ends]) -&gt; integer, ...</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the internal numerical representation of the characters in the <code>hs.styledtext</code> object specified by the given indicies.  Mimics the Lua <code>string.byte</code> function.</p>
<p>Parameters:</p>
<ul>
<li>starts - an optional index position within the text of the <code>hs.styledtext</code> object indicating the beginning of the substring to return numerical values for.  Defaults to 1, the beginning of the objects text.  If this number is negative, it is counted backwards from the end of the object's text (i.e. -1 would be the last character position).</li>
<li>ends   - an optional index position within the text of the <code>hs.styledtext</code> object indicating the end of the substring to return numerical values for.  Defaults to the value of <code>starts</code>.  If this number is negative, it is counted backwards from the end of the object's text.</li>
</ul>
<p>Returns:</p>
<ul>
<li>a list of integers representing the internal numeric representation of the characters in the <code>hs.styledtext</code> object specified by the given indicies.</li>
</ul>
<p>Notes:</p>
<ul>
<li><code>starts</code> and <code>ends</code> follow the conventions of <code>i</code> and <code>j</code> for Lua's <code>string.sub</code> function.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="convert">
	<h5><a href="#convert">convert</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.styledtext:convert([type]) -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Converts the styledtext object into the data format specified.</p>
<p>Parameters:</p>
<ul>
<li>type          - a string indicating the format to convert the styletext object into.  Defaults to "html".  The string may be one of the following:<ul>
<li>"text"      - Plain text document.</li>
<li>"rtf"        - Rich text format document.</li>
<li>"rtfd"       - Rich text format with attachments document.</li>
<li>"html"       - Hypertext Markup Language (HTML) document.</li>
<li>"word"       - Microsoft Word document.</li>
<li>"wordXML"    - Microsoft Word XML (WordML schema) document.</li>
<li>"webArchive" - Web Kit WebArchive document.</li>
<li>"openXML"    - ECMA Office Open XML text document format.</li>
<li>"open"       - OASIS Open Document text document format.</li>
</ul>
</li>
</ul>
<p>Returns:</p>
<ul>
<li>a string containing the converted data</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="copy">
	<h5><a href="#copy">copy</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.styledtext:copy(styledText) -&gt; styledText object</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Create a copy of the <code>hs.styledtext</code> object.</p>
<p>Parameters:</p>
<ul>
<li>styledText - an <code>hs.styledtext</code> object</li>
</ul>
<p>Returns:</p>
<ul>
<li>a copy of the styledText object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="find">
	<h5><a href="#find">find</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.styledtext:find(pattern, [init, [plain]]) -&gt; start, end, ... | nil</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the indicies of the first occurrence of the specified pattern in the text of the <code>hs.styledtext</code> object.  Mimics the Lua <code>string.find</code> function.</p>
<p>Parameters:</p>
<ul>
<li>pattern  - a string containing the pattern to locate.  See the Lua manual, section 6.4.1 (<code>help.lua._man._6_4_1</code>) for more details.</li>
<li>init     - an optional integer specifying the location within the text to start the pattern search</li>
<li>plain    - an optional boolean specifying whether or not to treat the pattern as plain text (i.e. an exact match).  Defaults to false.  If you wish to specify this argument, you must also specify init.</li>
</ul>
<p>Returns:</p>
<ul>
<li>if a match is found, <code>start</code> and <code>end</code> will be the indices where the pattern was first located.  If captures were specified in the pattern, they will also be returned as additional arguments after <code>start</code> and <code>end</code>.  If the pattern was not found in the text, then this method returns nil.</li>
</ul>
<p>Notes:</p>
<ul>
<li>Any captures returned are returned as Lua Strings, not as <code>hs.styledtext</code> objects.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getString">
	<h5><a href="#getString">getString</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.styledtext:getString([starts], [ends]) -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the text of the <code>hs.styledtext</code> object as a Lua String</p>
<p>Parameters:</p>
<ul>
<li>starts - an optional index position within the text of the <code>hs.styledtext</code> object indicating the beginning of the substring to return the string for.  Defaults to 1, the beginning of the objects text.  If this number is negative, it is counted backwards from the end of the object's text (i.e. -1 would be the last character position).</li>
<li>ends   - an optional index position within the text of the <code>hs.styledtext</code> object indicating the end of the substring to return the string for.  Defaults to the length of the objects text.  If this number is negative, it is counted backwards from the end of the object's text.</li>
</ul>
<p>Returns:</p>
<ul>
<li>a string containing the text of the <code>hs.styledtext</code> object specified</li>
</ul>
<p>Notes:</p>
<ul>
<li><code>starts</code> and <code>ends</code> follow the conventions of <code>i</code> and <code>j</code> for Lua's <code>string.sub</code> function.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="gmatch">
	<h5><a href="#gmatch">gmatch</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.styledtext:gmatch(pattern) -&gt; iterator-function</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns an iterator function which will return the captures (or the entire pattern) of the next match of the specified pattern in the text of the <code>hs.styledtext</code> object each time it is called.  Mimics the Lua <code>string.gmatch</code> function.</p>
<p>Parameters:</p>
<ul>
<li>pattern  - a string containing the pattern to locate.  See the Lua manual, section 6.4.1 (<code>help.lua._man._6_4_1</code>) for more details.</li>
</ul>
<p>Returns:</p>
<ul>
<li>an iterator function which will return the captures (or the entire pattern) of the next match of the specified pattern in the text of the <code>hs.styledtext</code> object each time it is called.</li>
</ul>
<p>Notes:</p>
<ul>
<li>Any captures (or the entire pattern) returned by the iterator are returned as Lua Strings, not as <code>hs.styledtext</code> objects.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="isIdentical">
	<h5><a href="#isIdentical">isIdentical</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.styledtext:isIdentical(styledText) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Determine if the <code>styledText</code> object is identical to the one specified.</p>
<p>Parameters:</p>
<ul>
<li>styledText - an <code>hs.styledtext</code> object</li>
</ul>
<p>Returns:</p>
<ul>
<li>a boolean value indicating whether or not the styled text objects are identical, both in text content and attributes specified.</li>
</ul>
<p>Notes:</p>
<ul>
<li>comparing two <code>hs.styledtext</code> objects with the <code>==</code> operator only compares whether or not the string values are identical.  This method also compares their attributes.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="len">
	<h5><a href="#len">len</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.styledtext:len() -&gt; integer</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the length of the text of the <code>hs.styledtext</code> object.  Mimics the Lua <code>string.len</code> function.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>an integer which is the length of the text of the <code>hs.styledtext</code> object.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="lower">
	<h5><a href="#lower">lower</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.styledtext:lower() -&gt; styledText object</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a copy of the <code>hs.styledtext</code> object with all alpha characters converted to lower case.  Mimics the Lua <code>string.lower</code> function.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>a copy of the <code>hs.styledtext</code> object with all alpha characters converted to lower case</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="match">
	<h5><a href="#match">match</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.styledtext:match(pattern, [init]) -&gt; match ... | nil</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the first occurrence of the captures in the specified pattern (or the complete pattern, if no captures are specified) in the text of the <code>hs.styledtext</code> object.  Mimics the Lua <code>string.match</code> function.</p>
<p>Parameters:</p>
<ul>
<li>pattern  - a string containing the pattern to locate.  See the Lua manual, section 6.4.1 (<code>help.lua._man._6_4_1</code>) for more details.</li>
<li>init     - an optional integer specifying the location within the text to start the pattern search</li>
</ul>
<p>Returns:</p>
<ul>
<li>if a match is found, the captures in the specified pattern (or the complete pattern, if no captures are specified).  If the pattern was not found in the text, then this method returns nil.</li>
</ul>
<p>Notes:</p>
<ul>
<li>Any captures (or the entire pattern) returned are returned as Lua Strings, not as <code>hs.styledtext</code> objects.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="removeStyle">
	<h5><a href="#removeStyle">removeStyle</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.styledtext:removeStyle(attributes, [starts], [ends]) -&gt; styledText object</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Return a copy of the <code>hs.styledtext</code> object containing the changes to its attributes specified in the <code>attributes</code> table.</p>
<p>Parameters:</p>
<ul>
<li>attributes - an array of attribute labels to remove (set to <code>nil</code>) from the <code>hs.styledtext</code> object.</li>
<li>starts     - an optional index position within the text of the <code>hs.styledtext</code> object indicating the beginning of the substring to remove attributes for.  Defaults to 1, the beginning of the object's text.  If this number is negative, it is counted backwards from the end of the object's text (i.e. -1 would be the last character position).</li>
<li>ends       - an optional index position within the text of the <code>hs.styledtext</code> object indicating the end of the substring to remove attributes for.  Defaults to the length of the object's text.  If this number is negative, it is counted backwards from the end of the object's text.</li>
</ul>
<p>Returns:</p>
<ul>
<li>a copy of the <code>hs.styledtext</code> object with the attributes specified removed from the given range of the original object.</li>
</ul>
<p>Notes:</p>
<ul>
<li><p><code>starts</code> and <code>ends</code> follow the conventions of <code>i</code> and <code>j</code> for Lua's <code>string.sub</code> function.</p>
</li>
<li><p>See the module description documentation (<code>help.hs.styledtext</code>) for a list of officially recognized attribute label names.</p>
</li>
<li>The officially recognized attribute labels were chosen for brevity or for consistency with conventions used in Hammerspoon's other modules.  If you know the Objective-C name for an attribute, you can list it instead of an officially recognized label, allowing the removal of attributes which this module cannot manipulate in other ways.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="rep">
	<h5><a href="#rep">rep</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.styledtext:rep(n, [separator]) -&gt; styledText object</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns an <code>hs.styledtext</code> object which contains <code>n</code> repetitions of the <code>hs.styledtext</code> object, optionally with <code>separator</code> between each repetition.  Mimics the Lua <code>string.rep</code> function.</p>
<p>Parameters:</p>
<ul>
<li>n         - the number of times to repeat the <code>hs.styledtext</code> object.</li>
<li>separator - an optional string or <code>hs.styledtext</code> object to insert between repetitions.</li>
</ul>
<p>Returns:</p>
<ul>
<li>an <code>hs.styledtext</code> object which contains <code>n</code> repitions of the object, including <code>separator</code> between repetitions, if it is specified.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="setString">
	<h5><a href="#setString">setString</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.styledtext:setString(string, [starts], [ends], [clear]) -&gt; styledText object</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Return a copy of the <code>hs.styledtext</code> object containing the changes to its attributes specified in the <code>attributes</code> table.</p>
<p>Parameters:</p>
<ul>
<li>string     - a string, table, or <code>hs.styledtext</code> object to insert or replace the substring specified.</li>
<li>starts     - an optional index position within the text of the <code>hs.styledtext</code> object indicating the beginning of the destination for the specified string.  Defaults to 1, the beginning of the objects text.  If this number is negative, it is counted backwards from the end of the object's text (i.e. -1 would be the last character position).</li>
<li>ends       - an optional index position within the text of the <code>hs.styledtext</code> object indicating the end of destination for the specified string.  Defaults to the length of the objects text.  If this number is negative, it is counted backwards from the end of the object's text.  If this number is 0, then the substring is inserted at the index specified by <code>starts</code> rather than replacing it.</li>
<li>clear      - an optional boolean indicating whether or not the attributes of the new string should be included (true) or whether the new substring should inherit the attributes of the first character replaced (false).  Defaults to false if <code>string</code> is a Lua String or number; otherwise defaults to true.</li>
</ul>
<p>Returns:</p>
<ul>
<li>a copy of the <code>hs.styledtext</code> object with the specified substring replacement to the original object, or nil if an error occurs</li>
</ul>
<p>Notes:</p>
<ul>
<li><p><code>starts</code> and <code>ends</code> follow the conventions of <code>i</code> and <code>j</code> for Lua's <code>string.sub</code> function except that <code>starts</code> must refer to an index preceding or equal to <code>ends</code>, even after negative and out-of-bounds indices are adjusted for.</p>
</li>
<li><p>See the module description documentation (<code>help.hs.styledtext</code>) for a description of the attributes table format</p>
</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="setStyle">
	<h5><a href="#setStyle">setStyle</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.styledtext:setStyle(attributes, [starts], [ends], [clear]) -&gt; styledText object</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Return a copy of the <code>hs.styledtext</code> object containing the changes to its attributes specified in the <code>attributes</code> table.</p>
<p>Parameters:</p>
<ul>
<li>attributes - a table of attribute key-value pairs to apply to the object between the positions of <code>starts</code> and <code>ends</code></li>
<li>starts     - an optional index position within the text of the <code>hs.styledtext</code> object indicating the beginning of the substring to set attributes for.  Defaults to 1, the beginning of the objects text.  If this number is negative, it is counted backwards from the end of the object's text (i.e. -1 would be the last character position).</li>
<li>ends       - an optional index position within the text of the <code>hs.styledtext</code> object indicating the end of the substring to set attributes for.  Defaults to the length of the objects text.  If this number is negative, it is counted backwards from the end of the object's text.</li>
<li>clear      - an optional boolean indicating whether or not the attributes specified should completely replace the existing attributes (true) or be added to/modify them (false).  Defaults to false.</li>
</ul>
<p>Returns:</p>
<ul>
<li>a copy of the <code>hs.styledtext</code> object with the attributes specified applied to the given range of the original object.</li>
</ul>
<p>Notes:</p>
<ul>
<li><p><code>starts</code> and <code>ends</code> follow the conventions of <code>i</code> and <code>j</code> for Lua's <code>string.sub</code> function.</p>
</li>
<li><p>See the module description documentation (<code>help.hs.styledtext</code>) for a description of the attributes table format</p>
</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="sub">
	<h5><a href="#sub">sub</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.styledtext:sub(starts, [ends]) -&gt; styledText object</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a substring, including the style attributes, specified by the given indicies from the <code>hs.styledtext</code> object.  Mimics the Lua <code>string.sub</code> function.</p>
<p>Parameters:</p>
<ul>
<li>starts - the index position within the text of the <code>hs.styledtext</code> object indicating the beginning of the substring to return.  If this number is negative, it is counted backwards from the end of the object's text (i.e. -1 would be the last character position).</li>
<li>ends   - an optional index position within the text of the <code>hs.styledtext</code> object indicating the end of the substring to return.  Defaults to the length of the objects text.  If this number is negative, it is counted backwards from the end of the object's text.</li>
</ul>
<p>Returns:</p>
<ul>
<li>an <code>hs.styledtext</code> object containing the specified substring.</li>
</ul>
<p>Notes:</p>
<ul>
<li><code>starts</code> and <code>ends</code> follow the conventions of <code>i</code> and <code>j</code> for Lua's <code>string.sub</code> function.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="upper">
	<h5><a href="#upper">upper</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.styledtext:upper() -&gt; styledText object</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a copy of the <code>hs.styledtext</code> object with all alpha characters converted to upper case.  Mimics the Lua <code>string.upper</code> function.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>a copy of the <code>hs.styledtext</code> object with all alpha characters converted to upper case</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
