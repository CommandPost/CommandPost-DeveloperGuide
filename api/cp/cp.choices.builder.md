# [docs](index.md) » cp.choices.builder
---

Choices Builder Module.

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
	<li><a href="#new">new</a></li>
  </ul>
<li>Methods - API calls which can only be made on an object returned by a constructor</li>
  <ul>
	<li><a href="#id">id</a></li>
	<li><a href="#params">params</a></li>
	<li><a href="#subText">subText</a></li>
	<li><a href="#text">text</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="new">
	<h5><a href="#new">new</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.choices.builder.new(choiceType) -&gt; builder</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new choice builder instance.</p>
<p>Parameters:</p>
<ul>
<li><code>choice</code>  - The choice instance to configure.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The new choice builder.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Methods</h4>
  <section id="id">
	<h5><a href="#id">id</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.choices.builder:id(value) -&gt; builder</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Sets the ID of the choice.</p>
<p>Parameters:</p>
<ul>
<li><code>value</code>   - The ID.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The choice builder.</li>
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
		<td><code>cp.choices.builder:params(value) -&gt; builder</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Specifies a table of parameter values for the choice. These
values need to be simple - text, numbers, booleans, or tables.</p>
<p>Parameters:</p>
<ul>
<li><code>value</code>   - The table of parameters.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The choice builder, added to the choices set.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="subText">
	<h5><a href="#subText">subText</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.choices.builder:subText(value) -&gt; builder</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Specifies the <code>subText</code> value for the choice being built.</p>
<p>Parameters:</p>
<ul>
<li><code>value</code>   - The subText title for the choice.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The choice builder.</li>
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
		<td><code>cp.choices.builder:text(value) -&gt; builder</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Specifies the text value for the choice being built.</p>
<p>Parameters:</p>
<ul>
<li><code>value</code>   - The text title for the choice.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The choice builder, added to the choices set.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
