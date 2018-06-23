# [docs](index.md) » cp.plist
---

Reads & Writes plist data.

<style type="text/css">
	a { text-decoration: none; }
	a:hover { text-decoration: underline; }
	th { background-color: #DDDDDD; vertical-align: top; padding: 3px; }
	td { width: 100%; background-color: #EEEEEE; vertical-align: top; padding: 3px; }
	table { width: 100% ; border: 1px solid #0; text-align: left; }
	section > table table td { width: 0; }
</style>
<link rel="stylesheet" href="../../css/docs.css" type="text/css" media="screen" />
<h3>Submodules</h3>
<ul>
<li><a href="cp.plist.archiver.md">cp.plist.archiver</a></li>
<li><a href="cp.plist.plistParser.md">cp.plist.plistParser</a></li>
</ul>
<h3>API Overview</h3>
<ul>
<li>Functions - API calls offered directly by the extension</li>
  <ul>
	<li><a href="#base64ToTable">base64ToTable</a></li>
	<li><a href="#binaryFileToTable">binaryFileToTable</a></li>
	<li><a href="#binaryFileToXML">binaryFileToXML</a></li>
	<li><a href="#binaryToTable">binaryToTable</a></li>
	<li><a href="#fileToTable">fileToTable</a></li>
	<li><a href="#isBinaryPlist">isBinaryPlist</a></li>
	<li><a href="#xmlFileToTable">xmlFileToTable</a></li>
	<li><a href="#xmlToTable">xmlToTable</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="base64ToTable">
	<h5><a href="#base64ToTable">base64ToTable</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.plist.base64ToTable(base64Data) -&gt; table | nil, string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Converts base64 encoded Property List string into a Table.</p>
<p>Parameters:</p>
<ul>
<li>base64Data - Binary data encoded in base64 as a string</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table of the plist data</li>
<li>A error message as string if an error occurs</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="binaryFileToTable">
	<h5><a href="#binaryFileToTable">binaryFileToTable</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.plist.binaryFileToTable(plistFileName) -&gt; table | nil, string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Converts the data from a Binary File into a LUA Table.</p>
<p>Parameters:</p>
<ul>
<li>plistFileName - Path &amp; Filename of the Binary File</li>
</ul>
<p>Returns:</p>
<ul>
<li>data             - A table of plist data, or <code>nil</code> if there was a problem.</li>
<li>err              - The error message, or <code>nil</code> if there were no problems.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="binaryFileToXML">
	<h5><a href="#binaryFileToXML">binaryFileToXML</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.plist.binaryFileToXML(plistFileName) -&gt; string | nil, string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Converts the data from a Binary plist File into XML as a string.</p>
<p>Parameters:</p>
<ul>
<li>plistFileName - Path &amp; Filename of the Binary File</li>
</ul>
<p>Returns:</p>
<ul>
<li>data             - A string of XML data</li>
<li>err              - The error message, or <code>nil</code> if there were no problems.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="binaryToTable">
	<h5><a href="#binaryToTable">binaryToTable</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.plist.binaryToTable(binaryData) -&gt; table | nil, string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Converts Binary Data into a LUA Table.</p>
<p>Parameters:</p>
<ul>
<li>binaryData       - Binary data</li>
</ul>
<p>Returns:</p>
<ul>
<li>data             - A string of XML data</li>
<li>err              - The error message, or <code>nil</code> if there were no problems.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="fileToTable">
	<h5><a href="#fileToTable">fileToTable</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.plist.fileToTable(plistFileName) -&gt; table | nil, string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Converts plist data from a binary or XML file into a LUA Table.
It will check the file prior to loading to determine which type it is.
If you know which type of file you're dealing with in advance, you can use
cp.plist.xmlFileToTable() or hs.plist.binaryFileToTable() instead.</p>
<p>Parameters:</p>
<ul>
<li>plistFileName    - Path &amp; Filename of the XML File</li>
</ul>
<p>Returns:</p>
<ul>
<li>data             - A table of plist data, or <code>nil</code> if there was a problem.</li>
<li>err              - The error message, or <code>nil</code> if there were no problems.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="isBinaryPlist">
	<h5><a href="#isBinaryPlist">isBinaryPlist</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.plist.isBinaryPlist(plistList) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns true if plistList is a binary plist file otherwise false</p>
<p>Parameters:</p>
<ul>
<li>plistList - Path to the file</li>
</ul>
<p>Returns:</p>
<ul>
<li>Boolean</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="xmlFileToTable">
	<h5><a href="#xmlFileToTable">xmlFileToTable</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.plist.xmlFileToTable(plistFileName) -&gt; table | nil, string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Converts XML data from a file into a LUA Table.</p>
<p>Parameters:</p>
<ul>
<li>plistFileName    - Path &amp; Filename of the XML File</li>
</ul>
<p>Returns:</p>
<ul>
<li>data             - A table of plist data, or <code>nil</code> if there was a problem.</li>
<li>err              - The error message, or <code>nil</code> if there were no problems.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="xmlToTable">
	<h5><a href="#xmlToTable">xmlToTable</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.plist.xmlToTable(plistXml) -&gt; table | nil, string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Converts an XML plist string into a LUA Table.</p>
<p>Parameters:</p>
<ul>
<li>plistXml         - The XML string</li>
</ul>
<p>Returns:</p>
<ul>
<li>data             - A table of plist data, or <code>nil</code> if there was a problem.</li>
<li>err              - The error message, or <code>nil</code> if there were no problems.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
