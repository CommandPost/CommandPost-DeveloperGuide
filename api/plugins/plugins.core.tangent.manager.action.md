# [docs](index.md) » plugins.core.tangent.manager.action
---

Represents a Tangent Action

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
	<li><a href="#controls">controls</a></li>
	<li><a href="#is">is</a></li>
	<li><a href="#onPress">onPress</a></li>
	<li><a href="#onRelease">onRelease</a></li>
	<li><a href="#parent">parent</a></li>
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
		<td><code>plugins.core.tangent.manager.action.new(id[, name]) -&gt; action</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constructor</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new <code>Action</code> instance.</p>
<p>Parameters:</p>
<ul>
<li>id        - The ID number of the action.</li>
<li>name      - The name of the action.</li>
</ul>
<p>Returns:</p>
<ul>
<li>the new <code>action</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Methods</h4>
  <section id="controls">
	<h5><a href="#controls">controls</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.tangent.manager.action:controls()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the <code>controls</code> the action belongs to.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>controls</code>, or <code>nil</code> if not specified.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="is">
	<h5><a href="#is">is</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.tangent.manager.action.is() -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Is an object an action?</p>
<p>Parameters:</p>
<ul>
<li>otherThing - Object to test.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the object is an action otherwise <code>false</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="onPress">
	<h5><a href="#onPress">onPress</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.tangent.manager.action:onPress(pressFn) -&gt; self</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Sets the function that will be called when the Tangent sends a 'action on' request.
This function should have this signature:</p>
<p><code>function() -&gt; nil</code></p>
<p>Parameters:</p>
<ul>
<li>pressFn     - The function to call when the Tangent requests the action on.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>parameter</code> instance.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="onRelease">
	<h5><a href="#onRelease">onRelease</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.tangent.manager.action:onRelease(releaseFn) -&gt; self</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Sets the function that will be called when the Tangent sends a 'action off' request.
This function should have this signature:</p>
<p><code>function() -&gt; nil</code></p>
<p>Parameters:</p>
<ul>
<li>releaseFn     - The function to call when the Tangent requests the action off.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>parameter</code> instance.</li>
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
		<td><code>plugins.core.tangent.manager.action:parent() -&gt; group | controls</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the <code>group</code> or <code>controls</code> that contains this action.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The action's parent.</li>
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
		<td><code>plugins.core.tangent.manager.action:xml() -&gt; cp.web.xml</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the <code>xml</code> configuration for the Action.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>xml</code> for the Action.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
