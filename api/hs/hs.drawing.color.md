# [docs](index.md) » hs.drawing.color
---

Additions to hs.drawing which provide access to the system color lists and a wider variety of ways to represent color within Hammerspoon.

Color is represented within Hammerspoon as a table containing keys which tell Hammerspoon how the color is specified.  You can specify a color in one of the following ways, depending upon the keys you supply within the table:

* As a combination of Red, Green, and Blue elements (RGB Color):
  * red   - the red component of the color specified as a number from 0.0 to 1.0.
  * green - the green component of the color specified as a number from 0.0 to 1.0.
  * blue  - the blue component of the color specified as a number from 0.0 to 1.0.
  * alpha - the color transparency from 0.0 (completely transparent) to 1.0 (completely opaque)

* As a combination of Hue, Saturation, and Brightness (HSB or HSV Color):
  * hue        - the hue component of the color specified as a number from 0.0 to 1.0.
  * saturation - the saturation component of the color specified as a number from 0.0 to 1.0.
  * brightness - the brightness component of the color specified as a number from 0.0 to 1.0.
  * alpha      - the color transparency from 0.0 (completely transparent) to 1.0 (completely opaque)

* As grayscale (Grayscale Color):
  * white - the ratio of white to black from 0.0 (completely black) to 1.0 (completely white)
  * alpha - the color transparency from 0.0 (completely transparent) to 1.0 (completely opaque)

* From the system or Hammerspoon color lists:
  * list - the name of a system color list or a collection list defined in `hs.drawing.color`
  * name - the color name within the specified color list

* As an HTML style hex color specification:
  * hex   - a string of the format "#rrggbb" or "#rgb" where `r`, `g`, and `b` are hexadecimal digits (i.e. 0-9, A-F)
  * alpha - the color transparency from 0.0 (completely transparent) to 1.0 (completely opaque)

* From an image to be used as a tiled pattern:
  * image - an `hs.image` object representing the image to be used as a tiled pattern

Any combination of the above keys may be specified within the color table and they will be evaluated in the following order:
  1. if the `image` key is specified, it will be used to create a tiling pattern.
  2. If the `list` and `name` keys are specified, and if they can be matched to an existing color within the system color lists, that color is used.
  3. If the `hue` key is provided, then the color is generated as an HSB color
  4. If the `white` key is provided, then the color is generated as a Grayscale color
  5. Otherwise, an RGB color is generated.

Except where specified above to indicate the color model being used, any key which is not provided defaults to a value of 0.0, except for `alpha`, which defaults to 1.0.  This means that specifying an empty table as the color will result in an opaque black color.

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
	<li><a href="#definedCollections">definedCollections</a></li>
  </ul>
<li>Variables - Configurable values</li>
  <ul>
	<li><a href="#ansiTerminalColors">ansiTerminalColors</a></li>
	<li><a href="#hammerspoon">hammerspoon</a></li>
	<li><a href="#x11">x11</a></li>
  </ul>
<li>Functions - API calls offered directly by the extension</li>
  <ul>
	<li><a href="#asHSB">asHSB</a></li>
	<li><a href="#asRGB">asRGB</a></li>
	<li><a href="#colorsFor">colorsFor</a></li>
	<li><a href="#lists">lists</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Constants</h4>
  <section id="definedCollections">
	<h5><a href="#definedCollections">definedCollections</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.drawing.color.definedCollections</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>This table contains this list of defined color collections provided by the <code>hs.drawing.color</code> module.  Collections differ from the system color lists in that you can modify the color values their members contain by modifying the table at <code>hs.drawing.color.&lt;collection&gt;.&lt;color&gt;</code> and future references to that color will reflect the new changes, thus allowing you to customize the palettes for your installation.</p>
<p>Notes:</p>
<ul>
<li>This list is a constant, but the members it refers to are not.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Variables</h4>
  <section id="ansiTerminalColors">
	<h5><a href="#ansiTerminalColors">ansiTerminalColors</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.drawing.color.ansiTerminalColors</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>A collection of colors representing the ANSI Terminal color sequences.  The color definitions are based upon code found at <a href="https://github.com/balthamos/geektool-3">https://github.com/balthamos/geektool-3</a> in the /NerdTool/classes/ANSIEscapeHelper.m file.</p>
<p>Notes:</p>
<ul>
<li>This is not a constant, so you can adjust the colors at run time for your installation if desired.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="hammerspoon">
	<h5><a href="#hammerspoon">hammerspoon</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.drawing.color.hammerspoon</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>This table contains a collection of various useful pre-defined colors:</p>
<ul>
<li>osx_red - The same red used for OS X window close buttons</li>
<li>osx_green - The same green used for OS X window zoom buttons</li>
<li>osx_yellow - The same yellow used for OS X window minimize buttons</li>
</ul>
<p>Notes:</p>
<ul>
<li><p>This is not a constant, so you can adjust the colors at run time for your installation if desired.</p>
</li>
<li><p>Previous versions of Hammerspoon included these colors at the <code>hs.drawing.color</code> path; for backwards compatibility, the keys of this table are replicated at that path as long as they do not conflict with any other color collection or function within the <code>hs.drawing.color</code> module.  You really should adjust your code to use the collection, as this may change in the future.</p>
</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="x11">
	<h5><a href="#x11">x11</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.drawing.color.x11</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>A collection of colors representing the X11 color names as defined at  <a href="https://en.wikipedia.org/wiki/Web_colors#X11_color_names">https://en.wikipedia.org/wiki/Web_colors#X11_color_names</a> (names in lowercase)</p>
<p>Notes:</p>
<ul>
<li>This is not a constant, so you can adjust the colors at run time for your installation if desired.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Functions</h4>
  <section id="asHSB">
	<h5><a href="#asHSB">asHSB</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.drawing.color.asHSB(color) -&gt; table | string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a table containing the HSB representation of the specified color.</p>
<p>Parameters:</p>
<ul>
<li>color - a table specifying a color as described in the module definition (see <code>hs.drawing.color</code> in the online help or Dash documentation)</li>
</ul>
<p>Returns:</p>
<ul>
<li>a table containing the hue, saturation, brightness, and alpha keys representing the specified color as HSB or a string describing the color's colorspace if conversion is not possible.</li>
</ul>
<p>Notes:</p>
<ul>
<li>See also <code>hs.drawing.color.asRGB</code></li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="asRGB">
	<h5><a href="#asRGB">asRGB</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.drawing.color.asRGB(color) -&gt; table | string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a table containing the RGB representation of the specified color.</p>
<p>Parameters:</p>
<ul>
<li>color - a table specifying a color as described in the module definition (see <code>hs.drawing.color</code> in the online help or Dash documentation)</li>
</ul>
<p>Returns:</p>
<ul>
<li>a table containing the red, blue, green, and alpha keys representing the specified color as RGB or a string describing the color's colorspace if conversion is not possible.</li>
</ul>
<p>Notes:</p>
<ul>
<li>See also <code>hs.drawing.color.asHSB</code></li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="colorsFor">
	<h5><a href="#colorsFor">colorsFor</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.drawing.color.colorsFor(list) -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a table containing the colors for the specified system color list or hs.drawing.color collection.</p>
<p>Parameters:</p>
<ul>
<li>list - the name of the list to provide colors for</li>
</ul>
<p>Returns:</p>
<ul>
<li>a table whose keys are made from the colors provided by the color list or nil if the list does not exist.</li>
</ul>
<p>Notes:</p>
<ul>
<li>Where possible, each color node is provided as its RGB color representation.  Where this is not possible, the color node contains the keys <code>list</code> and <code>name</code> which identify the indicated color.  This means that you can use the following wherever a color parameter is expected: <code>hs.drawing.color.colorsFor(list)["color-name"]</code></li>
<li>This function provides a tostring metatable method which allows listing the defined colors in the list in the Hammerspoon console with: <code>hs.drawing.colorsFor(list)</code></li>
<li>See also <code>hs.drawing.color.lists</code></li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="lists">
	<h5><a href="#lists">lists</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.drawing.color.lists() -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a table containing the system color lists and hs.drawing.color collections with their defined colors.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>a table whose keys are made from the currently defined system color lists and hs.drawing.color collections.  Each color list key refers to a table whose keys make up the colors provided by the specific color list.</li>
</ul>
<p>Notes:</p>
<ul>
<li>Where possible, each color node is provided as its RGB color representation.  Where this is not possible, the color node contains the keys <code>list</code> and <code>name</code> which identify the indicated color.  This means that you can use the following wherever a color parameter is expected: <code>hs.drawing.color.lists()["list-name"]["color-name"]</code></li>
<li>This function provides a tostring metatable method which allows listing the defined color lists in the Hammerspoon console with: <code>hs.drawing.color.lists()</code></li>
<li>See also <code>hs.drawing.color.colorsFor</code></li>
</ul>
</td>
	  </tr>
	</table>
  </section>
