# [docs](index.md) » plugins.core.tangent.manager.controls
---

Represents a Tangent Group

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
	<li><a href="#controls">controls</a></li>
  </ul>
<li>Constructors - API calls which return an object, typically one that offers API methods</li>
  <ul>
	<li><a href="#new">new</a></li>
  </ul>
<li>Methods - API calls which can only be made on an object returned by a constructor</li>
  <ul>
	<li><a href="#action">action</a></li>
	<li><a href="#controls">controls</a></li>
	<li><a href="#findByID">findByID</a></li>
	<li><a href="#group">group</a></li>
	<li><a href="#menu">menu</a></li>
	<li><a href="#parameter">parameter</a></li>
	<li><a href="#parent">parent</a></li>
	<li><a href="#register">register</a></li>
	<li><a href="#unregister">unregister</a></li>
	<li><a href="#xml">xml</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Constants</h4>
  <section id="controls">
	<h5><a href="#controls">controls</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.tangent.manager.controls</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The set of controls currently registered.</p>
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
		<td><code>plugins.core.tangent.manager.controls.new(id, name)</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constructor</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new <code>Group</code> instance.</p>
<p>Parameters:</p>
<ul>
<li>name      - The name of the controls.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Methods</h4>
  <section id="action">
	<h5><a href="#action">action</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.tangent.manager.controls:action(id[, name]) -&gt; action</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Adds an <code>action</code> to this controls.</p>
<p>Parameters</p>
<ul>
<li>id    - The ID number of the new action</li>
<li>name  - The name of the action.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The new <code>action</code></li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="controls">
	<h5><a href="#controls">controls</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.tangent.manager.controls:controls() -&gt; controls</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns this <code>controls</code> instance.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The `controls instance.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="findByID">
	<h5><a href="#findByID">findByID</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.tangent.manager.controls:findByID(id) -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Finds a control (Action/Parameter/Mode) by its unique ID.</p>
<p>Parameters:</p>
<ul>
<li>id        - the ID to search by</li>
</ul>
<p>Returns:</p>
<ul>
<li>The control, or <code>nil</code> if not found.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="group">
	<h5><a href="#group">group</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.tangent.manager.controls:group(name) -&gt; group</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Adds a subgroup to this group.</p>
<p>Parameters</p>
<ul>
<li>name  - the name of the new sub-group</li>
</ul>
<p>Returns:</p>
<ul>
<li>The new <code>group</code></li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="menu">
	<h5><a href="#menu">menu</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.tangent.manager.controls:menu(id[, name]) -&gt; menu</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Adds an <code>menu</code> to this controls.</p>
<p>Parameters</p>
<ul>
<li>id    - The ID number of the new menu</li>
<li>name  - The name of the menu.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The new <code>menu</code></li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="parameter">
	<h5><a href="#parameter">parameter</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.tangent.manager.controls:parameter(id[, name]) -&gt; parameter</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Adds an <code>parameter</code> to this controls.</p>
<p>Parameters</p>
<ul>
<li>id    - The ID number of the new parameter</li>
<li>name  - The name of the parameter.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The new <code>parameter</code></li>
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
		<td><code>plugins.core.tangent.manager.controls:parent() -&gt; nil</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Always returns <code>nil</code>, sinces <code>controls</code> have no parent.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>nil</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="register">
	<h5><a href="#register">register</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.tangent.manager.controls:register(control) -&gt; self</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Registers a control (Action/Parameter/Menu) with it's ID
This allows efficient retrieval via the <code>findById(...)</code> method, as well
as checking that ID is unique.</p>
<p>Parameters:</p>
<ul>
<li>control       - The Action/Parameter/Menu to register</li>
</ul>
<p>Returns:</p>
<ul>
<li>self</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="unregister">
	<h5><a href="#unregister">unregister</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.tangent.manager.controls:unregister(control) -&gt; self</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Unregisters a control (Action/Parameter/Menu) with it's ID</p>
<p>Parameters:</p>
<ul>
<li>control       - The Action/Parameter/Menu to unregister</li>
</ul>
<p>Returns:</p>
<ul>
<li>self</li>
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
		<td><code>plugins.core.tangent.manager.controls:xml() -&gt; cp.web.xml</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the <code>xml</code> configuration for the Group.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>xml</code> for the Group.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
