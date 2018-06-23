# [docs](index.md) » cp.apple.finalcutpro.main.LibrariesFilmstrip
---

Libraries Filmstrip Module.

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
	<li><a href="#clips">clips</a></li>
	<li><a href="#clipsUI">clipsUI</a></li>
	<li><a href="#deselectAll">deselectAll</a></li>
	<li><a href="#selectAll">selectAll</a></li>
	<li><a href="#selectClip">selectClip</a></li>
	<li><a href="#selectClipAt">selectClipAt</a></li>
	<li><a href="#selectClipTitled">selectClipTitled</a></li>
	<li><a href="#selectedClips">selectedClips</a></li>
	<li><a href="#selectedClipsUI">selectedClipsUI</a></li>
	<li><a href="#showClip">showClip</a></li>
	<li><a href="#showClipAt">showClipAt</a></li>
	<li><a href="#sortClips">sortClips</a></li>
  </ul>
<li>Constructors - API calls which return an object, typically one that offers API methods</li>
  <ul>
	<li><a href="#new">new</a></li>
  </ul>
<li>Methods - API calls which can only be made on an object returned by a constructor</li>
  <ul>
	<li><a href="#app">app</a></li>
	<li><a href="#parent">parent</a></li>
	<li><a href="#playhead">playhead</a></li>
	<li><a href="#show">show</a></li>
	<li><a href="#skimmingPlayhead">skimmingPlayhead</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="clips">
	<h5><a href="#clips">clips</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.LibrariesFilmstrip:clips(filterFn) -&gt; table | nil</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets clips using a custom filter.</p>
<p>Parameters:</p>
<ul>
<li>filterFn - A function to filter the UI results.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table of <code>Clip</code> objects or <code>nil</code> if no clip UI could be found.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="clipsUI">
	<h5><a href="#clipsUI">clipsUI</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.LibrariesFilmstrip:clipsUI(filterFn) -&gt; table | nil</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets clip UIs using a custom filter.</p>
<p>Parameters:</p>
<ul>
<li>filterFn - A function to filter the UI results.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table of <code>axuielementObject</code> objects or <code>nil</code> if no clip UI could be found.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="deselectAll">
	<h5><a href="#deselectAll">deselectAll</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.LibrariesFilmstrip:deselectAll() -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Deselect all clips.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successful otherwise <code>false</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="selectAll">
	<h5><a href="#selectAll">selectAll</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.LibrariesFilmstrip:selectAll([clips]) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Select all clips.</p>
<p>Parameters:</p>
<ul>
<li>clips - A optional table of <code>Clip</code> objects.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successful otherwise <code>false</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="selectClip">
	<h5><a href="#selectClip">selectClip</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.LibrariesFilmstrip.selectClip(clip) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Selects a clip.</p>
<p>Parameters:</p>
<ul>
<li>clip - The <code>Clip</code> you want to select.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successful otherwise <code>false</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="selectClipAt">
	<h5><a href="#selectClipAt">selectClipAt</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.LibrariesFilmstrip:selectClipAt(index) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Select clip at a specific index.</p>
<p>Parameters:</p>
<ul>
<li>index - A number of where the clip appears in the list.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successful otherwise <code>false</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="selectClipTitled">
	<h5><a href="#selectClipTitled">selectClipTitled</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.LibrariesFilmstrip:selectClipTitled(title) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Select clip with a specific title.</p>
<p>Parameters:</p>
<ul>
<li>title - The title of a clip.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successful otherwise <code>false</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="selectedClips">
	<h5><a href="#selectedClips">selectedClips</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.LibrariesFilmstrip:selectedClips() -&gt; table | nil</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets selected clips.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table of <code>Clip</code> objects or <code>nil</code> if no clips are selected.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="selectedClipsUI">
	<h5><a href="#selectedClipsUI">selectedClipsUI</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.LibrariesFilmstrip:selectedClipsUI() -&gt; table | nil</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets selected clips UI's.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table of <code>axuielementObject</code> objects or <code>nil</code> if no clips are selected.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="showClip">
	<h5><a href="#showClip">showClip</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.LibrariesFilmstrip:showClip(clip) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Shows a clip.</p>
<p>Parameters:</p>
<ul>
<li>clip - The <code>Clip</code> you want to show.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successful otherwise <code>false</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="showClipAt">
	<h5><a href="#showClipAt">showClipAt</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.LibrariesFilmstrip:showClipAt(index) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Shows a clip at a specific index.</p>
<p>Parameters:</p>
<ul>
<li>index - The index of the clip you want to show.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successful otherwise <code>false</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="sortClips">
	<h5><a href="#sortClips">sortClips</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.LibrariesFilmstrip.sortClips(a,b) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Determines if clip A is above clip B or not.</p>
<p>Parameters:</p>
<ul>
<li>a - Clip A</li>
<li>b - Clip B</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if clip A is above clip B, otherwise <code>false</code>.</li>
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
		<td><code>cp.apple.finalcutpro.main.LibrariesFilmstrip.new(app) -&gt; LibrariesFilmstrip</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constructor</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new <code>LibrariesFilmstrip</code> instance.</p>
<p>Parameters:</p>
<ul>
<li>parent - The parent object</li>
</ul>
<p>Returns:</p>
<ul>
<li>A new <code>LibrariesFilmstrip</code> object.</li>
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
		<td><code>cp.apple.finalcutpro.main.LibrariesFilmstrip:app() -&gt; App</code></td>
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
  <section id="parent">
	<h5><a href="#parent">parent</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.LibrariesFilmstrip:parent() -&gt; parent</code></td>
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
  <section id="playhead">
	<h5><a href="#playhead">playhead</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.LibrariesFilmstrip:playhead() -&gt; Playhead</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Get the Libraries Filmstrip Playhead.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>Playhead</code> object</li>
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
		<td><code>cp.apple.finalcutpro.main.LibrariesFilmstrip:show() -&gt; LibrariesFilmstrip</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Show the Libraries Filmstrip.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>LibrariesFilmstrip</code> object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="skimmingPlayhead">
	<h5><a href="#skimmingPlayhead">skimmingPlayhead</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.LibrariesFilmstrip:skimmingPlayhead() -&gt; Playhead</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Get the Libraries Filmstrip Skimming Playhead.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>Playhead</code> object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
