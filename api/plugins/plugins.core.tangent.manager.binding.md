# [docs](index.md) » plugins.core.tangent.manager.binding
---

Represents a Tangent Binding

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
<li>Constructors - API calls which return an object, typically one that offers API methods</li>
  <ul>
	<li><a href="#new">new</a></li>
  </ul>
<li>Methods - API calls which can only be made on an object returned by a constructor</li>
  <ul>
	<li><a href="#member">member</a></li>
	<li><a href="#members">members</a></li>
	<li><a href="#xml">xml</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Constructors</h4>
  <section id="new">
	<h5><a href="#new">new</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.tangent.manager.binding.new(id[, name]) -&gt; binding</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constructor</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new <code>Binding</code> instance.</p>
<p>Parameters:</p>
<ul>
<li>id        - The ID number of the binding.</li>
<li>name      - The name of the binding.</li>
</ul>
<p>Returns:</p>
<ul>
<li>the new <code>binding</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Methods</h4>
  <section id="member">
	<h5><a href="#member">member</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.tangent.manager.binding:member(parameter) -&gt; self</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Adds a <code>parameter</code> as a member of the Binding group. The order is significant</p>
<ul>
<li>it will determine the order the parameters are applied to group controls in the Mapper.</li>
</ul>
<p>Parameters:</p>
<ul>
<li>param     - The <code>parameter</code> to add to the binding.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>binding</code> instance.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="members">
	<h5><a href="#members">members</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.tangent.manager.binding:members(...) -&gt; self</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Adds the list of parameters to this binding.</p>
<p>Parameters:</p>
<ul>
<li>...   - the list of parameters to bind.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>binding</code> instance.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="xml">
	<h5><a href="#xml">xml</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.tangent.manager.binding:xml() -&gt; cp.web.xml</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the <code>xml</code> configuration for the Binding.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>xml</code> for the Binding.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
