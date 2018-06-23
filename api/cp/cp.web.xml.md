# [docs](index.md) » cp.web.xml
---

Functions for Generating XML markup.

This library allows the creation of 'safe' XML using via code.

Examples:

```lua
local xml = require "cp.web.xml"
print xml.Root "Hello world!"						-- "<Root>Hello world!</Root>"
print xml.Root { class = "custom" } "Hello world!"	-- "<Root class='custom'>Hello world!</Root>"
print xml.Root { class = "custom" } (
	xml.Child "One" .. " and " .. xml.Child "Two" .. "."
)
-- "<Root class='custom'><Child>One</Child> and <Child>Two</Child>.</Root>"
print xml("1 < 2")										-- "1 &lt; 2" (escaped)
print xml("1 < 2", true)								-- "1 < 2" (unescaped)
print xml.Root ("<Child>One</Child>", true)				-- "<Root><Child>One</Child></Root>"
```

Be aware that concatonating with ".." can behave unexpectedly in some cases. For example:

```lua
local name = "world!"
print xml.Root "Hello " .. name					-- "<Root>Hello </Root>world!"
```

The `"Hello"` gets inserted into the `Root` tag, but the `name` gets concatonated after the closing tag.
To get the `name` inside the `Root` tag, we need to put brackets around the content:

```lua
print xml.Root ("Hello " .. name)					-- "<Root>Hello world!</Root>"
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
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="is">
	<h5><a href="#is">is</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.web.xml.is(value) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Checks if the <code>value</code> is an <code>cp.web.xml</code> block.</p>
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
