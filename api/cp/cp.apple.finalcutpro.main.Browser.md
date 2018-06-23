# [docs](index.md) » cp.apple.finalcutpro.main.Browser
---

Browser Module.

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
<li><a href="cp.apple.finalcutpro.main.Browser.BrowserMarkerPopover.md">cp.apple.finalcutpro.main.Browser.BrowserMarkerPopover</a></li>
</ul>
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
	<li><a href="#generators">generators</a></li>
	<li><a href="#hide">hide</a></li>
	<li><a href="#libraries">libraries</a></li>
	<li><a href="#loadLayout">loadLayout</a></li>
	<li><a href="#markerPopover">markerPopover</a></li>
	<li><a href="#media">media</a></li>
	<li><a href="#saveLayout">saveLayout</a></li>
	<li><a href="#showGenerators">showGenerators</a></li>
	<li><a href="#showLibraries">showLibraries</a></li>
	<li><a href="#showMedia">showMedia</a></li>
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
		<td><code>cp.apple.finalcutpro.main.Browser.matches(element) -&gt; boolean</code></td>
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
		<td><code>cp.apple.finalcutpro.main.Browser.new(app) -&gt; Browser</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constructor</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new <code>Browser</code> instance.</p>
<p>Parameters:</p>
<ul>
<li>app - The Final Cut Pro app instance.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The new <code>Browser</code>.</li>
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
		<td><code>cp.apple.finalcutpro.main.Browser:app() -&gt; App</code></td>
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
  <section id="generators">
	<h5><a href="#generators">generators</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.Browser:generators() -&gt; GeneratorsBrowser</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Get Generators Browser object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A <code>GeneratorsBrowser</code> object.</li>
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
		<td><code>cp.apple.finalcutpro.main.Browser:hide() -&gt; Browser</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Hides the Browser.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>Browser</code> object.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="libraries">
	<h5><a href="#libraries">libraries</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.Browser:libraries() -&gt; LibrariesBrowser</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Get Libraries Browser object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A <code>LibrariesBrowser</code> object.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="loadLayout">
	<h5><a href="#loadLayout">loadLayout</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.Browser:loadLayout(layout) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Loads a Browser layout.</p>
<p>Parameters:</p>
<ul>
<li>layout - A table containing the Browser layout settings - created using <code>cp.apple.finalcutpro.main.Browser:saveLayout()</code>.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="markerPopover">
	<h5><a href="#markerPopover">markerPopover</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.Browser:markerPopover() -&gt; BrowserMarkerPopover</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Get Browser Marker Popover object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A <code>BrowserMarkerPopover</code> object.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="media">
	<h5><a href="#media">media</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.Browser:media() -&gt; MediaBrowser</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Get Media Browser object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A <code>MediaBrowser</code> object.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="saveLayout">
	<h5><a href="#saveLayout">saveLayout</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.Browser:saveLayout() -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Saves the current Browser layout to a table.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table containing the current Browser Layout.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="showGenerators">
	<h5><a href="#showGenerators">showGenerators</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.Browser:showGenerators() -&gt; CheckBox</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Show Media.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A <code>CheckBox</code> object.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="showLibraries">
	<h5><a href="#showLibraries">showLibraries</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.Browser:showLibraries() -&gt; CheckBox</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Shows Libraries.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A <code>CheckBox</code> object.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="showMedia">
	<h5><a href="#showMedia">showMedia</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.Browser:showMedia() -&gt; CheckBox</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Show Media.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A <code>CheckBox</code> object.</li>
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
		<td><code>cp.apple.finalcutpro.main.Browser:showOnPrimary() -&gt; Browser</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Show Browser on Primary Screen.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>Browser</code> object.</li>
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
		<td><code>cp.apple.finalcutpro.main.Browser:showOnSecondary() -&gt; Browser</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Show Browser on Secondary Screen.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>Browser</code> object.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
