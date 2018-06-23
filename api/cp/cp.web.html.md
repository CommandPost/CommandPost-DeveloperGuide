# [docs](index.md) » cp.web.html
---

Functions for Generating HTML markup.

This library allows the creation of 'safe' HTML using via code.

Examples:

```lua
local html = require "cp.web.html"
print html.p "Hello world!"								-- "<p>Hello world!</p>"
print html.p { class = "custom" } "Hello world!"		-- "<p class='custom'>Hello world!</p>"
print html.p { class = "custom" } (
	html.b "Bold" .. " and " .. html.i "italic" .. "."
)
-- "<p class='custom'><b>Bold</b> and <i>italic</i>.</p>"
print html("1 < 2")										-- "1 &lt; 2" (escaped)
print html("1 < 2", true)								-- "1 < 2" (unescaped)
print html.p ("<b>bold</b>", true)						-- "<p><b>bold</b></p>"
```

Be aware that concatonating with ".." can behave unexpectedly in some cases. For example:

```lua
local name = "world!"
print html.p "Hello " .. name					-- "<p>Hello </p>world!"
```

The `"Hello"` gets inserted into the `p` tag, but the `name` gets concatonated after the closing tag.
To get the `name` inside the `p` tag, we need to put brackets around the content:

```lua
print html.p ("Hello " .. name)					-- "<p>Hello world!</p>"
```

Any tag name can be generated, along with any attribute. The results are correctly escaped.
There are two 'special' tag names:
 * `CDATA`	- will generate a `&lt;![CDATA[ ... ]]&gt;` section with the content contained.
 * `__`		- (double underscore) will generate a `&lt!-- ... --&gt` comment block.

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
<li>Functions - API calls offered directly by the extension</li>
  <ul>
	<li><a href="#is">is</a></li>
  </ul>
<li>Methods - API calls which can only be made on an object returned by a constructor</li>
  <ul>
	<li><a href="#append">append</a></li>
	<li><a href="#prepend">prepend</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="is">
	<h5><a href="#is">is</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.web.html.is(value) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Checks if the <code>value</code> is an <code>cp.web.html</code> block.</p>
<p>Parameters:</p>
<ul>
<li>value     - the value to check</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if it is an HTML block, or <code>false</code> otherwise.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Methods</h4>
  <section id="append">
	<h5><a href="#append">append</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.web.html:append(newContent[, escaped]) -&gt; self</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Appends the content. If specified, the <code>escaped</code> value will override any default escaping for the content type.</p>
<p>Parameters:</p>
<ul>
<li>newContent        - The content to append to the contents of the HTML block.</li>
<li>escaped           - May be set to override default escaping for the content.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The same HTML block instance.</li>
</ul>
<p>Notes:</p>
<ul>
<li>The <code>newContent</code> may be almost any value. The default handling is below:
<strong> <code>cp.web.html</code> instance: Any other HTML block can be added. Default escaping: <code>false</code>.</strong> <code>function</code>: Functions will be executed every time the HTML block is converted to a string. Default escaping: whatever the default is for the returned value.
<strong> <code>list</code>: Tables which are lists will be iterrated and each item will be evaluated each time the HTML block is converted to a string. Default escaping: the default for each item.</strong> <em>everything else</em>: Converted to a string via the <code>tostring</code> function. Default escaping: <code>true</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="prepend">
	<h5><a href="#prepend">prepend</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.web.html:prepend(newContent[, escaped]) -&gt; self</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Prepends the content. If specified, the <code>escaped</code> value will override any default escaping for the content type.</p>
<p>Parameters:</p>
<ul>
<li>newContent        - The content to prepend to the contents of the HTML block.</li>
<li>escaped           - May be set to override default escaping for the content.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The same HTML block instance.</li>
</ul>
<p>Notes:</p>
<ul>
<li>The <code>newContent</code> may be almost any value. The default handling is below:
<strong> <code>cp.web.html</code> instance: Any other HTML block can be added. Default escaping: <code>false</code>.</strong> <code>function</code>: Functions will be executed every time the HTML block is converted to a string. Default escaping: whatever the default is for the returned value.
<strong> <code>list</code>: Tables which are lists will be iterrated and each item will be evaluated each time the HTML block is converted to a string. Default escaping: the default for each item.</strong> <em>everything else</em>: Converted to a string via the <code>tostring</code> function. Default escaping: <code>true</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
