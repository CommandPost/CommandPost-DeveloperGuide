# [docs](index.md) » plugins.core.action.manager
---

Action Manager Module.

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
	<li><a href="#handlerIds">handlerIds</a></li>
	<li><a href="#handlers">handlers</a></li>
  </ul>
<li>Functions - API calls offered directly by the extension</li>
  <ul>
	<li><a href="#addHandler">addHandler</a></li>
	<li><a href="#getActivator">getActivator</a></li>
	<li><a href="#getHandler">getHandler</a></li>
	<li><a href="#getURL">getURL</a></li>
	<li><a href="#init">init</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Constants</h4>
  <section id="handlerIds">
	<h5><a href="#handlerIds">handlerIds</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.action.manager.handlerIds &lt;cp.prop: table of strings; read-only&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a list of registered handler IDs.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="handlers">
	<h5><a href="#handlers">handlers</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.action.manager.handlers &lt;cp.prop: table of handlers; read-only&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Provides access to the set of handlers registered with the manager. It
returns a table with the handler ID's as the key and the handler as the value.
As such, use <code>pairs(...)</code> to loop through them.</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Functions</h4>
  <section id="addHandler">
	<h5><a href="#addHandler">addHandler</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.action.manager.addHandler(id) -&gt; handler</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Adds a new action handler with the specified unique ID and returns it for further configuration.</p>
<p>Parameters:</p>
<ul>
<li><code>id</code>      - The unique ID</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>handler</code> instance.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getActivator">
	<h5><a href="#getActivator">getActivator</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.action.manager.getActivator(id) -&gt; activator</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns an activator with the specified ID. If it doesn't exist, it will be created.
Future calls to get the same ID, and it will return the same instance each time.</p>
<p>Parameters:</p>
<ul>
<li><code>activatorId</code>     - The unique ID of the activator.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The activator with the specified ID.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getHandler">
	<h5><a href="#getHandler">getHandler</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.action.manager.getHandler(id) -&gt; handler</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns an existing handler with the specified ID.</p>
<p>Parameters:</p>
<ul>
<li><code>id</code>          - The unique ID of the action handler.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The action handler, or <code>nil</code></li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getURL">
	<h5><a href="#getURL">getURL</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.action.manager.getURL(handlerId, action) -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets a URL based on the Handler ID &amp; Action Table.</p>
<p>Parameters:</p>
<ul>
<li><code>handlerId</code> - The Handler ID</li>
<li><code>action</code> The action table</li>
</ul>
<p>Returns:</p>
<ul>
<li>A string</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="init">
	<h5><a href="#init">init</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.action.manager.init() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Initialises the module.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
