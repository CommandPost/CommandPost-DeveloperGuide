# [docs](index.md) » cp.json
---

A collection of handy JSON tools.

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
	<li><a href="#decode">decode</a></li>
	<li><a href="#encode">encode</a></li>
	<li><a href="#prop">prop</a></li>
	<li><a href="#read">read</a></li>
	<li><a href="#write">write</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="decode">
	<h5><a href="#decode">decode</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.json.decode(jsonString) -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Decodes JSON into a table</p>
<p>Parameters:</p>
<ul>
<li>jsonString - A string containing some JSON data</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table representing the supplied JSON data</li>
</ul>
<p>Notes:</p>
<ul>
<li>This is useful for retrieving some of the more complex lua table structures as a persistent setting (see <code>hs.settings</code>)</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="encode">
	<h5><a href="#encode">encode</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.json.encode(val[, prettyprint]) -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Encodes a table as JSON</p>
<p>Parameters:</p>
<ul>
<li>val - A table containing data to be encoded as JSON</li>
<li>prettyprint - An optional boolean, true to format the JSON for human readability, false to format the JSON for size efficiency. Defaults to false</li>
</ul>
<p>Returns:</p>
<ul>
<li>A string containing a JSON representation of the supplied table</li>
</ul>
<p>Notes:</p>
<ul>
<li>This is useful for storing some of the more complex lua table structures as a persistent setting (see <code>hs.settings</code>)</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="prop">
	<h5><a href="#prop">prop</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.json.prop(folder, filename, defaultValue) -&gt; cp.prop</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a <code>cp.prop</code> instance for a JSON file.</p>
<p>Parameters:</p>
<ul>
<li>path - The path to the JSON folder (i.e. "~/Library/Caches")</li>
<li>folder - The folder containing the JSON file (i.e. "Final Cut Pro")</li>
<li>filename - The filename of the JSON file (i.e. "Test.json")</li>
<li>defaultValue - The default value if the JSON file doesn't exist yet.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A <code>cp.prop</code> instance.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="read">
	<h5><a href="#read">read</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.json.read(path) -&gt; table | nil</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Attempts to read the specified path as a JSON file.
If the file cannot be found, <code>nil</code> is returned. If the file is
not a JSON file, an error will occur.</p>
<p>Parameters:</p>
<ul>
<li>path      - The JSON file path.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The JSON file converted into table, or <code>nil</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="write">
	<h5><a href="#write">write</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.json.write(path, data) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Writes data to a JSON file.</p>
<p>Parameters:</p>
<ul>
<li>path - The path to where you want to save the JSON file.</li>
<li>data - A table containing data to be encoded as JSON.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successfully saved, otherwise <code>false</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
