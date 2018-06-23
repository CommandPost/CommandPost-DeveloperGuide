# [docs](index.md) » plugins.finalcutpro.timeline.pluginshortcuts
---

Controls for Final Cut Pro's Plugin Shortcuts (for use with Hack Shortcuts).

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
<li>Variables - Configurable values</li>
  <ul>
	<li><a href="#shortcuts">shortcuts</a></li>
  </ul>
<li>Functions - API calls offered directly by the extension</li>
  <ul>
	<li><a href="#applyShortcut">applyShortcut</a></li>
	<li><a href="#assignShortcut">assignShortcut</a></li>
	<li><a href="#getShortcut">getShortcut</a></li>
	<li><a href="#init">init</a></li>
	<li><a href="#setShortcut">setShortcut</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Variables</h4>
  <section id="shortcuts">
	<h5><a href="#shortcuts">shortcuts</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.timeline.pluginshortcuts.shortcuts &lt;cp.prop: table&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Table of shortcuts.</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Functions</h4>
  <section id="applyShortcut">
	<h5><a href="#applyShortcut">applyShortcut</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.timeline.pluginshortcuts.applyShortcut(handlerId, shortcutNumber) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Applies a shortcut.</p>
<p>Parameters:</p>
<ul>
<li><code>handlerId</code>      - The action handler ID.</li>
<li><code>shortcutNumber</code> - The shortcut number, between 1 and 5, which is being assigned.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="assignShortcut">
	<h5><a href="#assignShortcut">assignShortcut</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.timeline.pluginshortcuts.assignShortcut(shortcutNumber, handlerId) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Asks the user to assign the specified video effect shortcut number to a selected effect.
A chooser will be displayed, and the selected item will become the shortcut.</p>
<p>Parameters:</p>
<ul>
<li><code>handlerId</code>      - The action handler ID.</li>
<li><code>shortcutNumber</code> - The shortcut number, between 1 and 5, which is being assigned.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getShortcut">
	<h5><a href="#getShortcut">getShortcut</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.timeline.pluginshortcuts.getShortcut(handlerId, shortcutNumber) -&gt; shortcut</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets a shortcut.</p>
<p>Parameters:</p>
<ul>
<li><code>handlerId</code>      - The action handler ID.</li>
<li><code>shortcutNumber</code> - The shortcut number, between 1 and 5, which is being assigned.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The shortcut</li>
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
		<td><code>plugins.finalcutpro.timeline.pluginshortcuts.init(handlerId, action, shortcutNumber) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Initialise the module.</p>
<p>Parameters:</p>
<ul>
<li><code>deps</code> - Dependancies</li>
</ul>
<p>Returns:</p>
<ul>
<li>The module</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="setShortcut">
	<h5><a href="#setShortcut">setShortcut</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.timeline.pluginshortcuts.setShortcut(handlerId, action, shortcutNumber) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Sets a shortcut.</p>
<p>Parameters:</p>
<ul>
<li><code>handlerId</code>      - The action handler ID.</li>
<li><code>action</code>         - The action.</li>
<li><code>shortcutNumber</code> - The shortcut number, between 1 and 5, which is being assigned.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
