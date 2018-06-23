# [docs](index.md) » cp.web.generate
---

Functions for Generating HTML UI Items

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
	<li><a href="#button">button</a></li>
	<li><a href="#checkbox">checkbox</a></li>
	<li><a href="#dropdown">dropdown</a></li>
	<li><a href="#heading">heading</a></li>
	<li><a href="#javascript">javascript</a></li>
	<li><a href="#setWebviewLabel">setWebviewLabel</a></li>
	<li><a href="#text">text</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="button">
	<h5><a href="#button">button</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.web.generate.button() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Generates a HTML Button</p>
<p>Parameters:</p>
<ul>
<li>data - Table containing the data you want to display on the Checkbox</li>
<li>customTrigger - Custom label used for JavaScript Callback</li>
<li>customWidth - Number to set the width of the button to</li>
<li>customID - Overrides the random HTML ID</li>
</ul>
<p>Returns:</p>
<ul>
<li>String containing the HTML</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="checkbox">
	<h5><a href="#checkbox">checkbox</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.web.generate.checkbox() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Generates a HTML Checkbox</p>
<p>Parameters:</p>
<ul>
<li>data - Table containing the data you want to display on the Checkbox</li>
<li>customTrigger - Custom label used for JavaScript Callback</li>
<li>customID - Custom ID used for the HTML objects</li>
</ul>
<p>Returns:</p>
<ul>
<li>String containing the HTML</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="dropdown">
	<h5><a href="#dropdown">dropdown</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.web.generate.dropdown() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Generates a HTML Dropdown</p>
<p>Parameters:</p>
<ul>
<li>title - Title to put in front of the Dropdown. Can be "".</li>
<li>data - Table containing the data you want to display on the Checkbox</li>
<li>customTrigger - Custom label used for JavaScript Callback</li>
</ul>
<p>Returns:</p>
<ul>
<li>String containing the HTML</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="heading">
	<h5><a href="#heading">heading</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.web.generate.heading() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Generates a HTML Heading</p>
<p>Parameters:</p>
<ul>
<li>data - Table containing the data you want to display on the Checkbox</li>
</ul>
<p>Returns:</p>
<ul>
<li>String containing the HTML</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="javascript">
	<h5><a href="#javascript">javascript</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.web.generate.javascript(script, context) -&gt; cp.web.html</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Generates a HTML Heading</p>
<p>Parameters:</p>
<ul>
<li>data - Table containing the data you want to display on the Checkbox</li>
</ul>
<p>Returns:</p>
<ul>
<li>String containing the HTML</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="setWebviewLabel">
	<h5><a href="#setWebviewLabel">setWebviewLabel</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.web.generate.setWebviewLabel() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Sets the WebView Label</p>
<p>Parameters:</p>
<ul>
<li>value - WebView Label as string</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="text">
	<h5><a href="#text">text</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.web.generate.text() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Generates a blank HTML</p>
<p>Parameters:</p>
<ul>
<li>data - Table containing the data you want to display.</li>
</ul>
<p>Returns:</p>
<ul>
<li>String containing the HTML</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
