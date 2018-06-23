# [docs](index.md) » cp.apple.finalcutpro.main.PrimaryToolbar
---

Timeline Toolbar.

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
<li>Variables - Configurable values</li>
  <ul>
	<li><a href="#isShowing">isShowing</a></li>
  </ul>
<li>Functions - API calls offered directly by the extension</li>
  <ul>
	<li><a href="#matches">matches</a></li>
  </ul>
<li>Constructors - API calls which return an object, typically one that offers API methods</li>
  <ul>
	<li><a href="#new">new</a></li>
  </ul>
<li>Methods - API calls which can only be made on an object returned by a constructor</li>
  <ul>
	<li><a href="#app">app</a></li>
	<li><a href="#browserButton">browserButton</a></li>
	<li><a href="#parent">parent</a></li>
	<li><a href="#shareButton">shareButton</a></li>
	<li><a href="#UI">UI</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Variables</h4>
  <section id="isShowing">
	<h5><a href="#isShowing">isShowing</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.PrimaryToolbar.isShowing &lt;cp.prop: boolean&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Is the Primary Toolbar showing?</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Functions</h4>
  <section id="matches">
	<h5><a href="#matches">matches</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.PrimaryToolbar.matches(element) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Checks to see if an element matches what we think it should be.</p>
<p>Parameters:</p>
<ul>
<li>element - An <code>axuielementObject</code> to check.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if matches otherwise <code>false</code></li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Constructors</h4>
  <section id="new">
	<h5><a href="#new">new</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.PrimaryToolbar.new(parent) -&gt; PrimaryToolbar</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constructor</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new <code>PrimaryToolbar</code> instance.</p>
<p>Parameters:</p>
<ul>
<li>parent - The parent object.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A new <code>PrimaryToolbar</code> object.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Methods</h4>
  <section id="app">
	<h5><a href="#app">app</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.PrimaryToolbar:app() -&gt; App</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the app instance representing Final Cut Pro.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>App</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="browserButton">
	<h5><a href="#browserButton">browserButton</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.PrimaryToolbar:browserButton() -&gt; CheckBox</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets the Browser Button Checkbox.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>CheckBox</code> object.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="parent">
	<h5><a href="#parent">parent</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.PrimaryToolbar:parent() -&gt; parent</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the parent object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>parent</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="shareButton">
	<h5><a href="#shareButton">shareButton</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.PrimaryToolbar:shareButton() -&gt; Button</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets the Share Button.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>Button</code> object.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="UI">
	<h5><a href="#UI">UI</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.PrimaryToolbar:UI() -&gt; axuielementObject</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets the Primary Toolbar UI.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>axuielementObject</code></li>
</ul>
</td>
	  </tr>
	</table>
  </section>
