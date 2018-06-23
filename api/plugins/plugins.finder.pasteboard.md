# [docs](index.md) » plugins.finder.pasteboard
---

Handy text tools.

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
	<li><a href="#processText">processText</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="processText">
	<h5><a href="#processText">processText</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finder.pasteboard.processText(value, copyAndPaste) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Processes Text</p>
<p>Parameters:</p>
<ul>
<li>value - The type of text manipulation you want to do. Current values are: <code>uppercase</code>, <code>lowercase</code> or <code>camelcase</code>.</li>
<li>copyAndPaste - A boolean that defines whether or not we should trigger copy and paste.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
