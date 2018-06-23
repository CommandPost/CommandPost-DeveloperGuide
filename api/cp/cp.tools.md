# [docs](index.md) » cp.tools
---

A collection of handy miscellaneous tools for Lua development.

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
	<li><a href="#cleanupButtonText">cleanupButtonText</a></li>
	<li><a href="#dirFiles">dirFiles</a></li>
	<li><a href="#doesDirectoryExist">doesDirectoryExist</a></li>
	<li><a href="#doesFileExist">doesFileExist</a></li>
	<li><a href="#doubleLeftClick">doubleLeftClick</a></li>
	<li><a href="#endsWith">endsWith</a></li>
	<li><a href="#ensureDirectoryExists">ensureDirectoryExists</a></li>
	<li><a href="#executeWithAdministratorPrivileges">executeWithAdministratorPrivileges</a></li>
	<li><a href="#firstToUpper">firstToUpper</a></li>
	<li><a href="#getEmail">getEmail</a></li>
	<li><a href="#getExternalDevices">getExternalDevices</a></li>
	<li><a href="#getFilenameFromPath">getFilenameFromPath</a></li>
	<li><a href="#getFullname">getFullname</a></li>
	<li><a href="#getKeysSortedByValue">getKeysSortedByValue</a></li>
	<li><a href="#getmacOSVersion">getmacOSVersion</a></li>
	<li><a href="#getModelName">getModelName</a></li>
	<li><a href="#getRAMSize">getRAMSize</a></li>
	<li><a href="#getScreenshotsAsBase64">getScreenshotsAsBase64</a></li>
	<li><a href="#getThunderboltDevices">getThunderboltDevices</a></li>
	<li><a href="#getUSBDevices">getUSBDevices</a></li>
	<li><a href="#getVRAMSize">getVRAMSize</a></li>
	<li><a href="#iconFallback">iconFallback</a></li>
	<li><a href="#incrementFilename">incrementFilename</a></li>
	<li><a href="#isNumberString">isNumberString</a></li>
	<li><a href="#isOffScreen">isOffScreen</a></li>
	<li><a href="#leftClick">leftClick</a></li>
	<li><a href="#lines">lines</a></li>
	<li><a href="#macOSVersion">macOSVersion</a></li>
	<li><a href="#mergeTable">mergeTable</a></li>
	<li><a href="#ninjaDoubleClick">ninjaDoubleClick</a></li>
	<li><a href="#ninjaMouseAction">ninjaMouseAction</a></li>
	<li><a href="#ninjaMouseClick">ninjaMouseClick</a></li>
	<li><a href="#numberToWord">numberToWord</a></li>
	<li><a href="#playErrorSound">playErrorSound</a></li>
	<li><a href="#removeFilenameFromPath">removeFilenameFromPath</a></li>
	<li><a href="#removeFromTable">removeFromTable</a></li>
	<li><a href="#rmdir">rmdir</a></li>
	<li><a href="#round">round</a></li>
	<li><a href="#safeFilename">safeFilename</a></li>
	<li><a href="#spairs">spairs</a></li>
	<li><a href="#split">split</a></li>
	<li><a href="#splitOnColumn">splitOnColumn</a></li>
	<li><a href="#stringMaxLength">stringMaxLength</a></li>
	<li><a href="#tableContains">tableContains</a></li>
	<li><a href="#tableCount">tableCount</a></li>
	<li><a href="#trim">trim</a></li>
	<li><a href="#unescape">unescape</a></li>
	<li><a href="#urlQueryStringDecode">urlQueryStringDecode</a></li>
	<li><a href="#volumeFormat">volumeFormat</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="cleanupButtonText">
	<h5><a href="#cleanupButtonText">cleanupButtonText</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.cleanupButtonText(value) -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Removes the … symbol and multiple &gt;'s from a string.</p>
<p>Parameters:</p>
<ul>
<li>value - A string</li>
</ul>
<p>Returns:</p>
<ul>
<li>A cleaned string</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="dirFiles">
	<h5><a href="#dirFiles">dirFiles</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.dirFiles(path) -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets all the files in a directory</p>
<p>Parameters:</p>
<ul>
<li>path - A path as string</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table containing filenames as strings.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="doesDirectoryExist">
	<h5><a href="#doesDirectoryExist">doesDirectoryExist</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.doesDirectoryExist(path) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns whether or not a directory exists.</p>
<p>Parameters:</p>
<ul>
<li>path - Path to the directory</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the directory exists otherwise <code>false</code></li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="doesFileExist">
	<h5><a href="#doesFileExist">doesFileExist</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.doesFileExist(path) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns whether or not a file exists.</p>
<p>Parameters:</p>
<ul>
<li>path - Path to the file</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the file exists otherwise <code>false</code></li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="doubleLeftClick">
	<h5><a href="#doubleLeftClick">doubleLeftClick</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.doubleLeftClick(point[, delay]) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Performs a Left Mouse Double Click.</p>
<p>Parameters:</p>
<ul>
<li>point - A point-table containing the absolute x and y co-ordinates to move the mouse pointer to</li>
<li>delay - The optional delay between multiple mouse clicks</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="endsWith">
	<h5><a href="#endsWith">endsWith</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.endsWith(str, ending) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Checks to see if <code>str</code> has the same ending as <code>ending</code>.</p>
<p>Parameters:</p>
<ul>
<li>str       - String to analysis</li>
<li>ending    - End of string to compare against</li>
</ul>
<p>Returns:</p>
<ul>
<li>table</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="ensureDirectoryExists">
	<h5><a href="#ensureDirectoryExists">ensureDirectoryExists</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.ensureDirectoryExists(rootPath, ...) -&gt; string | nil</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Ensures all steps on a provided path exist. If not, attempts to create them.
If it fails, <code>nil</code> is returned.</p>
<p>Parameters:</p>
<ul>
<li><code>rootPath</code> - The root path (should already exist).</li>
<li><code>...</code>      - The list of path steps to create</li>
</ul>
<p>Returns:</p>
<ul>
<li>The full path, if it exists, or <code>nil</code> if unable to create the directory for some reason.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="executeWithAdministratorPrivileges">
	<h5><a href="#executeWithAdministratorPrivileges">executeWithAdministratorPrivileges</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.executeWithAdministratorPrivileges(input[, stopOnError]) -&gt; boolean or string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Executes a single or multiple shell commands with Administrator Privileges.</p>
<p>Parameters:</p>
<ul>
<li>input - either a string or a table of strings of commands you want to execute</li>
<li>stopOnError - an optional variable that stops processing multiple commands when an individual commands returns an error</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successful, <code>false</code> if cancelled and a string if there's an error.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="firstToUpper">
	<h5><a href="#firstToUpper">firstToUpper</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.firstToUpper(str) -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Makes the first letter of a string uppercase.</p>
<p>Parameters:</p>
<ul>
<li>str - The string you want to manipulate</li>
</ul>
<p>Returns:</p>
<ul>
<li>A string</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getEmail">
	<h5><a href="#getEmail">getEmail</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.getEmail() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the current users Email, otherwise an empty string.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>String</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getExternalDevices">
	<h5><a href="#getExternalDevices">getExternalDevices</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.getExternalDevices() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a string of USB &amp; Thunderbolt Devices.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>String</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getFilenameFromPath">
	<h5><a href="#getFilenameFromPath">getFilenameFromPath</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.getFilenameFromPath(input[, removeExtension]) -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets the filename component of a path.</p>
<p>Parameters:</p>
<ul>
<li>input - The path</li>
<li>removeExtension - (optional) set to <code>true</code> if the file extension should be removed</li>
</ul>
<p>Returns:</p>
<ul>
<li>A string of the filename.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getFullname">
	<h5><a href="#getFullname">getFullname</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.getFullname() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the current users Full Name, otherwise an empty string.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>String</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getKeysSortedByValue">
	<h5><a href="#getKeysSortedByValue">getKeysSortedByValue</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.getKeysSortedByValue(tbl, sortFunction) -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Sorts table keys by a value</p>
<p>Parameters:</p>
<ul>
<li>tbl - the table you want to sort</li>
<li>sortFunction - the function you want to use to sort the table</li>
</ul>
<p>Returns:</p>
<ul>
<li>A sorted table</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getmacOSVersion">
	<h5><a href="#getmacOSVersion">getmacOSVersion</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.getmacOSVersion() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the macOS Version in the format that Apple's Feedback Form expects.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The macOS version as a string or "" if unknown.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getModelName">
	<h5><a href="#getModelName">getModelName</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.getModelName() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns Model Name of Hardware.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>String</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getRAMSize">
	<h5><a href="#getRAMSize">getRAMSize</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.getRAMSize() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns RAM Size in a format Apple's Feedback form expects.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The RAM size as a string, or "" if unknown.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getScreenshotsAsBase64">
	<h5><a href="#getScreenshotsAsBase64">getScreenshotsAsBase64</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.getScreenshotsAsBase64() -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Captures all available screens and saves them as base64 encodes in a table.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table containing base64 images of all available screens.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getThunderboltDevices">
	<h5><a href="#getThunderboltDevices">getThunderboltDevices</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.getThunderboltDevices() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a string of Thunderbolt Devices.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>String</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getUSBDevices">
	<h5><a href="#getUSBDevices">getUSBDevices</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.getUSBDevices() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a string of USB Devices.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>String</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getVRAMSize">
	<h5><a href="#getVRAMSize">getVRAMSize</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.getVRAMSize() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the VRAM size in format suitable for Apple's Final Cut Pro feedback form or "" if unknown.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>String</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="iconFallback">
	<h5><a href="#iconFallback">iconFallback</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.iconFallback(paths) -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Excepts one or more paths to an icon, checks to see if they exist (in the order that they're given), and if none exist, returns the CommandPost icon path.</p>
<p>Parameters:</p>
<ul>
<li>paths - One or more paths to an icon</li>
</ul>
<p>Returns:</p>
<ul>
<li>A string</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="incrementFilename">
	<h5><a href="#incrementFilename">incrementFilename</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.incrementFilename(value) -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Increments the filename.</p>
<p>Parameters:</p>
<ul>
<li>value - A string</li>
</ul>
<p>Returns:</p>
<ul>
<li>A string</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="isNumberString">
	<h5><a href="#isNumberString">isNumberString</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.isNumberString(value) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns whether or not value is a number string.</p>
<p>Parameters:</p>
<ul>
<li>value - the string you want to check</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if value is a number string, otherwise <code>false</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="isOffScreen">
	<h5><a href="#isOffScreen">isOffScreen</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.isOffScreen(rect) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Determines if the given rect is off screen or not.</p>
<p>Parameters:</p>
<ul>
<li>rect - the rect you want to check</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if offscreen otherwise <code>false</code></li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="leftClick">
	<h5><a href="#leftClick">leftClick</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.leftClick(point[, delay, clickNumber]) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Performs a Left Mouse Click.</p>
<p>Parameters:</p>
<ul>
<li>point - A point-table containing the absolute x and y co-ordinates to move the mouse pointer to</li>
<li>delay - The optional delay between multiple mouse clicks</li>
<li>clickNumber - The optional number of times you want to perform the click.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="lines">
	<h5><a href="#lines">lines</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.lines(string) -&gt; table | nil</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Splits a string containing multiple lines of text into a table.</p>
<p>Parameters:</p>
<ul>
<li>string - the string you want to process</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table or <code>nil</code> if the parameter is not a string.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="macOSVersion">
	<h5><a href="#macOSVersion">macOSVersion</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.macOSVersion() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a the macOS Version as a single string.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A string containing the macOS version</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="mergeTable">
	<h5><a href="#mergeTable">mergeTable</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.mergeTable(target, ...) -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Merges multiple tables into a target table.</p>
<p>Parameters:</p>
<ul>
<li>target   - The target table</li>
<li>...      - Any other tables you want to merge into target</li>
</ul>
<p>Returns:</p>
<ul>
<li>Table</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="ninjaDoubleClick">
	<h5><a href="#ninjaDoubleClick">ninjaDoubleClick</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.ninjaDoubleClick(point[, delay]) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Performs a mouse double click, but returns the mouse to the original position without the users knowledge.</p>
<p>Parameters:</p>
<ul>
<li>point - A point-table containing the absolute x and y co-ordinates to move the mouse pointer to</li>
<li>delay - The optional delay between multiple mouse clicks</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="ninjaMouseAction">
	<h5><a href="#ninjaMouseAction">ninjaMouseAction</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.ninjaMouseAction(point, fn) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Moves the mouse to a point, performs a function, then returns the mouse to the original point.</p>
<p>Parameters:</p>
<ul>
<li>point - A point-table containing the absolute x and y co-ordinates to move the mouse pointer to</li>
<li>fn - A function you want to perform</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="ninjaMouseClick">
	<h5><a href="#ninjaMouseClick">ninjaMouseClick</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.ninjaMouseClick(point[, delay]) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Performs a mouse click, but returns the mouse to the original position without the users knowledge.</p>
<p>Parameters:</p>
<ul>
<li>point - A point-table containing the absolute x and y co-ordinates to move the mouse pointer to</li>
<li>delay - The optional delay between multiple mouse clicks</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="numberToWord">
	<h5><a href="#numberToWord">numberToWord</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.numberToWord(number) -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Converts a number to a string (i.e. 1 becomes "One").</p>
<p>Parameters:</p>
<ul>
<li>number - A whole number between 0 and 10</li>
</ul>
<p>Returns:</p>
<ul>
<li>A string</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="playErrorSound">
	<h5><a href="#playErrorSound">playErrorSound</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.playErrorSound() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Plays the "Funk" error sound.</p>
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
  <section id="removeFilenameFromPath">
	<h5><a href="#removeFilenameFromPath">removeFilenameFromPath</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.removeFilenameFromPath(string) -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Removes the filename from a path.</p>
<p>Parameters:</p>
<ul>
<li>string - The path</li>
</ul>
<p>Returns:</p>
<ul>
<li>A string of the path without the filename.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="removeFromTable">
	<h5><a href="#removeFromTable">removeFromTable</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.removeFromTable(table, element) -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Removes a string from a table of strings</p>
<p>Parameters:</p>
<ul>
<li>table - the table you want to check</li>
<li>element - the string you want to remove</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="rmdir">
	<h5><a href="#rmdir">rmdir</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.rmdir(path[, recursive]) -&gt; true | nil, err</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Attempts to remove the directory at the specified path, optionally removing
any contents recursively.</p>
<p>Parameters:</p>
<ul>
<li><code>path</code>        - The absolute path to remove</li>
<li><code>recursive</code>   - If <code>true</code>, the contents of the directory will be removed first.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successful, or <code>nil, err</code> if there was a problem.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="round">
	<h5><a href="#round">round</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.round(num, numDecimalPlaces) -&gt; number</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Rounds a number to a set number of decimal places</p>
<p>Parameters:</p>
<ul>
<li>num - The number you want to round</li>
<li>numDecimalPlaces - How many numbers of decimal places (defaults to 0)</li>
</ul>
<p>Returns:</p>
<ul>
<li>A rounded number</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="safeFilename">
	<h5><a href="#safeFilename">safeFilename</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.safeFilename(value[, defaultValue]) -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a Safe Filename.</p>
<p>Parameters:</p>
<ul>
<li>value - a string you want to make safe</li>
<li>defaultValue - the optional default filename to use if the value is not valid</li>
</ul>
<p>Returns:</p>
<ul>
<li>A string of the safe filename</li>
</ul>
<p>Notes:</p>
<ul>
<li>Returns "filename" is both <code>value</code> and <code>defaultValue</code> are <code>nil</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="spairs">
	<h5><a href="#spairs">spairs</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.spairs(t, order) -&gt; function</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>A customised version of pairs, called <code>spairs</code> because it iterates over the table in a sorted order.</p>
<p>Parameters:</p>
<ul>
<li>t     - The table to process</li>
<li>order - The function of how to sort the table.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A iterator function.</li>
</ul>
<p>Notes:</p>
<ul>
<li>Author: <a href="https://stackoverflow.com/a/15706820">Michal Kottman</a></li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="split">
	<h5><a href="#split">split</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.split(str, pat) -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Splits a string with a pattern.</p>
<p>Parameters:</p>
<ul>
<li>str - The string to split</li>
<li>pat - The pattern</li>
</ul>
<p>Returns:</p>
<ul>
<li>Table</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="splitOnColumn">
	<h5><a href="#splitOnColumn">splitOnColumn</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.splitOnColumn() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Splits a string on a column.</p>
<p>Parameters:</p>
<ul>
<li>Input</li>
</ul>
<p>Returns:</p>
<ul>
<li>String</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="stringMaxLength">
	<h5><a href="#stringMaxLength">stringMaxLength</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.stringMaxLength(string, maxLength[, optionalEnd]) -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Trims a string based on a maximum length.</p>
<p>Parameters:</p>
<ul>
<li>maxLength - The length of the string as a number</li>
<li>optionalEnd - A string that is applied to the end of the input string if the input string is larger than the maximum length.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A string</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="tableContains">
	<h5><a href="#tableContains">tableContains</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.tableContains(table, element) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Does a element exist in a table?</p>
<p>Parameters:</p>
<ul>
<li>table - the table you want to check</li>
<li>element - the element you want to check for</li>
</ul>
<p>Returns:</p>
<ul>
<li>Boolean</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="tableCount">
	<h5><a href="#tableCount">tableCount</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.tableCount(table) -&gt; number</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns how many items are in a table.</p>
<p>Parameters:</p>
<ul>
<li>table - The table you want to count.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The number of items in the table.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="trim">
	<h5><a href="#trim">trim</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.trim(string) -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Trims the whitespaces from a string</p>
<p>Parameters:</p>
<ul>
<li>string - the string you want to trim</li>
</ul>
<p>Returns:</p>
<ul>
<li>A trimmed string</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="unescape">
	<h5><a href="#unescape">unescape</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.unescape(str) -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Removes any URL encoding in the provided string.</p>
<p>Parameters:</p>
<ul>
<li>str - the string to decode</li>
</ul>
<p>Returns:</p>
<ul>
<li>A string with all "+" characters converted to spaces and all percent encoded sequences converted to their ASCII equivalents.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="urlQueryStringDecode">
	<h5><a href="#urlQueryStringDecode">urlQueryStringDecode</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.urlQueryStringDecode() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Decodes a URL Query String</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>Decoded URL Query String as string</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="volumeFormat">
	<h5><a href="#volumeFormat">volumeFormat</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.tools.volumeFormat(path) -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gives you the file system volume format of a path.</p>
<p>Parameters:</p>
<ul>
<li>path - the path you want to check as a string</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>NSURLVolumeLocalizedFormatDescriptionKey</code> as a string, otherwise <code>nil</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
