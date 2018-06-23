# [docs](index.md) » plugins.finalcutpro.watchfolders.panels.fcpxml
---

Final Cut Pro FCPXML Watch Folder Plugin.

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
	<li><a href="#SECONDS_UNTIL_DELETE">SECONDS_UNTIL_DELETE</a></li>
  </ul>
<li>Variables - Configurable values</li>
  <ul>
	<li><a href="#automaticallyImport">automaticallyImport</a></li>
	<li><a href="#deleteAfterImport">deleteAfterImport</a></li>
	<li><a href="#disableImport">disableImport</a></li>
	<li><a href="#filesInTransit">filesInTransit</a></li>
	<li><a href="#notifications">notifications</a></li>
	<li><a href="#savedNotifications">savedNotifications</a></li>
	<li><a href="#watchFolders">watchFolders</a></li>
	<li><a href="#watchFolderTableID">watchFolderTableID</a></li>
  </ul>
<li>Functions - API calls offered directly by the extension</li>
  <ul>
	<li><a href="#addWatchFolder">addWatchFolder</a></li>
	<li><a href="#controllerCallback">controllerCallback</a></li>
	<li><a href="#createNotification">createNotification</a></li>
	<li><a href="#generateTable">generateTable</a></li>
	<li><a href="#importFile">importFile</a></li>
	<li><a href="#init">init</a></li>
	<li><a href="#insertFilesIntoFinalCutPro">insertFilesIntoFinalCutPro</a></li>
	<li><a href="#newWatcher">newWatcher</a></li>
	<li><a href="#refreshTable">refreshTable</a></li>
	<li><a href="#removeWatcher">removeWatcher</a></li>
	<li><a href="#setupWatchers">setupWatchers</a></li>
	<li><a href="#styleSheet">styleSheet</a></li>
	<li><a href="#watchFolderTriggered">watchFolderTriggered</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Constants</h4>
  <section id="SECONDS_UNTIL_DELETE">
	<h5><a href="#SECONDS_UNTIL_DELETE">SECONDS_UNTIL_DELETE</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.watchfolders.panels.fcpxml.SECONDS_UNTIL_DELETE -&gt; number</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Seconds until a file is deleted.</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Variables</h4>
  <section id="automaticallyImport">
	<h5><a href="#automaticallyImport">automaticallyImport</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.watchfolders.panels.fcpxml.automaticallyImport &lt;cp.prop: boolean&gt;</code></td>
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
  <section id="deleteAfterImport">
	<h5><a href="#deleteAfterImport">deleteAfterImport</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.watchfolders.panels.fcpxml.deleteAfterImport &lt;cp.prop: boolean&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Boolean that sets whether or not you want to delete file after they've been imported.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="disableImport">
	<h5><a href="#disableImport">disableImport</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.watchfolders.panels.fcpxml.disableImport -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>When <code>true</code> Notifications will no longer be triggered.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="filesInTransit">
	<h5><a href="#filesInTransit">filesInTransit</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.watchfolders.panels.fcpxml.filesInTransit -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Files currently being copied</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="notifications">
	<h5><a href="#notifications">notifications</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.watchfolders.panels.fcpxml.notifications -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Table of Notifications</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="savedNotifications">
	<h5><a href="#savedNotifications">savedNotifications</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.watchfolders.panels.fcpxml.savedNotifications &lt;cp.prop: table&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Table of Notifications that are saved between restarts</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="watchFolders">
	<h5><a href="#watchFolders">watchFolders</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.watchfolders.panels.fcpxml.watchFolders &lt;cp.prop: table&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Table of the users watch folders.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="watchFolderTableID">
	<h5><a href="#watchFolderTableID">watchFolderTableID</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.watchfolders.panels.fcpxml.watchFolderTableID -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Watch Folder Table ID</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Functions</h4>
  <section id="addWatchFolder">
	<h5><a href="#addWatchFolder">addWatchFolder</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.watchfolders.panels.fcpxml.addWatchFolder() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Opens the "Add Watch Folder" Dialog.</p>
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
  <section id="controllerCallback">
	<h5><a href="#controllerCallback">controllerCallback</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.watchfolders.panels.fcpxml.controllerCallback(id, params) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Callback Controller</p>
<p>Parameters:</p>
<ul>
<li>id - ID as string</li>
<li>params - table of Parameters</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="createNotification">
	<h5><a href="#createNotification">createNotification</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.watchfolders.panels.fcpxml.createNotification(file) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new notification</p>
<p>Parameters:</p>
<ul>
<li>file - File name</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="generateTable">
	<h5><a href="#generateTable">generateTable</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.watchfolders.panels.fcpxml.generateTable() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Generate HTML Table</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>Returns a HTML table as a string</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="importFile">
	<h5><a href="#importFile">importFile</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.watchfolders.panels.fcpxml.importFile(file, obj) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Imports a file into Final Cut Pro</p>
<p>Parameters:</p>
<ul>
<li>file - File name</li>
<li>tag - The notification tag</li>
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
		<td><code>plugins.finalcutpro.watchfolders.panels.fcpxml.init(deps, env) -&gt; table</code></td>
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
<li>deps - The dependencies environment</li>
<li>env - The plugin environment</li>
</ul>
<p>Returns:</p>
<ul>
<li>Table of the module.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="insertFilesIntoFinalCutPro">
	<h5><a href="#insertFilesIntoFinalCutPro">insertFilesIntoFinalCutPro</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.watchfolders.panels.fcpxml.insertFilesIntoFinalCutPro(files) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Imports a file into Final Cut Pro</p>
<p>Parameters:</p>
<ul>
<li>files - File names in table</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="newWatcher">
	<h5><a href="#newWatcher">newWatcher</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.watchfolders.panels.fcpxml.newWatcher(path) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>New Folder Watcher</p>
<p>Parameters:</p>
<ul>
<li>path - Path to Watch Folder</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="refreshTable">
	<h5><a href="#refreshTable">refreshTable</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.watchfolders.panels.fcpxml.refreshTable() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Refreshes the Final Cut Pro Watch Folder Panel via JavaScript Injection</p>
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
  <section id="removeWatcher">
	<h5><a href="#removeWatcher">removeWatcher</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.watchfolders.panels.fcpxml.removeWatcher(path) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Remove Folder Watcher</p>
<p>Parameters:</p>
<ul>
<li>path - Path to Watch Folder</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="setupWatchers">
	<h5><a href="#setupWatchers">setupWatchers</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.watchfolders.panels.fcpxml.setupWatchers(path) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Setup Folder Watchers</p>
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
  <section id="styleSheet">
	<h5><a href="#styleSheet">styleSheet</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.watchfolders.panels.fcpxml.styleSheet() -&gt; cp.web.html</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Generates Style Sheet</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>Returns Style Sheet as a string</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="watchFolderTriggered">
	<h5><a href="#watchFolderTriggered">watchFolderTriggered</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.watchfolders.panels.fcpxml.watchFolderTriggered(files) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Watch Folder Triggered</p>
<p>Parameters:</p>
<ul>
<li>files - A table of files</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
