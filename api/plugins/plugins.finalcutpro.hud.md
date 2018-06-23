# [docs](index.md) » plugins.finalcutpro.hud
---

Final Cut Pro HUD.

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
	<li><a href="#position">position</a></li>
  </ul>
<li>Functions - API calls offered directly by the extension</li>
  <ul>
	<li><a href="#assignButton">assignButton</a></li>
	<li><a href="#choices">choices</a></li>
	<li><a href="#delete">delete</a></li>
	<li><a href="#generateHTML">generateHTML</a></li>
	<li><a href="#getButton">getButton</a></li>
	<li><a href="#getButtonCommand">getButtonCommand</a></li>
	<li><a href="#getButtonText">getButtonText</a></li>
	<li><a href="#getButtonURL">getButtonURL</a></li>
	<li><a href="#hide">hide</a></li>
	<li><a href="#init">init</a></li>
	<li><a href="#javaScriptCallback">javaScriptCallback</a></li>
	<li><a href="#new">new</a></li>
	<li><a href="#refresh">refresh</a></li>
	<li><a href="#setButton">setButton</a></li>
	<li><a href="#show">show</a></li>
	<li><a href="#update">update</a></li>
	<li><a href="#updateVisibility">updateVisibility</a></li>
	<li><a href="#visible">visible</a></li>
  </ul>
<li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
  <ul>
	<li><a href="#buttonsShown">buttonsShown</a></li>
	<li><a href="#dropTargetsShown">dropTargetsShown</a></li>
	<li><a href="#enabled">enabled</a></li>
	<li><a href="#inspectorShown">inspectorShown</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Constants</h4>
  <section id="position">
	<h5><a href="#position">position</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.hud.position &lt;cp.prop: table&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the last HUD frame saved in settings.</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Functions</h4>
  <section id="assignButton">
	<h5><a href="#assignButton">assignButton</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.hud.assignButton() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Assigns a HUD button.</p>
<p>Parameters:</p>
<ul>
<li>button - which button you want to assign.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="choices">
	<h5><a href="#choices">choices</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.hud.choices() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Choices for the Assign HUD Button chooser.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>Table</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="delete">
	<h5><a href="#delete">delete</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.hud.delete()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Deletes the existing HUD if it exists</p>
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
  <section id="generateHTML">
	<h5><a href="#generateHTML">generateHTML</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.hud.generateHTML() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Generate the HTML for the HUD.</p>
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
  <section id="getButton">
	<h5><a href="#getButton">getButton</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.hud.getButton() -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets the button values from settings.</p>
<p>Parameters:</p>
<ul>
<li>index - Index of the Button</li>
<li>defaultValue - Default Value of the Button</li>
</ul>
<p>Returns:</p>
<ul>
<li>Button value</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getButtonCommand">
	<h5><a href="#getButtonCommand">getButtonCommand</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.hud.getButtonCommand() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets the button command.</p>
<p>Parameters:</p>
<ul>
<li>index - Index of the Button</li>
</ul>
<p>Returns:</p>
<ul>
<li>Button Command</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getButtonText">
	<h5><a href="#getButtonText">getButtonText</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.hud.getButtonText() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets the button text.</p>
<p>Parameters:</p>
<ul>
<li>index - Index of the Button</li>
</ul>
<p>Returns:</p>
<ul>
<li>Button Label or Unassigned Value</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getButtonURL">
	<h5><a href="#getButtonURL">getButtonURL</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.hud.getButtonURL() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets the button URL.</p>
<p>Parameters:</p>
<ul>
<li>index - Index of the Button</li>
</ul>
<p>Returns:</p>
<ul>
<li>Button URL</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="hide">
	<h5><a href="#hide">hide</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.hud.hide() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Hide the HUD.</p>
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
		<td><code>plugins.finalcutpro.hud.init() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Initialise HUD Module.</p>
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
  <section id="javaScriptCallback">
	<h5><a href="#javaScriptCallback">javaScriptCallback</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.hud.javaScriptCallback() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Javascript Callback</p>
<p>Parameters:</p>
<ul>
<li>message - the message for the callback</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="new">
	<h5><a href="#new">new</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.hud.new()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new HUD</p>
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
  <section id="refresh">
	<h5><a href="#refresh">refresh</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.hud.refresh() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Refresh the HUD's content.</p>
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
  <section id="setButton">
	<h5><a href="#setButton">setButton</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.hud.setButton() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Sets the button.</p>
<p>Parameters:</p>
<ul>
<li>index - Index of the Button</li>
<li>value - Value you want to set the button to.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="show">
	<h5><a href="#show">show</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.hud.show() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Show the HUD.</p>
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
  <section id="update">
	<h5><a href="#update">update</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.hud.update() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Enables or Disables the HUD.</p>
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
  <section id="updateVisibility">
	<h5><a href="#updateVisibility">updateVisibility</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.hud.updateVisibility() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Update the visibility of the HUD.</p>
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
  <section id="visible">
	<h5><a href="#visible">visible</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.hud.visible() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Is the HUD visible?</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> or <code>false</code></li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Fields</h4>
  <section id="buttonsShown">
	<h5><a href="#buttonsShown">buttonsShown</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.hud.buttonsShown &lt;cp.prop: boolean&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Should Buttons in the HUD be shown?</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="dropTargetsShown">
	<h5><a href="#dropTargetsShown">dropTargetsShown</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.hud.dropTargetsShown &lt;cp.prop: boolean&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Should Drop Targets in the HUD be enabled?</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="enabled">
	<h5><a href="#enabled">enabled</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.hud.enabled &lt;cp.prop: boolean&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Is the HUD enabled in the settings?</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="inspectorShown">
	<h5><a href="#inspectorShown">inspectorShown</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.hud.inspectorShown &lt;cp.prop: boolean&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Should the Inspector in the HUD be shown?</p>
</td>
	  </tr>
	</table>
  </section>
