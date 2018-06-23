# [docs](index.md) » cp.apple.commandeditor
---

Functions to control and manage Apple's Command Editor - used in Final Cut Pro,
Motion and Compressor.

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
	<li><a href="#padKeys">padKeys</a></li>
  </ul>
<li>Functions - API calls offered directly by the extension</li>
  <ul>
	<li><a href="#characterStringToKeyCode">characterStringToKeyCode</a></li>
	<li><a href="#keypadCharacterToKeyCode">keypadCharacterToKeyCode</a></li>
	<li><a href="#modifierMaskToModifiers">modifierMaskToModifiers</a></li>
	<li><a href="#modifierMatch">modifierMatch</a></li>
	<li><a href="#shortcutsFromCommandSet">shortcutsFromCommandSet</a></li>
	<li><a href="#translateModifiers">translateModifiers</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Variables</h4>
  <section id="padKeys">
	<h5><a href="#padKeys">padKeys</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.commandeditor.padKeys -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Table of Pad Keys</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Functions</h4>
  <section id="characterStringToKeyCode">
	<h5><a href="#characterStringToKeyCode">characterStringToKeyCode</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.commandeditor.characterStringToKeyCode() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Translate Keyboard Character Strings from Command Set Format into Hammerspoon Format.</p>
<p>Parameters:</p>
<ul>
<li>input - Character String</li>
</ul>
<p>Returns:</p>
<ul>
<li>Keycode as String or ""</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="keypadCharacterToKeyCode">
	<h5><a href="#keypadCharacterToKeyCode">keypadCharacterToKeyCode</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.commandeditor.keypadCharacterToKeyCode() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Translate Keyboard Keypad Character Strings from Command Set Format into Hammerspoon Format.</p>
<p>Parameters:</p>
<ul>
<li>input - Character String</li>
</ul>
<p>Returns:</p>
<ul>
<li>string or nil</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="modifierMaskToModifiers">
	<h5><a href="#modifierMaskToModifiers">modifierMaskToModifiers</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.commandeditor.modifierMaskToModifiers() -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Translate Keyboard Modifiers from Apple's Property List Format into Hammerspoon Format.</p>
<p>Parameters:</p>
<ul>
<li>value - Modifiers String</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table of modifier strings.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="modifierMatch">
	<h5><a href="#modifierMatch">modifierMatch</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.commandeditor.modifierMatch(inputA, inputB) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Compares two modifier tables.</p>
<p>Parameters:</p>
<ul>
<li>inputA - table of modifiers</li>
<li>inputB - table of modifiers</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if there's a match otherwise <code>false</code></li>
</ul>
<p>Notes:</p>
<ul>
<li>This function only takes into account 'ctrl', 'alt', 'cmd', 'shift'.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="shortcutsFromCommandSet">
	<h5><a href="#shortcutsFromCommandSet">shortcutsFromCommandSet</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.commandeditor.shortcutsFromCommandSet(id, commandSet) -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets a specific command from a specified Command Set and returns a table of Shortcuts.</p>
<p>Parameters:</p>
<ul>
<li>id - The ID of the command you want to get.</li>
<li>commandSet - A table containing an entire Command Set.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table of shortcuts for a specific command.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="translateModifiers">
	<h5><a href="#translateModifiers">translateModifiers</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.commandeditor.translateModifiers() -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Translate Keyboard Modifiers from Command Set Format into Hammerspoon Format.</p>
<p>Parameters:</p>
<ul>
<li>input - Modifiers String</li>
</ul>
<p>Returns:</p>
<ul>
<li>table</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
