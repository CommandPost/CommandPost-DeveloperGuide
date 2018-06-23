# [docs](index.md) » plugins.core.tangent.manager.menu
---

Represents a Tangent Menu. Menus are controls that have a fixed set of
non-numerical values. This could be as simple as "On" and "Off", or a long
list of options.

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
	<li><a href="#controls">controls</a></li>
	<li><a href="#get">get</a></li>
	<li><a href="#next">next</a></li>
	<li><a href="#onGet">onGet</a></li>
	<li><a href="#onNext">onNext</a></li>
	<li><a href="#onPrev">onPrev</a></li>
	<li><a href="#parent">parent</a></li>
	<li><a href="#prev">prev</a></li>
	<li><a href="#update">update</a></li>
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
		<td><code>plugins.core.tangent.manager.menu.is(other) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Checks if the <code>other</code> is a <code>menu</code> instance.</p>
<p>Parameters:</p>
<ul>
<li>other     - The other object to test.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if it is a <code>menu</code>, <code>false</code> if not.</li>
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
		<td><code>plugins.core.tangent.manager.menu.new(id[, name[, parent]]) -&gt; menu</code></td>
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
<li>id        - The ID number of the menu.</li>
<li>name      - The name of the menu.</li>
<li>parent    - The parent of the menu.</li>
</ul>
<p>Returns:</p>
<ul>
<li>the new <code>menu</code>.</li>
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
		<td><code>plugins.core.tangent.manager.menu:controls()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the <code>controls</code> the menu belongs to.</p>
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
  <section id="get">
	<h5><a href="#get">get</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.tangent.manager.menu:get() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Executes the <code>get</code> function, if present, returning the string value for the current menu.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>nil</code></li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="next">
	<h5><a href="#next">next</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.tangent.manager.menu:next() -&gt; nil</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Executes the <code>next</code> function, if present.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>nil</code></li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="onGet">
	<h5><a href="#onGet">onGet</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.tangent.manager.menu:onGet(getFn) -&gt; self</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Sets the function that will be called when the Tangent sends a <code>menu string request</code>.
This function should have this signature:</p>
<p><code>function() -&gt; string</code></p>
<p>Parameters:</p>
<ul>
<li>getFn     - The function to call when the Tangent requests the <code>menu string</code>.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>parameter</code> instance.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="onNext">
	<h5><a href="#onNext">onNext</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.tangent.manager.menu:onNext(nextFn) -&gt; self</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Sets the function that will be called when the Tangent sends a <code>menu change +1</code> request.
This function should have this signature:</p>
<p><code>function() -&gt; nil</code></p>
<p>It is suggested that when arriving at the end of the list of options a subsequent <code>next</code> call
will cycle back to the beginning of the options. This is particularly useful for menus with
two options.</p>
<p>Parameters:</p>
<ul>
<li>nextFn     - The function to call when the Tangent requests the <code>menu change +1</code>.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>parameter</code> instance.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="onPrev">
	<h5><a href="#onPrev">onPrev</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.tangent.manager.menu:onPrev(prevFn) -&gt; self</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Sets the function that will be called when the Tangent sends a <code>menu change -1</code> request.
This function should have this signature:</p>
<p><code>function() -&gt; nil</code></p>
<p>It is suggested that when arriving at the start of the list of options a subsequent <code>prev</code> call
will cycle to the end of the options. This is particularly useful for menus with
two options.</p>
<p>Parameters:</p>
<ul>
<li>prevFn     - The function to call when the Tangent requests the <code>menu change -1</code>.</li>
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
		<td><code>plugins.core.tangent.manager.menu:parent() -&gt; group | controls</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the <code>group</code> or <code>controls</code> that contains this menu.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The parent.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="prev">
	<h5><a href="#prev">prev</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.tangent.manager.menu:prev() -&gt; nil</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Executes the <code>prev</code> function, if present.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>nil</code></li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="update">
	<h5><a href="#update">update</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.tangent.manager.menu:update() -&gt; nil</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Updates the Tangent panel with the current value.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the update was sent.</li>
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
		<td><code>plugins.core.tangent.manager.menu:xml() -&gt; cp.web.xml</code></td>
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
