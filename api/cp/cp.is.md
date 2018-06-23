# [docs](index.md) » cp.is
---

A simple class that lets you test if a value `is` a particular type.
Note: for best performance, assign the specific checks you want to use to local functions. Eg:

```lua
local is_nothing = require("cp.is").nothing
is_nothing(nil) == true
```

You can also get functions that negate the functions below by calling `is.nt.XXX(...)` (read: "isn't XXX").
The individual functions are not documented, but all will work as expected. Eg:

```lua
is.blank("") == true
is.nt.blank("") == false
```

They can also be assigned directly to local values for better performance:

```lua
local isnt_blank = is.nt.blank
isnt_blank(nil) == false
```

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
	<li><a href="#blank">blank</a></li>
	<li><a href="#boolean">boolean</a></li>
	<li><a href="#callable">callable</a></li>
	<li><a href="#falsey">falsey</a></li>
	<li><a href="#fn">fn</a></li>
	<li><a href="#list">list</a></li>
	<li><a href="#nothing">nothing</a></li>
	<li><a href="#number">number</a></li>
	<li><a href="#object">object</a></li>
	<li><a href="#something">something</a></li>
	<li><a href="#string">string</a></li>
	<li><a href="#table">table</a></li>
	<li><a href="#truthy">truthy</a></li>
	<li><a href="#userdata">userdata</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="blank">
	<h5><a href="#blank">blank</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.is.blank(value) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Check if the value is a blank string value - either <code>nil</code> or <code>tostring(value) == ""</code>.</p>
<p>Parameters:</p>
<ul>
<li>value     - the value to check.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if it matches, <code>false</code> if not.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="boolean">
	<h5><a href="#boolean">boolean</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.is.boolean(value) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Check if the value is a <code>function</code>.</p>
<p>Parameters:</p>
<ul>
<li>value     - the value to check</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if it matches, <code>false</code> if not.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="callable">
	<h5><a href="#callable">callable</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.is.callable(value) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Check if the value is a callable - either a <code>function</code> or a <code>table</code> with <code>__call</code> in it's metatable hierarchy.</p>
<p>Parameters:</p>
<ul>
<li>value     - the value to check</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if it matches, <code>false</code> if not.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="falsey">
	<h5><a href="#falsey">falsey</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.is.falsey(value) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Check if the value is a <code>falsey</code> value.
A value is considered to be <code>falsey</code> if it is <code>nil</code> or <code>false</code>.</p>
<p>Parameters:</p>
<ul>
<li>value     - the value to check</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if it matches, <code>false</code> if not.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="fn">
	<h5><a href="#fn">fn</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.is.fn(value) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Check if the value is a <code>function</code>.</p>
<p>Parameters:</p>
<ul>
<li>value     - the value to check</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if it matches, <code>false</code> if not.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="list">
	<h5><a href="#list">list</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.is.list(value) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Check if the value is a <code>list</code>.</p>
<p>Parameters:</p>
<ul>
<li>value     - the value to check</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if it matches, <code>false</code> if not.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="nothing">
	<h5><a href="#nothing">nothing</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.is.nothing(value) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Check if the value is <code>nil</code>.</p>
<p>Parameters:</p>
<ul>
<li>value     - the value to check</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if it matches, <code>false</code> if not.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="number">
	<h5><a href="#number">number</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.is.number(value) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Check if the value is a <code>number</code>.</p>
<p>Parameters:</p>
<ul>
<li>value     - the value to check</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if it matches, <code>false</code> if not.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="object">
	<h5><a href="#object">object</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.is.object(value) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Check if the value is a <code>object</code>.</p>
<p>Parameters:</p>
<ul>
<li>value     - the value to check</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if it matches, <code>false</code> if not.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="something">
	<h5><a href="#something">something</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.is.something(value) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Check if the value is not <code>nil</code>.</p>
<p>Parameters:</p>
<ul>
<li>value     - the value to check</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if it matches, <code>false</code> if not.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="string">
	<h5><a href="#string">string</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.is.string(value) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Check if the value is a string.</p>
<p>Parameters:</p>
<ul>
<li>value     - the value to check</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if it matches, <code>false</code> if not.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="table">
	<h5><a href="#table">table</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.is.table(value) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Check if the value is a <code>table</code>.</p>
<p>Parameters:</p>
<ul>
<li>value     - the value to check</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if it matches, <code>false</code> if not.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="truthy">
	<h5><a href="#truthy">truthy</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.is.truthy(value) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Check if the value is a <code>truthy</code> value.
A value is considered to be truthy if it is not <code>nil</code> nor <code>false</code>.</p>
<p>Parameters:</p>
<ul>
<li>value     - the value to check</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if it matches, <code>false</code> if not.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="userdata">
	<h5><a href="#userdata">userdata</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.is.userdata(value) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Check if the value is a <code>userdata</code> object.</p>
<p>Parameters:</p>
<ul>
<li>value     - the value to check</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if it matches, <code>false</code> if not.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
