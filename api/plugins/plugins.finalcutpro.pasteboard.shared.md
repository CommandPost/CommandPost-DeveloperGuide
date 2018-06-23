# [docs](index.md) » plugins.finalcutpro.pasteboard.shared
---

Shared Pasteboard Plugin.

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
	<li><a href="#copyWithCustomClipName">copyWithCustomClipName</a></li>
	<li><a href="#copyWithCustomClipNameAndFolder">copyWithCustomClipNameAndFolder</a></li>
	<li><a href="#generateSharedPasteboardMenu">generateSharedPasteboardMenu</a></li>
	<li><a href="#getHistory">getHistory</a></li>
	<li><a href="#getHistoryPath">getHistoryPath</a></li>
	<li><a href="#getLocalFolderName">getLocalFolderName</a></li>
	<li><a href="#getRootPath">getRootPath</a></li>
	<li><a href="#init">init</a></li>
	<li><a href="#overrideNextFolderName">overrideNextFolderName</a></li>
	<li><a href="#pasteHistoryItem">pasteHistoryItem</a></li>
	<li><a href="#setHistory">setHistory</a></li>
	<li><a href="#setRootPath">setRootPath</a></li>
	<li><a href="#update">update</a></li>
	<li><a href="#validRootPath">validRootPath</a></li>
  </ul>
<li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
  <ul>
	<li><a href="#enabled">enabled</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="copyWithCustomClipName">
	<h5><a href="#copyWithCustomClipName">copyWithCustomClipName</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.pasteboard.shared.copyWithCustomClipName() -&gt; None</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Triggers a copy with custom clip name action.</p>
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
  <section id="copyWithCustomClipNameAndFolder">
	<h5><a href="#copyWithCustomClipNameAndFolder">copyWithCustomClipNameAndFolder</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.pasteboard.shared.copyWithCustomClipNameAndFolder() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Copy with Custom Label &amp; Folder.</p>
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
  <section id="generateSharedPasteboardMenu">
	<h5><a href="#generateSharedPasteboardMenu">generateSharedPasteboardMenu</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.pasteboard.shared.generateSharedPasteboardMenu() -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Generates the shared pasteboard menu.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The shared pasteboard menu as a table.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getHistory">
	<h5><a href="#getHistory">getHistory</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.pasteboard.shared.getHistory(folderName) -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets the history for a supplied folder name.</p>
<p>Parameters:</p>
<ul>
<li>folderName - The folder name</li>
</ul>
<p>Returns:</p>
<ul>
<li>The history in a table.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getHistoryPath">
	<h5><a href="#getHistoryPath">getHistoryPath</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.pasteboard.shared.getHistoryPath(folderName, fileExtension) -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets the History Path.</p>
<p>Parameters:</p>
<ul>
<li>folderName - The folder name</li>
<li>fileExtension - The file extension</li>
</ul>
<p>Returns:</p>
<ul>
<li>The history path as a string</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getLocalFolderName">
	<h5><a href="#getLocalFolderName">getLocalFolderName</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.pasteboard.shared.getLocalFolderName() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets the local folder name.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The local folder name as a string.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getRootPath">
	<h5><a href="#getRootPath">getRootPath</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.pasteboard.shared.getRootPath() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Get shared pasteboard root path.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>Shared Pasteboard Path as string.</li>
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
		<td><code>plugins.finalcutpro.pasteboard.shared.init() -&gt; sharedPasteboard</code></td>
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
<li>manager - The pasteboard manager</li>
</ul>
<p>Returns:</p>
<ul>
<li>The sharedPasteboard object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="overrideNextFolderName">
	<h5><a href="#overrideNextFolderName">overrideNextFolderName</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.pasteboard.shared.overrideNextFolderName(overrideFolder) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Overrides the folder name for the next clip which is copied from Final Cut Pro to the
specified value. Once the override has been used, the standard folder name via
<code>mod.getLocalFolderName()</code> will be used for subsequent copy operations.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The local folder name as a string.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="pasteHistoryItem">
	<h5><a href="#pasteHistoryItem">pasteHistoryItem</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.pasteboard.shared.pasteHistoryItem(folderName, index) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Paste History Item.</p>
<p>Parameters:</p>
<ul>
<li>folderName - The folder name</li>
<li>index - The index of the item you want to paste</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="setHistory">
	<h5><a href="#setHistory">setHistory</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.pasteboard.shared.setHistory(folderName, history) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Clears the history.</p>
<p>Parameters:</p>
<ul>
<li>folderName - The folder name</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="setRootPath">
	<h5><a href="#setRootPath">setRootPath</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.pasteboard.shared.setRootPath(path) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Sets the shared pasteboard root path.</p>
<p>Parameters:</p>
<ul>
<li>path - The path you want to set as a string.</li>
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
		<td><code>plugins.finalcutpro.pasteboard.shared.update() -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the list of folder names as an array of strings.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table of folder names.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="validRootPath">
	<h5><a href="#validRootPath">validRootPath</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.pasteboard.shared.validRootPath() -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets whether or not the current root path exists.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if it exists otherwise <code>false</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Fields</h4>
  <section id="enabled">
	<h5><a href="#enabled">enabled</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.pasteboard.shared.enabled &lt;cp.prop: boolean&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets whether or not the shared pasteboard is enabled as a boolean.</p>
</td>
	  </tr>
	</table>
  </section>
