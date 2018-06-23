# [docs](index.md) » cp.apple.finalcutpro.content.Clip
---

Represents a clip of media inside FCP.

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
	<li><a href="#filmstrip">filmstrip</a></li>
	<li><a href="#row">row</a></li>
  </ul>
<li>Functions - API calls offered directly by the extension</li>
  <ul>
	<li><a href="#is">is</a></li>
  </ul>
<li>Constructors - API calls which return an object, typically one that offers API methods</li>
  <ul>
	<li><a href="#new">new</a></li>
  </ul>
<li>Methods - API calls which can only be made on an object returned by a constructor</li>
  <ul>
	<li><a href="#getTitle">getTitle</a></li>
	<li><a href="#getType">getType</a></li>
	<li><a href="#UI">UI</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Constants</h4>
  <section id="filmstrip">
	<h5><a href="#filmstrip">filmstrip</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.content.Clip.type.filmstrip</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>A constant for clips which are represented by a filmstrip.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="row">
	<h5><a href="#row">row</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.content.Clip.type.row</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>A constant for clips which are represented by a table row.</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Functions</h4>
  <section id="is">
	<h5><a href="#is">is</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.content.Clip.is(thing) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Checks if the specified <code>thing</code> is a <code>Clip</code> instance.</p>
<p>Parameters:</p>
<ul>
<li><code>thing</code>  - The thing to check.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the <code>thing</code> is a <code>Clip</code>, otherwise returns <code>false</code>.</li>
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
		<td><code>cp.apple.finalcutpro.content.Clip.new(element[, options]) -&gt; Clip</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constructor</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new <code>Clip</code> pointing at the specified element, with the specified options.</p>
<p>Parameters:</p>
<ul>
<li><code>element</code>        - The <code>axuielement</code> the clip represents.</li>
<li><code>options</code>        - A table containing the options for the clip.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The new <code>Clip</code>.</li>
</ul>
<p>Notes:</p>
<ul>
<li>The options may be:
** <code>columnIndex</code>   - A number which will be used to specify the column number to find the title in, if relevant.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Methods</h4>
  <section id="getTitle">
	<h5><a href="#getTitle">getTitle</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.content.Clip:getTitle() -&gt; String</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the title of the clip.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The clip title.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getType">
	<h5><a href="#getType">getType</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.content.Clip:getType() -&gt; Clip.type</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the type of clip (one of the <code>Clip.type</code> values)</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>Clip.type</code> value (e.g. <code>Clip.type.row</code> or Clip.type.filmstrip`)</li>
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
		<td><code>cp.apple.finalcutpro.content.Clip:UI() -&gt; axuielement</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the <code>axuielement</code> for the clip.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>axuielement</code> for the clip.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
