# [docs](index.md) » plugins.compressor.watchfolders.panels.media
---

Final Cut Pro Media Watch Folder Plugin.

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
	<li><a href="#addFilesToCompressor">addFilesToCompressor</a></li>
	<li><a href="#addWatchFolder">addWatchFolder</a></li>
	<li><a href="#controllerCallback">controllerCallback</a></li>
	<li><a href="#generateTable">generateTable</a></li>
	<li><a href="#init">init</a></li>
	<li><a href="#newWatcher">newWatcher</a></li>
	<li><a href="#refreshTable">refreshTable</a></li>
	<li><a href="#removeWatcher">removeWatcher</a></li>
	<li><a href="#setupWatchers">setupWatchers</a></li>
	<li><a href="#styleSheet">styleSheet</a></li>
	<li><a href="#watchCompressorStatus">watchCompressorStatus</a></li>
	<li><a href="#watchFolderTriggered">watchFolderTriggered</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Variables</h4>
  <section id="automaticallyImport">
	<h5><a href="#automaticallyImport">automaticallyImport</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.compressor.watchfolders.panels.media.automaticallyImport</code></td>
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
		<td><code>plugins.compressor.watchfolders.panels.media.deleteAfterImport</code></td>
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
		<td><code>plugins.compressor.watchfolders.panels.media.disableImport</code></td>
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
		<td><code>plugins.compressor.watchfolders.panels.media.filesInTransit</code></td>
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
		<td><code>plugins.compressor.watchfolders.panels.media.notifications</code></td>
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
		<td><code>plugins.compressor.watchfolders.panels.media.savedNotifications</code></td>
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
		<td><code>plugins.compressor.watchfolders.panels.media.watchFolders</code></td>
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
		<td><code>plugins.compressor.watchfolders.panels.media.watchFolderTableID</code></td>
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
  <section id="addFilesToCompressor">
	<h5><a href="#addFilesToCompressor">addFilesToCompressor</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.compressor.watchfolders.panels.media.addFilesToCompressor(files) -&gt; none</code></td>
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
  <section id="addWatchFolder">
	<h5><a href="#addWatchFolder">addWatchFolder</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.compressor.watchfolders.panels.media.addWatchFolder() -&gt; none</code></td>
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
		<td><code>plugins.compressor.watchfolders.panels.media.controllerCallback(id, params) -&gt; none</code></td>
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
  <section id="generateTable">
	<h5><a href="#generateTable">generateTable</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.compressor.watchfolders.panels.media.generateTable() -&gt; string</code></td>
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
  <section id="init">
	<h5><a href="#init">init</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.compressor.watchfolders.panels.media.init(deps, env) -&gt; table</code></td>
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
  <section id="newWatcher">
	<h5><a href="#newWatcher">newWatcher</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.compressor.watchfolders.panels.media.newWatcher(path) -&gt; none</code></td>
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
		<td><code>plugins.compressor.watchfolders.panels.media.refreshTable() -&gt; string</code></td>
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
		<td><code>plugins.compressor.watchfolders.panels.media.removeWatcher(path) -&gt; none</code></td>
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
		<td><code>plugins.compressor.watchfolders.panels.media.setupWatchers(path) -&gt; none</code></td>
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
		<td><code>plugins.compressor.watchfolders.panels.media.styleSheet() -&gt; cp.web.html</code></td>
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
<li>Returns Style Sheet as a <code>cp.web.html</code> block.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="watchCompressorStatus">
	<h5><a href="#watchCompressorStatus">watchCompressorStatus</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.compressor.watchfolders.panels.media.watchCompressorStatus(jobID) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Checks the Status of a Job in Compressor</p>
<p>Parameters:</p>
<ul>
<li>jobID - Job ID as string</li>
<li>file - File Path as string</li>
<li>destinationPath - Destination Path as string</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
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
		<td><code>plugins.compressor.watchfolders.panels.media.watchFolderTriggered(files) -&gt; none</code></td>
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
