# [docs](index.md) » plugins.core.preferences.panels.shortcuts
---

Shortcuts Preferences Panel

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
	<li><a href="#DEFAULT_SHORTCUTS">DEFAULT_SHORTCUTS</a></li>
  </ul>
<li>Functions - API calls offered directly by the extension</li>
  <ul>
	<li><a href="#getGroupEditor">getGroupEditor</a></li>
	<li><a href="#init">init</a></li>
	<li><a href="#setGroupEditor">setGroupEditor</a></li>
  </ul>
<li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
  <ul>
	<li><a href="#lastGroup">lastGroup</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Constants</h4>
  <section id="DEFAULT_SHORTCUTS">
	<h5><a href="#DEFAULT_SHORTCUTS">DEFAULT_SHORTCUTS</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.preferences.panels.shortcuts.DEFAULT_SHORTCUTS -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Default Shortcuts File Name</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Functions</h4>
  <section id="getGroupEditor">
	<h5><a href="#getGroupEditor">getGroupEditor</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.preferences.panels.shortcuts.getGroupEditor(groupId) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets the Group Editor</p>
<p>Parameters:</p>
<ul>
<li>groupId - Group ID</li>
</ul>
<p>Returns:</p>
<ul>
<li>Group Editor</li>
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
		<td><code>plugins.core.preferences.panels.shortcuts.init(deps, env) -&gt; module</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Initialise the Module.</p>
<p>Parameters:</p>
<ul>
<li>deps - Dependancies Table</li>
<li>env - Environment Table</li>
</ul>
<p>Returns:</p>
<ul>
<li>The Module</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="setGroupEditor">
	<h5><a href="#setGroupEditor">setGroupEditor</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.preferences.panels.shortcuts.setGroupEditor(groupId, editorFn) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Sets the Group Editor</p>
<p>Parameters:</p>
<ul>
<li>groupId - Group ID</li>
<li>editorFn - Editor Function</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Fields</h4>
  <section id="lastGroup">
	<h5><a href="#lastGroup">lastGroup</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.preferences.panels.shortcuts.lastGroup &lt;cp.prop: string&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Last group used in the Preferences Drop Down.</p>
</td>
	  </tr>
	</table>
  </section>
