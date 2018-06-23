# [docs](index.md) » cp.commands.command
---

Commands Module.

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
<li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
  <ul>
	<li><a href="#isActive">isActive</a></li>
	<li><a href="#isEnabled">isEnabled</a></li>
  </ul>
<li>Methods - API calls which can only be made on an object returned by a constructor</li>
  <ul>
	<li><a href="#activated">activated</a></li>
	<li><a href="#activatedBy">activatedBy</a></li>
	<li><a href="#addShortcut">addShortcut</a></li>
	<li><a href="#deleteShortcuts">deleteShortcuts</a></li>
	<li><a href="#disable">disable</a></li>
	<li><a href="#enable">enable</a></li>
	<li><a href="#getFirstShortcut">getFirstShortcut</a></li>
	<li><a href="#getGroup">getGroup</a></li>
	<li><a href="#getShortcuts">getShortcuts</a></li>
	<li><a href="#getSubtitle">getSubtitle</a></li>
	<li><a href="#getTitle">getTitle</a></li>
	<li><a href="#groupedBy">groupedBy</a></li>
	<li><a href="#id">id</a></li>
	<li><a href="#new">new</a></li>
	<li><a href="#parent">parent</a></li>
	<li><a href="#pressed">pressed</a></li>
	<li><a href="#released">released</a></li>
	<li><a href="#repeated">repeated</a></li>
	<li><a href="#setShortcuts">setShortcuts</a></li>
	<li><a href="#subtitled">subtitled</a></li>
	<li><a href="#titled">titled</a></li>
	<li><a href="#whenActivated">whenActivated</a></li>
	<li><a href="#whenPressed">whenPressed</a></li>
	<li><a href="#whenReleased">whenReleased</a></li>
	<li><a href="#whenRepeated">whenRepeated</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Fields</h4>
  <section id="isActive">
	<h5><a href="#isActive">isActive</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.commands.command.isActive &lt;cp.prop: boolean; read-only&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Indicates if the command is active. To be active, both the command and the group it belongs to must be enabled.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="isEnabled">
	<h5><a href="#isEnabled">isEnabled</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.commands.command.isEnabled &lt;cp.prop: boolean&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>If set to <code>true</code>, the command is enabled.</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Methods</h4>
  <section id="activated">
	<h5><a href="#activated">activated</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.commands.command:activated(repeats) -&gt; command</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Executes the 'pressed', then 'repeated', then 'released' functions, if present.</p>
<p>Parameters:</p>
<ul>
<li><code>repeats</code>    - the number of times to repeat the 'repeated' function. Defaults to 1.</li>
</ul>
<p>Returns:</p>
<ul>
<li>the last 'truthy' result (non-nil/false).</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="activatedBy">
	<h5><a href="#activatedBy">activatedBy</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.commands.command:activatedBy([modifiers,] [keyCode]) -&gt; command/modifier</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Specifies that the command is activated by pressing a key combination.
This method can be called multiple times, and multiple key combinations will be registered for the command.
To remove existing key combinations, call the <code>command:deleteShortcuts()</code> method.</p>
<ul>
<li>If the <code>keyCode</code> is provided, no modifiers need to be pressed to activate and the <code>command</code> is returned.</li>
<li>If the <code>modifiers</code> and <code>keyCode</code> are provided, the combination is created and the <code>command</code> is returned.</li>
<li>If no <code>keyCode</code> is provided, a <code>modifier</code> is returned, which lets you specify keyboard combinations.</li>
</ul>
<p>For example:</p>

<pre><code>local global        = commands.collection("global")
local pressA        = global:add("commandA"):activatedBy("a")
local pressShiftA   = global:add("commandShiftA"):activatedBy({"shift"}, "a")
local pressCmdA     = global:add("commandCmdA"):activatedBy():command("a")
local pressOptCmdA  = global:add("commandOptCmdA"):activatedBy():option():command("a")
global:enable()</code></pre>
<p>Parameters:</p>
<ul>
<li><code>modifiers</code>  - (optional) The table containing names of required modifiers.</li>
<li><code>keyCode</code>    - (optional) The key code that will activate the command, with no modifiers.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>command</code> if a <code>keyCode</code> was provided, or <code>modifier</code> if not.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="addShortcut">
	<h5><a href="#addShortcut">addShortcut</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.commands.command:addShortcut(newShortcut) -&gt; command</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Adds the specified shortcut to the command.
If the command is enabled, the shortcut will also be enabled.</p>
<p>Parameters:</p>
<ul>
<li><code>newShortcut</code>    - the shortcut to add.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>self</code></li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="deleteShortcuts">
	<h5><a href="#deleteShortcuts">deleteShortcuts</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.commands.command:deleteShortcuts() -&gt; command</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Sets the function that will be called when the command key combo is pressed.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>command - The current command</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="disable">
	<h5><a href="#disable">disable</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.commands.command:disable() -&gt; cp.commands.command</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Disables the command.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.commands.command</code> instance.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="enable">
	<h5><a href="#enable">enable</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.commands.command:enable() -&gt; cp.commands.command</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Enables the command.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.commands.command</code> instance.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getFirstShortcut">
	<h5><a href="#getFirstShortcut">getFirstShortcut</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.commands.command:getFirstShortcut() -&gt; command</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the first shortcut, or <code>nil</code> if none have been registered.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The first shortcut, or <code>nil</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getGroup">
	<h5><a href="#getGroup">getGroup</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.commands.command:getGroup() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the group ID for the command.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The group ID.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getShortcuts">
	<h5><a href="#getShortcuts">getShortcuts</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.commands.command:getShortcuts() -&gt; command</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the set of shortcuts assigned to this command.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The associated shortcuts.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getSubtitle">
	<h5><a href="#getSubtitle">getSubtitle</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.commands.command:getSubtitle() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the current subtitle, based on either the set subtitle, or the "<ID>_subtitle" value in the I18N files.
If nothing is available, it will return <code>nil</code>.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The subtitle value or <code>nil</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getTitle">
	<h5><a href="#getTitle">getTitle</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.commands.command:getTitle() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the command title in the current language, if availalbe. If not, the ID is returned.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns</p>
<ul>
<li>The human-readable command title.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="groupedBy">
	<h5><a href="#groupedBy">groupedBy</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.commands.command:groupedBy(group) -&gt; cp.commands.command</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Specifies that the command is grouped by a specific value.
Note: This is different to the command group/parent value.</p>
<p>Parameters:</p>
<ul>
<li><code>group</code>   - The group ID.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.commands.command</code> instance.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="id">
	<h5><a href="#id">id</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.commands.command:id() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the ID for this command.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The ID.</li>
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
		<td><code>cp.commands.command.new() -&gt; command</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new command, which can have keyboard shortcuts assigned to it.</p>
<p>Parameters:</p>
<ul>
<li><code>id</code>     - the unique identifier for the command. E.g. 'cpCustomCommand'</li>
<li><code>parent</code> - The parent group.</li>
</ul>
<p>Returns:</p>
<ul>
<li>command - The command that was created.</li>
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
		<td><code>cp.commands.command:parent() -&gt; cp.commands</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the parent command group.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns</p>
<ul>
<li>The parent <code>cp.commands</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="pressed">
	<h5><a href="#pressed">pressed</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.commands.command:pressed() -&gt; command</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Executes the 'pressed' function, if present.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>the result of the function, or <code>nil</code> if none is present.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="released">
	<h5><a href="#released">released</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.commands.command:released() -&gt; command</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Executes the 'released' function, if present.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>the result of the function, or <code>nil</code> if none is present.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="repeated">
	<h5><a href="#repeated">repeated</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.commands.command:repeated(repeats) -&gt; command</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Executes the 'repeated' function, if present.</p>
<p>Parameters:</p>
<ul>
<li><code>repeats</code>    - the number of times to repeat. Defaults to 1.</li>
</ul>
<p>Returns:</p>
<ul>
<li>the last result.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="setShortcuts">
	<h5><a href="#setShortcuts">setShortcuts</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.commands.command:setShortcuts(shortcuts) -&gt; command</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Deletes any existing shortcuts and applies the new set of shortcuts in the table.</p>
<p>Parameters:</p>
<ul>
<li>shortcuts     - The set of <code>cp.commands.shortcuts</code> to apply to this command.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.commands.command</code> instance.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="subtitled">
	<h5><a href="#subtitled">subtitled</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.commands.command:subtitled(subtitle) -&gt; cp.commands.command</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Sets the specified subtitle and returns the <code>cp.commands.command</code> instance.</p>
<p>Note: By default, it will look up the <code>&lt;ID&gt;_subtitle</code> value.
Anything set here will override it in all langauges.</p>
<p>Parameters:</p>
<ul>
<li><code>subtitle</code>    - The new subtitle.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="titled">
	<h5><a href="#titled">titled</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.commands.command:titled(title) -&gt; command</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Applies the provided human-readable title to the command.</p>
<p>Parameters:</p>
<ul>
<li><code>id</code> = the unique identifier for the command. E.g. 'FCPXHacksCustomCommand'</li>
</ul>
<p>Returns:</p>
<ul>
<li>command - The command that was created.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="whenActivated">
	<h5><a href="#whenActivated">whenActivated</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.commands.command:whenActivated(activatedFn) -&gt; command</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Sets the function that will be called when the command is activated.</p>
<p>NOTE: This is a shortcut for calling <code>whenPressed(...)</code></p>
<p>Parameters:</p>
<ul>
<li><code>activatedFn</code>    - the function to call when activated.</li>
</ul>
<p>Returns:</p>
<ul>
<li>command - The current command</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="whenPressed">
	<h5><a href="#whenPressed">whenPressed</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.commands.command:whenPressed(pressedFn) -&gt; command</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Sets the function that will be called when the command key combo is pressed.</p>
<p>Parameters:</p>
<ul>
<li><code>pressedFn</code>  - the function to call when pressed.</li>
</ul>
<p>Returns:</p>
<ul>
<li>command - The current command</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="whenReleased">
	<h5><a href="#whenReleased">whenReleased</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.commands.command:whenReleased(releasedFn) -&gt; command</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Sets the function that will be called when the command key combo is released.</p>
<p>Parameters:</p>
<ul>
<li><code>releasedFn</code> - the function to call when released.</li>
</ul>
<p>Returns:</p>
<ul>
<li>command - The current command</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="whenRepeated">
	<h5><a href="#whenRepeated">whenRepeated</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.commands.command:whenRepeated(repeatedFn) -&gt; command</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Sets the function that will be called when the command key combo is repeated.</p>
<p>Parameters:</p>
<ul>
<li><code>repeatedFn</code> - the function to call when repeated.</li>
</ul>
<p>Returns:</p>
<ul>
<li>command - The current command</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
