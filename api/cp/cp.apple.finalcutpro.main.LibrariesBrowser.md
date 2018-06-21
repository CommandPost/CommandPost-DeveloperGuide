    <style type="text/css">
      a { text-decoration: none; }
      a:hover { text-decoration: underline; }
      th { background-color: #DDDDDD; vertical-align: top; padding: 3px; }
      td { width: 100%; background-color: #EEEEEE; vertical-align: top; padding: 3px; }
      table { width: 100% ; border: 1px solid #0; text-align: left; }
      section > table table td { width: 0; }
    </style>
    <link rel="stylesheet" href="../../css/docs.css" type="text/css" media="screen" />
    <header>
      <h1><a href="cp.apple.finalcutpro.main.LibrariesBrowser.md">docs</a> &raquo; cp.apple.finalcutpro.main.LibrariesBrowser</h1>
      <p>Libraries Browser Module.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Constants - Useful values which cannot be changed</li>
          <ul>
            <li><a href="#ALL_CLIPS">ALL_CLIPS</a></li>
            <li><a href="#FAVORITES">FAVORITES</a></li>
            <li><a href="#HIDE_REJECTED">HIDE_REJECTED</a></li>
            <li><a href="#NO_RATINGS_OR_KEYWORDS">NO_RATINGS_OR_KEYWORDS</a></li>
            <li><a href="#REJECTED">REJECTED</a></li>
            <li><a href="#UNUSED">UNUSED</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#clips">clips</a></li>
            <li><a href="#clipsUI">clipsUI</a></li>
            <li><a href="#deselectAll">deselectAll</a></li>
            <li><a href="#matchesSidebar">matchesSidebar</a></li>
            <li><a href="#openClipTitled">openClipTitled</a></li>
            <li><a href="#selectAll">selectAll</a></li>
            <li><a href="#selectClip">selectClip</a></li>
            <li><a href="#selectClipAt">selectClipAt</a></li>
            <li><a href="#selectClipTitled">selectClipTitled</a></li>
            <li><a href="#selectedClips">selectedClips</a></li>
            <li><a href="#selectedClipsUI">selectedClipsUI</a></li>
            <li><a href="#selectLibrary">selectLibrary</a></li>
            <li><a href="#showClip">showClip</a></li>
          </ul>
        <li>Constructors - API calls which return an object, typically one that offers API methods</li>
          <ul>
            <li><a href="#new">new</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#app">app</a></li>
            <li><a href="#appearanceAndFiltering">appearanceAndFiltering</a></li>
            <li><a href="#filmstrip">filmstrip</a></li>
            <li><a href="#filterToggle">filterToggle</a></li>
            <li><a href="#hide">hide</a></li>
            <li><a href="#loadLayout">loadLayout</a></li>
            <li><a href="#parent">parent</a></li>
            <li><a href="#playhead">playhead</a></li>
            <li><a href="#saveLayout">saveLayout</a></li>
            <li><a href="#search">search</a></li>
            <li><a href="#searchToggle">searchToggle</a></li>
            <li><a href="#selectClipFiltering">selectClipFiltering</a></li>
            <li><a href="#show">show</a></li>
            <li><a href="#sidebar">sidebar</a></li>
            <li><a href="#skimmingPlayhead">skimmingPlayhead</a></li>
            <li><a href="#toggleViewMode">toggleViewMode</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Constants</h4>
          <section id="ALL_CLIPS">
            <a name="//apple_ref/cpp/Constant/ALL_CLIPS" class="dashAnchor"></a>
            <h5><a href="#ALL_CLIPS">ALL_CLIPS</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.LibrariesBrowser.ALL_CLIPS -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>All Clips ID.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="FAVORITES">
            <a name="//apple_ref/cpp/Constant/FAVORITES" class="dashAnchor"></a>
            <h5><a href="#FAVORITES">FAVORITES</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.LibrariesBrowser.FAVORITES -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Favourites ID.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="HIDE_REJECTED">
            <a name="//apple_ref/cpp/Constant/HIDE_REJECTED" class="dashAnchor"></a>
            <h5><a href="#HIDE_REJECTED">HIDE_REJECTED</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.LibrariesBrowser.HIDE_REJECTED -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Hide Rejected ID.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="NO_RATINGS_OR_KEYWORDS">
            <a name="//apple_ref/cpp/Constant/NO_RATINGS_OR_KEYWORDS" class="dashAnchor"></a>
            <h5><a href="#NO_RATINGS_OR_KEYWORDS">NO_RATINGS_OR_KEYWORDS</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.LibrariesBrowser.NO_RATINGS_OR_KEYWORDS -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>No Rating or Keywords ID.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="REJECTED">
            <a name="//apple_ref/cpp/Constant/REJECTED" class="dashAnchor"></a>
            <h5><a href="#REJECTED">REJECTED</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.LibrariesBrowser.REJECTED -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Rejected ID.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="UNUSED">
            <a name="//apple_ref/cpp/Constant/UNUSED" class="dashAnchor"></a>
            <h5><a href="#UNUSED">UNUSED</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.LibrariesBrowser.UNUSED -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Unused ID.</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Functions</h4>
          <section id="clips">
            <a name="//apple_ref/cpp/Function/clips" class="dashAnchor"></a>
            <h5><a href="#clips">clips</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.LibrariesBrowser:clips(filterFn) -&gt; table | nil</code></td>
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
            <a name="//apple_ref/cpp/Function/clipsUI" class="dashAnchor"></a>
            <h5><a href="#clipsUI">clipsUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.LibrariesBrowser:clipsUI(filterFn) -&gt; table | nil</code></td>
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
            <a name="//apple_ref/cpp/Function/deselectAll" class="dashAnchor"></a>
            <h5><a href="#deselectAll">deselectAll</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.LibrariesBrowser:deselectAll() -&gt; boolean</code></td>
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
          <section id="matchesSidebar">
            <a name="//apple_ref/cpp/Function/matchesSidebar" class="dashAnchor"></a>
            <h5><a href="#matchesSidebar">matchesSidebar</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.LibrariesBrowser.matchesSidebar(element) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks to see if an element matches the Sidebar type.</p>
<p>Parameters:</p>
<ul>
<li>element - The element to check.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if there's a match, otherwise <code>false</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="openClipTitled">
            <a name="//apple_ref/cpp/Function/openClipTitled" class="dashAnchor"></a>
            <h5><a href="#openClipTitled">openClipTitled</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.LibrariesBrowser:openClipTitled(name) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Open a clip with a specific title.</p>
<p>Parameters:</p>
<ul>
<li>name - The name of the clip you want to open.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successful, otherwise <code>false</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="selectAll">
            <a name="//apple_ref/cpp/Function/selectAll" class="dashAnchor"></a>
            <h5><a href="#selectAll">selectAll</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.LibrariesBrowser:selectAll([clips]) -&gt; boolean</code></td>
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
            <a name="//apple_ref/cpp/Function/selectClip" class="dashAnchor"></a>
            <h5><a href="#selectClip">selectClip</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.LibrariesBrowser:selectClip(clip) -&gt; boolean</code></td>
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
            <a name="//apple_ref/cpp/Function/selectClipAt" class="dashAnchor"></a>
            <h5><a href="#selectClipAt">selectClipAt</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.LibrariesBrowser:selectClipAt(index) -&gt; boolean</code></td>
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
            <a name="//apple_ref/cpp/Function/selectClipTitled" class="dashAnchor"></a>
            <h5><a href="#selectClipTitled">selectClipTitled</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.LibrariesBrowser:selectClipTitled(title) -&gt; boolean</code></td>
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
            <a name="//apple_ref/cpp/Function/selectedClips" class="dashAnchor"></a>
            <h5><a href="#selectedClips">selectedClips</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.LibrariesBrowser:selectedClips() -&gt; table | nil</code></td>
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
            <a name="//apple_ref/cpp/Function/selectedClipsUI" class="dashAnchor"></a>
            <h5><a href="#selectedClipsUI">selectedClipsUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.LibrariesBrowser:selectedClipsUI() -&gt; table | nil</code></td>
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
          <section id="selectLibrary">
            <a name="//apple_ref/cpp/Function/selectLibrary" class="dashAnchor"></a>
            <h5><a href="#selectLibrary">selectLibrary</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.LibrariesBrowser:selectLibrary(...) -&gt; Table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Selects a Library.</p>
<p>Parameters:</p>
<ul>
<li>... - Libraries as string.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A <code>Table</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="showClip">
            <a name="//apple_ref/cpp/Function/showClip" class="dashAnchor"></a>
            <h5><a href="#showClip">showClip</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.LibrariesBrowser:showClip(clip) -&gt; boolean</code></td>
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
        <h4 class="documentation-section">Constructors</h4>
          <section id="new">
            <a name="//apple_ref/cpp/Constructor/new" class="dashAnchor"></a>
            <h5><a href="#new">new</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.LibrariesBrowser.new(app) -&gt; LibrariesBrowser</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new <code>LibrariesBrowser</code> instance.</p>
<p>Parameters:</p>
<ul>
<li>parent - The parent object.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A new <code>LibrariesBrowser</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Methods</h4>
          <section id="app">
            <a name="//apple_ref/cpp/Method/app" class="dashAnchor"></a>
            <h5><a href="#app">app</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.LibrariesBrowser:app() -&gt; App</code></td>
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
          <section id="appearanceAndFiltering">
            <a name="//apple_ref/cpp/Method/appearanceAndFiltering" class="dashAnchor"></a>
            <h5><a href="#appearanceAndFiltering">appearanceAndFiltering</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.LibrariesBrowser:appearanceAndFiltering() -&gt; Button</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Get Appearance &amp; Filtering Button.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>Button</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="filmstrip">
            <a name="//apple_ref/cpp/Method/filmstrip" class="dashAnchor"></a>
            <h5><a href="#filmstrip">filmstrip</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.LibrariesBrowser:filmstrip() -&gt; LibrariesList</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Get Libraries List object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>LibrariesList</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="filterToggle">
            <a name="//apple_ref/cpp/Method/filterToggle" class="dashAnchor"></a>
            <h5><a href="#filterToggle">filterToggle</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.LibrariesBrowser:filterToggle() -&gt; Button</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The Filter Toggle Button.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>Button</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="hide">
            <a name="//apple_ref/cpp/Method/hide" class="dashAnchor"></a>
            <h5><a href="#hide">hide</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.LibrariesBrowser:hide() -&gt; LibrariesBrowser</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Hide the Libraries Browser.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>LibrariesBrowser</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="loadLayout">
            <a name="//apple_ref/cpp/Method/loadLayout" class="dashAnchor"></a>
            <h5><a href="#loadLayout">loadLayout</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.LibrariesBrowser:loadLayout(layout) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Loads a Libraries Browser layout.</p>
<p>Parameters:</p>
<ul>
<li>layout - A table containing the Libraries Browser layout settings - created using <code>cp.apple.finalcutpro.main.LibrariesBrowser:saveLayout()</code>.</li>
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
            <a name="//apple_ref/cpp/Method/parent" class="dashAnchor"></a>
            <h5><a href="#parent">parent</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.LibrariesBrowser:parent() -&gt; parent</code></td>
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
            <a name="//apple_ref/cpp/Method/playhead" class="dashAnchor"></a>
            <h5><a href="#playhead">playhead</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.LibrariesBrowser:playhead() -&gt; Playhead</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the Libraries Browser Playhead.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A <code>Playhead</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="saveLayout">
            <a name="//apple_ref/cpp/Method/saveLayout" class="dashAnchor"></a>
            <h5><a href="#saveLayout">saveLayout</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.LibrariesBrowser:saveLayout() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Saves the current Libraries Browser layout to a table.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table containing the current Libraries Browser Layout.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="search">
            <a name="//apple_ref/cpp/Method/search" class="dashAnchor"></a>
            <h5><a href="#search">search</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.LibrariesBrowser:search() -&gt; TextField</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Get Search Text Field.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>TextField</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="searchToggle">
            <a name="//apple_ref/cpp/Method/searchToggle" class="dashAnchor"></a>
            <h5><a href="#searchToggle">searchToggle</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.LibrariesBrowser:searchToggle() -&gt; Button</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Get Search Toggle Button.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>Button</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="selectClipFiltering">
            <a name="//apple_ref/cpp/Method/selectClipFiltering" class="dashAnchor"></a>
            <h5><a href="#selectClipFiltering">selectClipFiltering</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.LibrariesBrowser:selectClipFiltering(filterType) -&gt; LibrariesBrowser</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Select Clip Filtering based on Filter Type.</p>
<p>Parameters:</p>
<ul>
<li>filterType - The filter type.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>LibrariesBrowser</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="show">
            <a name="//apple_ref/cpp/Method/show" class="dashAnchor"></a>
            <h5><a href="#show">show</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.LibrariesBrowser:show() -&gt; LibrariesBrowser</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Show the Libraries Browser.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>LibrariesBrowser</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="sidebar">
            <a name="//apple_ref/cpp/Method/sidebar" class="dashAnchor"></a>
            <h5><a href="#sidebar">sidebar</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.LibrariesBrowser:sidebar() -&gt; Table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Get Libraries sidebar object.</p>
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
          <section id="skimmingPlayhead">
            <a name="//apple_ref/cpp/Method/skimmingPlayhead" class="dashAnchor"></a>
            <h5><a href="#skimmingPlayhead">skimmingPlayhead</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.LibrariesBrowser:skimmingPlayhead() -&gt; Playhead</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the Libraries Browser Skimming Playhead.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A <code>Playhead</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="toggleViewMode">
            <a name="//apple_ref/cpp/Method/toggleViewMode" class="dashAnchor"></a>
            <h5><a href="#toggleViewMode">toggleViewMode</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.LibrariesBrowser:toggleViewMode() -&gt; Button</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Get Toggle View Mode button.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>Button</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
