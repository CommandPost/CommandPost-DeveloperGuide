# [docs](index.md) » plugins.core.accessibility
---

Accessibility Plugin.

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
	<li><a href="#enabled">enabled</a></li>
  </ul>
<li>Variables - Configurable values</li>
  <ul>
	<li><a href="#systemPreferencesAlreadyOpen">systemPreferencesAlreadyOpen</a></li>
  </ul>
<li>Functions - API calls offered directly by the extension</li>
  <ul>
	<li><a href="#completeSetupPanel">completeSetupPanel</a></li>
	<li><a href="#init">init</a></li>
	<li><a href="#showSetupPanel">showSetupPanel</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Constants</h4>
  <section id="enabled">
	<h5><a href="#enabled">enabled</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.accessibility.enabled &lt;cp.prop: boolean; read-only&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Is <code>true</code> if Accessibility permissions have been enabled for CommandPost.
Plugins interested in being notfied about accessibility status should
<code>watch</code> this property.</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Variables</h4>
  <section id="systemPreferencesAlreadyOpen">
	<h5><a href="#systemPreferencesAlreadyOpen">systemPreferencesAlreadyOpen</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.accessibility.systemPreferencesAlreadyOpen</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Was System Preferences already open?</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Functions</h4>
  <section id="completeSetupPanel">
	<h5><a href="#completeSetupPanel">completeSetupPanel</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.accessibility.completeSetupPanel() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Called when the setup panel for accessibility was shown and is ready to complete.</p>
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
  <section id="init">
	<h5><a href="#init">init</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.accessibility.init(setup) -&gt; table</code></td>
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
<li>setup - Dependancies setup</li>
</ul>
<p>Returns:</p>
<ul>
<li>The module as a table</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="showSetupPanel">
	<h5><a href="#showSetupPanel">showSetupPanel</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.accessibility.showSetupPanel() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Called when the Setup Panel should be shown to prompt the user about enabling Accessbility.</p>
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
