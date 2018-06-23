# [docs](index.md) » cp.apple.finalcutpro.main.MediaBrowser
---

Media Browser Module.

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
	<li><a href="#GARAGE_BAND">GARAGE_BAND</a></li>
	<li><a href="#ITUNES">ITUNES</a></li>
	<li><a href="#MAX_SECTIONS">MAX_SECTIONS</a></li>
	<li><a href="#PHOTOS">PHOTOS</a></li>
	<li><a href="#SOUND_EFFECTS">SOUND_EFFECTS</a></li>
	<li><a href="#TITLE">TITLE</a></li>
  </ul>
<li>Constructors - API calls which return an object, typically one that offers API methods</li>
  <ul>
	<li><a href="#new">new</a></li>
  </ul>
<li>Methods - API calls which can only be made on an object returned by a constructor</li>
  <ul>
	<li><a href="#app">app</a></li>
	<li><a href="#group">group</a></li>
	<li><a href="#hide">hide</a></li>
	<li><a href="#loadLayout">loadLayout</a></li>
	<li><a href="#parent">parent</a></li>
	<li><a href="#saveLayout">saveLayout</a></li>
	<li><a href="#search">search</a></li>
	<li><a href="#show">show</a></li>
	<li><a href="#showGarageBand">showGarageBand</a></li>
	<li><a href="#showITunes">showITunes</a></li>
	<li><a href="#showPhotos">showPhotos</a></li>
	<li><a href="#showSection">showSection</a></li>
	<li><a href="#showSoundEffects">showSoundEffects</a></li>
	<li><a href="#sidebar">sidebar</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Constants</h4>
  <section id="GARAGE_BAND">
	<h5><a href="#GARAGE_BAND">GARAGE_BAND</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.MediaBrowser.GARAGE_BAND -&gt; number</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Garage Band ID.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="ITUNES">
	<h5><a href="#ITUNES">ITUNES</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.MediaBrowser.ITUNES -&gt; number</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>iTunes ID.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="MAX_SECTIONS">
	<h5><a href="#MAX_SECTIONS">MAX_SECTIONS</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.MediaBrowser.MAX_SECTIONS -&gt; number</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Maximum Sections.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="PHOTOS">
	<h5><a href="#PHOTOS">PHOTOS</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.MediaBrowser.PHOTOS -&gt; number</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Photos ID.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="SOUND_EFFECTS">
	<h5><a href="#SOUND_EFFECTS">SOUND_EFFECTS</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.MediaBrowser.SOUND_EFFECTS -&gt; number</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Sound Effects ID.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="TITLE">
	<h5><a href="#TITLE">TITLE</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.MediaBrowser.TITLE -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Photos &amp; Audio Title.</p>
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
		<td><code>cp.apple.finalcutpro.main.MediaBrowser.new(parent) -&gt; MediaBrowser</code></td>
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
<li>parent - The parent object.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A new <code>MediaBrowser</code> object.</li>
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
		<td><code>cp.apple.finalcutpro.main.MediaBrowser:app() -&gt; App</code></td>
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
  <section id="group">
	<h5><a href="#group">group</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.MediaBrowser:group() -&gt; PopUpButton</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Get the group PopUpButton.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>PopUpButton</code> object.</li>
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
		<td><code>cp.apple.finalcutpro.main.MediaBrowser:hide() -&gt; MediaBrowser</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Hide the Media Browser.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>MediaBrowser</code> object.</li>
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
		<td><code>cp.apple.finalcutpro.main.MediaBrowser:loadLayout(layout) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Loads a Media Browser layout.</p>
<p>Parameters:</p>
<ul>
<li>layout - A table containing the Media Browser layout settings - created using <code>cp.apple.finalcutpro.main.MediaBrowser:saveLayout()</code>.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="parent">
	<h5><a href="#parent">parent</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.MediaBrowser:parent() -&gt; parent</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the parent object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>parent</li>
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
		<td><code>cp.apple.finalcutpro.main.MediaBrowser:saveLayout() -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Saves the current Media Browser layout to a table.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table containing the current Media Browser Layout.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="search">
	<h5><a href="#search">search</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.MediaBrowser:search() -&gt; axuielementObject</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Get the Top Categories UI.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>axuielementObject</code> object.</li>
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
		<td><code>cp.apple.finalcutpro.main.MediaBrowser:show() -&gt; MediaBrowser</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Show the Media Browser.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>MediaBrowser</code> object.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="showGarageBand">
	<h5><a href="#showGarageBand">showGarageBand</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.MediaBrowser:showGarageBand() -&gt; MediaBrowser</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Show Garage Band Section.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>MediaBrowser</code> object.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="showITunes">
	<h5><a href="#showITunes">showITunes</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.MediaBrowser:showITunes() -&gt; MediaBrowser</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Show iTunes Section.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>MediaBrowser</code> object.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="showPhotos">
	<h5><a href="#showPhotos">showPhotos</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.MediaBrowser:showPhotos() -&gt; MediaBrowser</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Show Photos Section.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>MediaBrowser</code> object.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="showSection">
	<h5><a href="#showSection">showSection</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.MediaBrowser:showSection(index) -&gt; MediaBrowser</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Show a specific section.</p>
<p>Parameters:</p>
<ul>
<li>index - The index ID of the section you want to show as a number.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>MediaBrowser</code> object.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="showSoundEffects">
	<h5><a href="#showSoundEffects">showSoundEffects</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.MediaBrowser:showSoundEffects() -&gt; MediaBrowser</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Show Sound Effects Section.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>MediaBrowser</code> object.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="sidebar">
	<h5><a href="#sidebar">sidebar</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.MediaBrowser:sidebar() -&gt; Table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Get the Sidebar Table.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>Table</code> object.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
