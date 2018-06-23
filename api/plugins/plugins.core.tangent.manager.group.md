# [docs](index.md) » plugins.core.tangent.manager.group
---

Represents a Tangent Group. Groups can also be used to enable/disable multiple
Parameters/Actions/Menus by enabling/disabling the containing group.

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
	<li><a href="#is">is</a></li>
  </ul>
<li>Constructors - API calls which return an object, typically one that offers API methods</li>
  <ul>
	<li><a href="#new">new</a></li>
  </ul>
<li>Methods - API calls which can only be made on an object returned by a constructor</li>
  <ul>
	<li><a href="#action">action</a></li>
	<li><a href="#binding">binding</a></li>
	<li><a href="#controls">controls</a></li>
	<li><a href="#group">group</a></li>
	<li><a href="#menu">menu</a></li>
	<li><a href="#parameter">parameter</a></li>
	<li><a href="#parent">parent</a></li>
	<li><a href="#reset">reset</a></li>
	<li><a href="#xml">xml</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="is">
	<h5><a href="#is">is</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.tangent.manager.group.is(otherThing) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Checks if the <code>otherThing</code> is a <code>group</code>.</p>
<p>Parameters:</p>
<ul>
<li>otherThing    - The thing to check.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if it is a <code>group</code>, <code>false</code> otherwise.</li>
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
		<td><code>plugins.core.tangent.manager.group.new(name, parent, controls)</code></td>
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
<li>name      - The name of the group.</li>
<li>parent    - The parent group.</li>
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
		<td><code>plugins.core.tangent.manager.group:action(id[, name]) -&gt; action</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Adds an <code>action</code> to this group.</p>
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
  <section id="binding">
	<h5><a href="#binding">binding</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.tangent.manager.group:binding(id[, name]) -&gt; binding</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Adds an <code>binding</code> to this group.</p>
<p>Parameters</p>
<ul>
<li>id    - The ID number of the new binding</li>
<li>name  - The name of the binding.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The new <code>binding</code></li>
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
		<td><code>plugins.core.tangent.manager.group:controls() -&gt; controls</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Retrieves the <code>controls</code> for this group. May be <code>nil</code> if the group was created independently.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>controls</code>, or <code>nil</code>.</li>
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
		<td><code>plugins.core.tangent.manager.group:group(name) -&gt; group</code></td>
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
		<td><code>plugins.core.tangent.manager.group:menu(id[, name]) -&gt; menu</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Adds an <code>menu</code> to this group.</p>
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
		<td><code>plugins.core.tangent.manager.group:parameter(id[, name]) -&gt; parameter</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Adds an <code>parameter</code> to this group.</p>
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
		<td><code>plugins.core.tangent.manager.group:parent() -&gt; group | controls</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the parent of the group, which should be either a <code>group</code>, <code>controls</code> or <code>nil</code>.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The group's parents.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="reset">
	<h5><a href="#reset">reset</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.tangent.manager.group:reset() -&gt; self</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>This will remove all parameters, actions, menus and bindings from
the group. It does not remove sub-groups. Use with care!</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>group</code> instance.</li>
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
		<td><code>plugins.core.tangent.manager.group:xml() -&gt; cp.web.xml</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the <code>xml</code> configuration for the Group, sorted alphabetically.</p>
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
