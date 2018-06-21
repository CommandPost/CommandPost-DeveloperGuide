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
      <h1><a href="cp.apple.finalcutpro.main.EffectsBrowser.md">docs</a> &raquo; cp.apple.finalcutpro.main.EffectsBrowser</h1>
      <p>Effects Browser Module.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Constants - Useful values which cannot be changed</li>
          <ul>
            <li><a href="#EFFECTS">EFFECTS</a></li>
            <li><a href="#TRANSITIONS">TRANSITIONS</a></li>
          </ul>
        <li>Variables - Configurable values</li>
          <ul>
            <li><a href="#isShowing">isShowing</a></li>
          </ul>
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
            <li><a href="#applyItem">applyItem</a></li>
            <li><a href="#audioCategoryRowsUI">audioCategoryRowsUI</a></li>
            <li><a href="#currentItemsUI">currentItemsUI</a></li>
            <li><a href="#getCurrentTitles">getCurrentTitles</a></li>
            <li><a href="#group">group</a></li>
            <li><a href="#hide">hide</a></li>
            <li><a href="#hideSidebar">hideSidebar</a></li>
            <li><a href="#itemIsSelected">itemIsSelected</a></li>
            <li><a href="#loadLayout">loadLayout</a></li>
            <li><a href="#mainGroupUI">mainGroupUI</a></li>
            <li><a href="#parent">parent</a></li>
            <li><a href="#saveLayout">saveLayout</a></li>
            <li><a href="#search">search</a></li>
            <li><a href="#selectedItemsUI">selectedItemsUI</a></li>
            <li><a href="#show">show</a></li>
            <li><a href="#showAllAudioEffects">showAllAudioEffects</a></li>
            <li><a href="#showAllEffects">showAllEffects</a></li>
            <li><a href="#showAllTransitions">showAllTransitions</a></li>
            <li><a href="#showAllVideoEffects">showAllVideoEffects</a></li>
            <li><a href="#showAudioCategory">showAudioCategory</a></li>
            <li><a href="#showInstalledEffects">showInstalledEffects</a></li>
            <li><a href="#showInstalledTransitions">showInstalledTransitions</a></li>
            <li><a href="#showSidebar">showSidebar</a></li>
            <li><a href="#showTransitionsCategory">showTransitionsCategory</a></li>
            <li><a href="#showVideoCategory">showVideoCategory</a></li>
            <li><a href="#sidebar">sidebar</a></li>
            <li><a href="#sidebarToggle">sidebarToggle</a></li>
            <li><a href="#toggleButton">toggleButton</a></li>
            <li><a href="#toggleSidebar">toggleSidebar</a></li>
            <li><a href="#type">type</a></li>
            <li><a href="#UI">UI</a></li>
            <li><a href="#videoCategoryRowsUI">videoCategoryRowsUI</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Constants</h4>
          <section id="EFFECTS">
            <a name="//apple_ref/cpp/Constant/EFFECTS" class="dashAnchor"></a>
            <h5><a href="#EFFECTS">EFFECTS</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser.EFFECTS -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Effects.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="TRANSITIONS">
            <a name="//apple_ref/cpp/Constant/TRANSITIONS" class="dashAnchor"></a>
            <h5><a href="#TRANSITIONS">TRANSITIONS</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser.TRANSITIONS -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Transitions.</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Variables</h4>
          <section id="isShowing">
            <a name="//apple_ref/cpp/Variable/isShowing" class="dashAnchor"></a>
            <h5><a href="#isShowing">isShowing</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser.isShowing &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Is the Effects Browser showing?</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Functions</h4>
          <section id="matches">
            <a name="//apple_ref/cpp/Function/matches" class="dashAnchor"></a>
            <h5><a href="#matches">matches</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser.matches(element) -&gt; boolean</code></td>
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
            <a name="//apple_ref/cpp/Constructor/new" class="dashAnchor"></a>
            <h5><a href="#new">new</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser.new(parent, type) -&gt; EffectsBrowser</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new <code>EffectsBrowser</code> instance.</p>
<p>Parameters:</p>
<ul>
<li>parent - The parent object.</li>
<li>type - A string determining whether the Effects Browser is for Effects (<code>cp.apple.finalcutpro.main.EffectsBrowser.EFFECTS</code>) or Transitions (<code>cp.apple.finalcutpro.main.EffectsBrowser.TRANSITIONS</code>).</li>
</ul>
<p>Returns:</p>
<ul>
<li>A new <code>EffectsBrowser</code> object.</li>
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
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser:app() -&gt; App</code></td>
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
          <section id="applyItem">
            <a name="//apple_ref/cpp/Method/applyItem" class="dashAnchor"></a>
            <h5><a href="#applyItem">applyItem</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser:applyItem(itemUI) -&gt; EffectsBrowser</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Applies an item by double clicking on it.</p>
<p>Parameters:</p>
<ul>
<li>itemUI - The <code>axuielementObject</code> of the item you want to apply.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>EffectsBrowser</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="audioCategoryRowsUI">
            <a name="//apple_ref/cpp/Method/audioCategoryRowsUI" class="dashAnchor"></a>
            <h5><a href="#audioCategoryRowsUI">audioCategoryRowsUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser:audioCategoryRowsUI() -&gt; axuielementObject</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the Audio Category Rows UI.</p>
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
          <section id="currentItemsUI">
            <a name="//apple_ref/cpp/Method/currentItemsUI" class="dashAnchor"></a>
            <h5><a href="#currentItemsUI">currentItemsUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser:currentItemsUI() -&gt; axuielementObject</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the current items UI.</p>
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
          <section id="getCurrentTitles">
            <a name="//apple_ref/cpp/Method/getCurrentTitles" class="dashAnchor"></a>
            <h5><a href="#getCurrentTitles">getCurrentTitles</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser:getCurrentTitles() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the list of titles for all effects/transitions currently visible.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="group">
            <a name="//apple_ref/cpp/Method/group" class="dashAnchor"></a>
            <h5><a href="#group">group</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser:group() -&gt; PopUpButton</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the group.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A <code>PopUpButton</code> object.</li>
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
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser:hide() -&gt; EffectsBrowser</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Hide the Effects Browser.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>EffectsBrowser</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="hideSidebar">
            <a name="//apple_ref/cpp/Method/hideSidebar" class="dashAnchor"></a>
            <h5><a href="#hideSidebar">hideSidebar</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser:hideSidebar() -&gt; EffectsBrowser</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Hide Sidebar.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>EffectsBrowser</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="itemIsSelected">
            <a name="//apple_ref/cpp/Method/itemIsSelected" class="dashAnchor"></a>
            <h5><a href="#itemIsSelected">itemIsSelected</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser:itemIsSelected(itemUI) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks to see if an item is selected.</p>
<p>Parameters:</p>
<ul>
<li>itemUI - A <code>axuielementObject</code> to check.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the item is selected, otherwise <code>false</code>.</li>
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
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser:loadLayout(layout) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Loads a Effects Browser layout.</p>
<p>Parameters:</p>
<ul>
<li>layout - A table containing the Effects Browser layout settings - created using <code>cp.apple.finalcutpro.main.Browser:saveLayout()</code>.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="mainGroupUI">
            <a name="//apple_ref/cpp/Method/mainGroupUI" class="dashAnchor"></a>
            <h5><a href="#mainGroupUI">mainGroupUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser:mainGroupUI() -&gt; ScrollArea</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the Effects Browser Contents.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A <code>ScrollArea</code> object.</li>
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
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser:parent() -&gt; parent</code></td>
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
            <a name="//apple_ref/cpp/Method/saveLayout" class="dashAnchor"></a>
            <h5><a href="#saveLayout">saveLayout</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser:saveLayout() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Saves the current Effects Browser layout to a table.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table containing the current Effects Browser Layout.</li>
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
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser:search() -&gt; PopUpButton</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the Search Popup Button object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A <code>PopUpButton</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="selectedItemsUI">
            <a name="//apple_ref/cpp/Method/selectedItemsUI" class="dashAnchor"></a>
            <h5><a href="#selectedItemsUI">selectedItemsUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser:selectedItemsUI() -&gt; axuielementObject</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the selected items UI.</p>
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
            <a name="//apple_ref/cpp/Method/show" class="dashAnchor"></a>
            <h5><a href="#show">show</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser:show() -&gt; EffectsBrowser</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Show the Effects Browser.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>EffectsBrowser</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="showAllAudioEffects">
            <a name="//apple_ref/cpp/Method/showAllAudioEffects" class="dashAnchor"></a>
            <h5><a href="#showAllAudioEffects">showAllAudioEffects</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser:showAllAudioEffects() -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Show All Audio Effects.</p>
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
          <section id="showAllEffects">
            <a name="//apple_ref/cpp/Method/showAllEffects" class="dashAnchor"></a>
            <h5><a href="#showAllEffects">showAllEffects</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser:showAllEffects() -&gt; EffectsBrowser</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Show All Effects.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>EffectsBrowser</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="showAllTransitions">
            <a name="//apple_ref/cpp/Method/showAllTransitions" class="dashAnchor"></a>
            <h5><a href="#showAllTransitions">showAllTransitions</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser:showAllTransitions() -&gt; EffectsBrowser</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Show All Transitions.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>EffectsBrowser</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="showAllVideoEffects">
            <a name="//apple_ref/cpp/Method/showAllVideoEffects" class="dashAnchor"></a>
            <h5><a href="#showAllVideoEffects">showAllVideoEffects</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser:showAllVideoEffects() -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Show All Video Effects.</p>
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
          <section id="showAudioCategory">
            <a name="//apple_ref/cpp/Method/showAudioCategory" class="dashAnchor"></a>
            <h5><a href="#showAudioCategory">showAudioCategory</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser:showAudioCategory(name) -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Ensures the sidebar is showing and that the selected 'Audio' category is selected, if available.</p>
<p>Parameters:</p>
<ul>
<li><code>name</code>        - The category name, in the current language.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The browser.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="showInstalledEffects">
            <a name="//apple_ref/cpp/Method/showInstalledEffects" class="dashAnchor"></a>
            <h5><a href="#showInstalledEffects">showInstalledEffects</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser:showInstalledEffects() -&gt; EffectsBrowser</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Show Installed Effects.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>EffectsBrowser</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="showInstalledTransitions">
            <a name="//apple_ref/cpp/Method/showInstalledTransitions" class="dashAnchor"></a>
            <h5><a href="#showInstalledTransitions">showInstalledTransitions</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser:showInstalledTransitions() -&gt; EffectsBrowser</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Show Installed Transitions.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>EffectsBrowser</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="showSidebar">
            <a name="//apple_ref/cpp/Method/showSidebar" class="dashAnchor"></a>
            <h5><a href="#showSidebar">showSidebar</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser:showSidebar() -&gt; EffectsBrowser</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Show Sidebar.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>EffectsBrowser</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="showTransitionsCategory">
            <a name="//apple_ref/cpp/Method/showTransitionsCategory" class="dashAnchor"></a>
            <h5><a href="#showTransitionsCategory">showTransitionsCategory</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser:showTransitionsCategory(name) -&gt; EffectsBrowser</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Ensures the sidebar is showing and that the selected 'Transitions' category is selected, if available.</p>
<p>Parameters:</p>
<ul>
<li>name - The category name, in the current language.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>EffectsBrowser</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="showVideoCategory">
            <a name="//apple_ref/cpp/Method/showVideoCategory" class="dashAnchor"></a>
            <h5><a href="#showVideoCategory">showVideoCategory</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser:showVideoCategory(name) -&gt; EffectsBrowser</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Ensures the sidebar is showing and that the selected 'Video' category is selected, if available.</p>
<p>Parameters:</p>
<ul>
<li>name - The category name, in the current language.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>EffectsBrowser</code> object.</li>
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
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser:sidebar() -&gt; Table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the sidebar object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A <code>Table</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="sidebarToggle">
            <a name="//apple_ref/cpp/Method/sidebarToggle" class="dashAnchor"></a>
            <h5><a href="#sidebarToggle">sidebarToggle</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser:sidebarToggle() -&gt; CheckBox</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the Sidebar Toggle.</p>
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
          <section id="toggleButton">
            <a name="//apple_ref/cpp/Method/toggleButton" class="dashAnchor"></a>
            <h5><a href="#toggleButton">toggleButton</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser:toggleButton() -&gt; RadioButton</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the Effects Browser Toggle Button.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A <code>RadioButton</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="toggleSidebar">
            <a name="//apple_ref/cpp/Method/toggleSidebar" class="dashAnchor"></a>
            <h5><a href="#toggleSidebar">toggleSidebar</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser:toggleSidebar() -&gt; EffectsBrowser</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Toggle Sidebar.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>EffectsBrowser</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="type">
            <a name="//apple_ref/cpp/Method/type" class="dashAnchor"></a>
            <h5><a href="#type">type</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser:type() -&gt; App</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Type of Effects Browser.</p>
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
          <section id="UI">
            <a name="//apple_ref/cpp/Method/UI" class="dashAnchor"></a>
            <h5><a href="#UI">UI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser:UI() -&gt; axuielementObject</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The Effects Browser UI.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>axuielementObject</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="videoCategoryRowsUI">
            <a name="//apple_ref/cpp/Method/videoCategoryRowsUI" class="dashAnchor"></a>
            <h5><a href="#videoCategoryRowsUI">videoCategoryRowsUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.EffectsBrowser:videoCategoryRowsUI() -&gt; axuielementObject</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the Video Category Rows UI.</p>
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
