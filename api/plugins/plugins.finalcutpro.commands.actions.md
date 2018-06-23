# [docs](index.md) » plugins.finalcutpro.commands.actions
---

An `action` which will execute a command with matching group/id values.
Registers itself with the `core.action.manager`.

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
	<li><a href="#execute">execute</a></li>
	<li><a href="#getId">getId</a></li>
	<li><a href="#getId">getId</a></li>
	<li><a href="#init">init</a></li>
	<li><a href="#onChoices">onChoices</a></li>
	<li><a href="#onExecute">onExecute</a></li>
	<li><a href="#reset">reset</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="execute">
	<h5><a href="#execute">execute</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.commands.actions.execute(action) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Executes the action with the provided parameters.</p>
<p>Parameters:</p>
<ul>
<li><p><code>action</code>  - A table representing the action, matching the following:</p>
<ul>
<li><code>id</code>      - The specific Command ID within the group.</li>
</ul>
</li>
<li><p><code>true</code> if the action was executed successfully.</p>
</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getId">
	<h5><a href="#getId">getId</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.commands.actions.getId(action) -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Get ID.</p>
<p>Parameters:</p>
<ul>
<li>action - The action table.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The ID as a string.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getId">
	<h5><a href="#getId">getId</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.commands.actionss.getId(action) -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets the ID from an action.</p>
<p>Parameters:</p>
<ul>
<li>action - The action table.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The ID as a string.</li>
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
		<td><code>plugins.finalcutpro.commands.actions.init(actionmanager, cmds) -&gt; none</code></td>
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
<li>actionmanager - The action manager object</li>
<li>cmds - Final Cut Pro commands manager</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="onChoices">
	<h5><a href="#onChoices">onChoices</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.commands.actions.onChoices([choices]) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Adds available choices to the selection.</p>
<p>Parameters:</p>
<ul>
<li><code>choices</code> - The optional <code>cp.choices</code> to add choices to.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="onExecute">
	<h5><a href="#onExecute">onExecute</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.commands.actions.onExecute(action) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>On Execute.</p>
<p>Parameters:</p>
<ul>
<li>action - The action table.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
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
		<td><code>plugins.finalcutpro.commands.actions.reset() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Reset the Font Handler Cache.</p>
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
