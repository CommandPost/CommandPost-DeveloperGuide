# [docs](index.md) » cp.apple.finalcutpro.main.FullScreenWindow
---

Full Screen Window

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
<li>Constructors - API calls which return an object, typically one that offers API methods</li>
  <ul>
	<li><a href="#new">new</a></li>
  </ul>
<li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
  <ul>
	<li><a href="#isFullScreen">isFullScreen</a></li>
	<li><a href="#isShowing">isShowing</a></li>
	<li><a href="#rootGroupUI">rootGroupUI</a></li>
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
		<td><code>cp.apple.finalcutpro.main.FullScreenWindow.matches(element) -&gt; boolean</code></td>
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
<h4 class="documentation-section">Constructors</h4>
  <section id="new">
	<h5><a href="#new">new</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.FullScreenWindow.new(app) -&gt; FullScreenWindow</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constructor</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new FCPX <code>FullScreenWindow</code> instance.</p>
<p>Parameters:</p>
<ul>
<li>app       - The FCP app instance.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The new <code>FullScreenWindow</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Fields</h4>
  <section id="isFullScreen">
	<h5><a href="#isFullScreen">isFullScreen</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.FullScreenWindow.isFullScreen &lt;cp.prop; boolean; read-only; live&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Checks if the window is full-screen.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="isShowing">
	<h5><a href="#isShowing">isShowing</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.FullScreenWindow.isShowing &lt;cp.prop; boolean; read-only; live&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Checks if the window is currently showing.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="rootGroupUI">
	<h5><a href="#rootGroupUI">rootGroupUI</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.FullScreenWindow.rootGroupUI &lt;cp.prop: hs._asm.axuielement; read-only; live&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The root <code>AXGroup</code>.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="UI">
	<h5><a href="#UI">UI</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.FullScreenWindow.UI &lt;cp.prop: hs._asm.axuielement; read-only; live&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The core <code>axuielement</code> for the window.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="viewerGroupUI">
	<h5><a href="#viewerGroupUI">viewerGroupUI</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.FullScreenWindow.viewerGroupUI &lt;cp.prop: hs._asm.axuielement; read-only; live&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The Viewer's group UI element.</p>
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
		<td><code>cp.apple.finalcutpro.main.FullScreenWindow:app() -&gt; cp.apple.finalcutpro</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the FCPX app.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The FCPX app.</li>
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
		<td><code>cp.apple.finalcutpro.main.FullScreenWindow:show() -&gt; cp.apple.finalcutpro</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Attempts to show the full screen window.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The window instance.</li>
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
		<td><code>cp.apple.finalcutpro.main.FullScreenWindow:window() -&gt; cp.ui.Window</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the <code>Window</code> instance for the full-screen window.</p>
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
