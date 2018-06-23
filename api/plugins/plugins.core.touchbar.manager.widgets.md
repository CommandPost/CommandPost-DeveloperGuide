# [docs](index.md) » plugins.core.touchbar.manager.widgets
---

Touch Bar Widgets Manager

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
	<li><a href="#allGroups">allGroups</a></li>
  </ul>
<li>Methods - API calls which can only be made on an object returned by a constructor</li>
  <ul>
	<li><a href="#get">get</a></li>
	<li><a href="#getAll">getAll</a></li>
	<li><a href="#id">id</a></li>
	<li><a href="#new">new</a></li>
	<li><a href="#params">params</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="allGroups">
	<h5><a href="#allGroups">allGroups</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.touchbar.manager.widgets.allGroups() -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a table containing all of the widget groups.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>Table</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Methods</h4>
  <section id="get">
	<h5><a href="#get">get</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.touchbar.manager.widgets:get(id) -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets a Touch Bar widget</p>
<p>Parameters:</p>
<ul>
<li><code>id</code>      - The unique ID for the widget you want to return.</li>
</ul>
<p>Returns:</p>
<ul>
<li>table containing the widget</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getAll">
	<h5><a href="#getAll">getAll</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.touchbar.manager.widgets:getAll() -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns all of the created widgets</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>table containing all of the created callbacks</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="id">
	<h5><a href="#id">id</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.touchbar.manager.widgets:id() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the ID of the widget</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The ID of the widget as a <code>string</code></li>
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
		<td><code>plugins.core.touchbar.manager.widgets:new(id, params) -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new Touch Bar Widget.</p>
<p>Parameters:</p>
<ul>
<li><code>id</code>      - The unique ID for this widget.</li>
</ul>
<p>Returns:</p>
<ul>
<li>table that has been created</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="params">
	<h5><a href="#params">params</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.touchbar.manager.widgets:params() -&gt; function</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the paramaters of the widget</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The paramaters of the widget</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
