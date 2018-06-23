# [docs](index.md) » cp.apple.finalcutpro.main.SecondaryWindow
---

Secondary Window Module.

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
	<li><a href="#matches">matches</a></li>
  </ul>
<li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
  <ul>
	<li><a href="#browserGroupUI">browserGroupUI</a></li>
	<li><a href="#frame">frame</a></li>
	<li><a href="#hsWindow">hsWindow</a></li>
	<li><a href="#isFullScreen">isFullScreen</a></li>
	<li><a href="#isShowing">isShowing</a></li>
	<li><a href="#rootGroupUI">rootGroupUI</a></li>
	<li><a href="#timelineGroupUI">timelineGroupUI</a></li>
	<li><a href="#UI">UI</a></li>
	<li><a href="#viewerGroupUI">viewerGroupUI</a></li>
  </ul>
<li>Methods - API calls which can only be made on an object returned by a constructor</li>
  <ul>
	<li><a href="#app">app</a></li>
	<li><a href="#show">show</a></li>
	<li><a href="#window">window</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="matches">
	<h5><a href="#matches">matches</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.SecondaryWindow.matches(element) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Checks to see if an element matches what we think it should be.</p>
<p>Parameters:</p>
<ul>
<li>element - An <code>axuielementObject</code> to check.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if matches otherwise <code>false</code></li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Fields</h4>
  <section id="browserGroupUI">
	<h5><a href="#browserGroupUI">browserGroupUI</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.SecondaryWindow.browserGroupUI &lt;cp.prop: hs._asm.axuielement; read-only; live&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The UI element that will contain the <code>Browser</code> if it's on the Secondary Window.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="frame">
	<h5><a href="#frame">frame</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.SecondaryWindow.frame &lt;cp.prop: frame&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The current position (x, y, width, height) of the window.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="hsWindow">
	<h5><a href="#hsWindow">hsWindow</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.SecondaryWindow.hsWindow &lt;cp.prop: hs.window; read-only; live&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The <code>hs.window</code> instance for the window, or <code>nil</code> if it can't be found.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="isFullScreen">
	<h5><a href="#isFullScreen">isFullScreen</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.SecondaryWindow.isFullScreen &lt;cp.prop: boolean; live&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Is <code>true</code> if the window is full-screen.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="isShowing">
	<h5><a href="#isShowing">isShowing</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.SecondaryWindow.isShowing &lt;cp.prop: boolean; read-only; live&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Is <code>true</code> if the window is visible.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="rootGroupUI">
	<h5><a href="#rootGroupUI">rootGroupUI</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.SecondaryWindow.rootGroupUI &lt;cp.prop: hs._asm.axuielement; read-only; live&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The root UI element on the window.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="timelineGroupUI">
	<h5><a href="#timelineGroupUI">timelineGroupUI</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.SecondaryWindow.timelineGroupUI &lt;cp.prop: hs._asm.axuielement; read-only; live&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The UI element that will contain the <code>Timeline</code> if it's on the Secondary Window.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="UI">
	<h5><a href="#UI">UI</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.SecondaryWindow.UI &lt;cp.prop: axuielement; read-only; live&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The <code>axuielement</code> for the window.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="viewerGroupUI">
	<h5><a href="#viewerGroupUI">viewerGroupUI</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.SecondaryWindow.viewerGroupUI &lt;cp.prop: hs._asm.axuielement; read-only; live&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The UI element that will contain the <code>Viewer</code> if it's on the Secondary Window.</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Methods</h4>
  <section id="app">
	<h5><a href="#app">app</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.SecondaryWindow:app() -&gt; App</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the app instance representing Final Cut Pro.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>App</li>
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
		<td><code>cp.apple.finalcutpro.main.SecondaryWindow:show() -&gt; SecondaryWindow</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Show the Secondary Window.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>SecondaryWindow</code> object.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="window">
	<h5><a href="#window">window</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.SecondaryWindow:window() -&gt; cp.ui.Window</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the <code>Window</code> instance.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>Window</code> instance.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
