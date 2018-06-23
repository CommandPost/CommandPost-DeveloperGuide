# [docs](index.md) » cp.apple.finalcutpro.main.Viewer
---

Viewer Module.

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
<li>Methods - API calls which can only be made on an object returned by a constructor</li>
  <ul>
	<li><a href="#app">app</a></li>
	<li><a href="#currentWindow">currentWindow</a></li>
	<li><a href="#hide">hide</a></li>
	<li><a href="#isEventViewer">isEventViewer</a></li>
	<li><a href="#isMainViewer">isMainViewer</a></li>
	<li><a href="#playButton">playButton</a></li>
	<li><a href="#showOnPrimary">showOnPrimary</a></li>
	<li><a href="#showOnSecondary">showOnSecondary</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="matches">
	<h5><a href="#matches">matches</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.Viewer.matches(element) -&gt; boolean</code></td>
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
		<td><code>cp.apple.finalcutpro.main.Viewer.new(app, eventViewer) -&gt; Viewer</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constructor</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new <code>Viewer</code> instance.</p>
<p>Parameters:</p>
<ul>
<li>app           - The FCP application.</li>
<li>eventViewer   - If <code>true</code>, the viewer is the Event Viewer.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The new <code>Viewer</code> instance.</li>
</ul>
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
		<td><code>cp.apple.finalcutpro.main.Viewer:app() -&gt; application</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the application.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The application.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="currentWindow">
	<h5><a href="#currentWindow">currentWindow</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.Viewer:currentWindow() -&gt; PrimaryWindow | SecondaryWindow</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets the current window object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>PrimaryWindow</code> or the <code>SecondaryWindow</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="hide">
	<h5><a href="#hide">hide</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.Viewer:hide() -&gt; self</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Hides the Viewer.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>Self</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="isEventViewer">
	<h5><a href="#isEventViewer">isEventViewer</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.Viewer:isEventViewer() -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns <code>true</code> if this is the Event Viewer.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if this is the Event Viewer.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="isMainViewer">
	<h5><a href="#isMainViewer">isMainViewer</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.Viewer:isMainViewer() -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns <code>true</code> if this is the main Viewer.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if this is the main Viewer.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="playButton">
	<h5><a href="#playButton">playButton</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.Viewer:playButton() -&gt; Button</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets the Play Button object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A Button</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="showOnPrimary">
	<h5><a href="#showOnPrimary">showOnPrimary</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.Viewer:showOnPrimary() -&gt; self</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Shows the Viewer on the Primary display.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>Self</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="showOnSecondary">
	<h5><a href="#showOnSecondary">showOnSecondary</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.Viewer:showOnSecondary() -&gt; self</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Shows the Viewer on the Seconary display.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>Self</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
