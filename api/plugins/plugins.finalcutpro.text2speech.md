# [docs](index.md) » plugins.finalcutpro.text2speech
---

Text to Speech Plugin.

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
	<li><a href="#copyToMediaFolder">copyToMediaFolder</a></li>
	<li><a href="#DELETE_DELAY">DELETE_DELAY</a></li>
  </ul>
<li>Variables - Configurable values</li>
  <ul>
	<li><a href="#addTextToNotesFieldAfterImport">addTextToNotesFieldAfterImport</a></li>
	<li><a href="#createRoleForVoice">createRoleForVoice</a></li>
	<li><a href="#currentIncrementalNumber">currentIncrementalNumber</a></li>
	<li><a href="#customPrefix">customPrefix</a></li>
	<li><a href="#deleteFileAfterImport">deleteFileAfterImport</a></li>
	<li><a href="#enableCustomPrefix">enableCustomPrefix</a></li>
	<li><a href="#includeTextInFilename">includeTextInFilename</a></li>
	<li><a href="#insertIntoTimeline">insertIntoTimeline</a></li>
	<li><a href="#path">path</a></li>
	<li><a href="#recentText">recentText</a></li>
	<li><a href="#replaceSpaceWithUnderscore">replaceSpaceWithUnderscore</a></li>
	<li><a href="#tag">tag</a></li>
	<li><a href="#useUnderscore">useUnderscore</a></li>
	<li><a href="#voice">voice</a></li>
  </ul>
<li>Functions - API calls offered directly by the extension</li>
  <ul>
	<li><a href="#chooseFolder">chooseFolder</a></li>
	<li><a href="#insertFromPasteboard">insertFromPasteboard</a></li>
	<li><a href="#show">show</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Constants</h4>
  <section id="copyToMediaFolder">
	<h5><a href="#copyToMediaFolder">copyToMediaFolder</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.text2speech.copyToMediaFolder &lt;cp.prop: boolean; live&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Copy to Media Folder Preferences Key.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="DELETE_DELAY">
	<h5><a href="#DELETE_DELAY">DELETE_DELAY</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.text2speech.DELETE_DELAY</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>How long before a file is deleted in seconds.</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Variables</h4>
  <section id="addTextToNotesFieldAfterImport">
	<h5><a href="#addTextToNotesFieldAfterImport">addTextToNotesFieldAfterImport</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.text2speech.addTextToNotesFieldAfterImport</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Option to Add Text to Notes Field After Importing</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="createRoleForVoice">
	<h5><a href="#createRoleForVoice">createRoleForVoice</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.text2speech.createRoleForVoice</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Boolean that sets whether or not a tag should be added for the voice.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="currentIncrementalNumber">
	<h5><a href="#currentIncrementalNumber">currentIncrementalNumber</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.text2speech.currentIncrementalNumber</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Current Incremental Number as number</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="customPrefix">
	<h5><a href="#customPrefix">customPrefix</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.text2speech.customPrefix</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>String which contains the custom prefix.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="deleteFileAfterImport">
	<h5><a href="#deleteFileAfterImport">deleteFileAfterImport</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.text2speech.deleteFileAfterImport</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Delete File After Import</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="enableCustomPrefix">
	<h5><a href="#enableCustomPrefix">enableCustomPrefix</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.text2speech.enableCustomPrefix</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Boolean that sets whether or not a custom prefix for the generated filename is enabled.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="includeTextInFilename">
	<h5><a href="#includeTextInFilename">includeTextInFilename</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.text2speech.includeTextInFilename</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Includes the entered text in the filename</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="insertIntoTimeline">
	<h5><a href="#insertIntoTimeline">insertIntoTimeline</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.text2speech.insertIntoTimeline</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Boolean that sets whether or not new generated voice file are automatically added to the timeline or not.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="path">
	<h5><a href="#path">path</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.text2speech.path</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Text to Speech Path for generated files.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="recentText">
	<h5><a href="#recentText">recentText</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.text2speech.recentText</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Table of recent items in Text to Speech Search.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="replaceSpaceWithUnderscore">
	<h5><a href="#replaceSpaceWithUnderscore">replaceSpaceWithUnderscore</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.text2speech.replaceSpaceWithUnderscore</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Replace Space with Underscore</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="tag">
	<h5><a href="#tag">tag</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.text2speech.tag</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Tag that will be added to generated voice overs.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="useUnderscore">
	<h5><a href="#useUnderscore">useUnderscore</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.text2speech.useUnderscore</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>If <code>true</code> then an underscore will be used in the Custom Prefix filename otherwise a dash will be used.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="voice">
	<h5><a href="#voice">voice</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.text2speech.voice</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Text to Speech Voice.</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Functions</h4>
  <section id="chooseFolder">
	<h5><a href="#chooseFolder">chooseFolder</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.text2speech.chooseFolder() -&gt; string or false</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Prompts the user to choose a folder for the Text to Speech Tool.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A string of the selected path or <code>false</code> if cancelled.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="insertFromPasteboard">
	<h5><a href="#insertFromPasteboard">insertFromPasteboard</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.text2speech.insertFromPasteboard() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Inserts Text to Speech by reading the Pasteboard.</p>
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
  <section id="show">
	<h5><a href="#show">show</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.text2speech.show() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Shows the Text to Speech Chooser.</p>
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
