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
      <h1><a href="cp.apple.finalcutpro.main.GeneratorsBrowser.md">docs</a> &raquo; cp.apple.finalcutpro.main.GeneratorsBrowser</h1>
      <p>Generators Browser Module.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Constants - Useful values which cannot be changed</li>
          <ul>
            <li><a href="#TITLE">TITLE</a></li>
          </ul>
        <li>Variables - Configurable values</li>
          <ul>
            <li><a href="#isShowing">isShowing</a></li>
          </ul>
        <li>Constructors - API calls which return an object, typically one that offers API methods</li>
          <ul>
            <li><a href="#new">new</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#app">app</a></li>
            <li><a href="#applyItem">applyItem</a></li>
            <li><a href="#contents">contents</a></li>
            <li><a href="#currentItemsUI">currentItemsUI</a></li>
            <li><a href="#getCurrentTitles">getCurrentTitles</a></li>
            <li><a href="#getGeneratorsRowLabel">getGeneratorsRowLabel</a></li>
            <li><a href="#getTitlesRowLabel">getTitlesRowLabel</a></li>
            <li><a href="#group">group</a></li>
            <li><a href="#hide">hide</a></li>
            <li><a href="#itemIsSelected">itemIsSelected</a></li>
            <li><a href="#loadLayout">loadLayout</a></li>
            <li><a href="#mainGroupUI">mainGroupUI</a></li>
            <li><a href="#parent">parent</a></li>
            <li><a href="#saveLayout">saveLayout</a></li>
            <li><a href="#search">search</a></li>
            <li><a href="#selectedItemsUI">selectedItemsUI</a></li>
            <li><a href="#show">show</a></li>
            <li><a href="#showAllGenerators">showAllGenerators</a></li>
            <li><a href="#showAllTitles">showAllTitles</a></li>
            <li><a href="#showGeneratorsCategory">showGeneratorsCategory</a></li>
            <li><a href="#showInstalledGenerators">showInstalledGenerators</a></li>
            <li><a href="#showInstalledTitles">showInstalledTitles</a></li>
            <li><a href="#showSidebar">showSidebar</a></li>
            <li><a href="#showTitlesCategory">showTitlesCategory</a></li>
            <li><a href="#sidebar">sidebar</a></li>
            <li><a href="#topCategoriesUI">topCategoriesUI</a></li>
            <li><a href="#UI">UI</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Constants</h4>
          <section id="TITLE">
            <a name="//apple_ref/cpp/Constant/TITLE" class="dashAnchor"></a>
            <h5><a href="#TITLE">TITLE</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.GeneratorsBrowser.TITLE -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Titles &amp; Generators Title.</p>
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
                <td><code>cp.apple.finalcutpro.main.GeneratorsBrowser.isShowing &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Is the Generators Browser showing?</p>
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
                <td><code>cp.apple.finalcutpro.main.GeneratorsBrowser.new(parent) -&gt; GeneratorsBrowser</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new <code>GeneratorsBrowser</code> instance.</p>
<p>Parameters:</p>
<ul>
<li>app - The <code>cp.apple.finalcutpro</code> object.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A new <code>GeneratorsBrowser</code> object.</li>
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
                <td><code>cp.apple.finalcutpro.main.GeneratorsBrowser:app() -&gt; App</code></td>
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
                <td><code>cp.apple.finalcutpro.main.GeneratorsBrowser:applyItem(itemUI) -&gt; GeneratorsBrowser</code></td>
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
<li>The <code>GeneratorsBrowser</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="contents">
            <a name="//apple_ref/cpp/Method/contents" class="dashAnchor"></a>
            <h5><a href="#contents">contents</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.GeneratorsBrowser:contents() -&gt; ScrollArea</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the Generators Browser Contents.</p>
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
          <section id="currentItemsUI">
            <a name="//apple_ref/cpp/Method/currentItemsUI" class="dashAnchor"></a>
            <h5><a href="#currentItemsUI">currentItemsUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.GeneratorsBrowser:currentItemsUI() -&gt; axuielementObject</code></td>
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
                <td><code>cp.apple.finalcutpro.main.GeneratorsBrowser:getCurrentTitles() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the list of titles for all generators currently visible.</p>
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
          <section id="getGeneratorsRowLabel">
            <a name="//apple_ref/cpp/Method/getGeneratorsRowLabel" class="dashAnchor"></a>
            <h5><a href="#getGeneratorsRowLabel">getGeneratorsRowLabel</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.GeneratorsBrowser:getGeneratorsRowLabel() -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets a Generators Row Label.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The Generators Row Label as string.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="getTitlesRowLabel">
            <a name="//apple_ref/cpp/Method/getTitlesRowLabel" class="dashAnchor"></a>
            <h5><a href="#getTitlesRowLabel">getTitlesRowLabel</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.GeneratorsBrowser:getTitlesRowLabel() -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the label of the 'Titles' row in the current language.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The 'Titles' label.</li>
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
                <td><code>cp.apple.finalcutpro.main.GeneratorsBrowser:group() -&gt; PopUpButton</code></td>
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
                <td><code>cp.apple.finalcutpro.main.GeneratorsBrowser:hide() -&gt; GeneratorsBrowser</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Hides the Generators Browser.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>GeneratorsBrowser</code> instance.</li>
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
                <td><code>cp.apple.finalcutpro.main.GeneratorsBrowser:itemIsSelected(itemUI) -&gt; boolean</code></td>
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
                <td><code>cp.apple.finalcutpro.main.GeneratorsBrowser:loadLayout(layout) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Loads a Generators Browser layout.</p>
<p>Parameters:</p>
<ul>
<li>layout - A table containing the Generators Browser layout settings - created using <code>cp.apple.finalcutpro.main.GeneratorsBrowser:saveLayout()</code>.</li>
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
                <td><code>cp.apple.finalcutpro.main.GeneratorsBrowser:mainGroupUI() -&gt; axuielementObject</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Main Group UI.</p>
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
          <section id="parent">
            <a name="//apple_ref/cpp/Method/parent" class="dashAnchor"></a>
            <h5><a href="#parent">parent</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.GeneratorsBrowser:parent() -&gt; parent</code></td>
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
                <td><code>cp.apple.finalcutpro.main.GeneratorsBrowser:saveLayout() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Saves the current Generators Browser layout to a table.</p>
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
                <td><code>cp.apple.finalcutpro.main.GeneratorsBrowser:search() -&gt; PopUpButton</code></td>
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
                <td><code>cp.apple.finalcutpro.main.GeneratorsBrowser:selectedItemsUI() -&gt; axuielementObject</code></td>
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
                <td><code>cp.apple.finalcutpro.main.GeneratorsBrowser:show() -&gt; GeneratorsBrowser</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Shows the Generators Browser.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>GeneratorsBrowser</code> instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="showAllGenerators">
            <a name="//apple_ref/cpp/Method/showAllGenerators" class="dashAnchor"></a>
            <h5><a href="#showAllGenerators">showAllGenerators</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.GeneratorsBrowser:showAllGenerators() -&gt; GeneratorsBrowser</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Show All Generators.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>GeneratorsBrowser</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="showAllTitles">
            <a name="//apple_ref/cpp/Method/showAllTitles" class="dashAnchor"></a>
            <h5><a href="#showAllTitles">showAllTitles</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.GeneratorsBrowser:showAllTitles() -&gt; GeneratorsBrowser</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Ensures the sidebar is showing in the Generators &amp; Titles panel, focused on all 'Titles'.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>GeneratorsBrowser</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="showGeneratorsCategory">
            <a name="//apple_ref/cpp/Method/showGeneratorsCategory" class="dashAnchor"></a>
            <h5><a href="#showGeneratorsCategory">showGeneratorsCategory</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.GeneratorsBrowser:showGeneratorsCategory(name) -&gt; GeneratorsBrowser</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Show a specific Generators Category.</p>
<p>Parameters:</p>
<ul>
<li>name - The name of the Generators Category to show.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>GeneratorsBrowser</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="showInstalledGenerators">
            <a name="//apple_ref/cpp/Method/showInstalledGenerators" class="dashAnchor"></a>
            <h5><a href="#showInstalledGenerators">showInstalledGenerators</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.GeneratorsBrowser:showInstalledGenerators() -&gt; GeneratorsBrowser</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Ensures that the browser is showing 'Installed Generators'.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>GeneratorsBrowser</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="showInstalledTitles">
            <a name="//apple_ref/cpp/Method/showInstalledTitles" class="dashAnchor"></a>
            <h5><a href="#showInstalledTitles">showInstalledTitles</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.GeneratorsBrowser:showInstalledTitles() -&gt; GeneratorsBrowser</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Ensures that the browser is showing 'Installed Titles'.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>GeneratorsBrowser</code> object.</li>
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
                <td><code>cp.apple.finalcutpro.main.GeneratorsBrowser:showSidebar() -&gt; GeneratorsBrowser</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Ensures the sidebar is showing in the Generators &amp; Titles panel.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>GeneratorsBrowser</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="showTitlesCategory">
            <a name="//apple_ref/cpp/Method/showTitlesCategory" class="dashAnchor"></a>
            <h5><a href="#showTitlesCategory">showTitlesCategory</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.GeneratorsBrowser:showTitlesCategory(name) -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Ensures the sidebar is showing and that the selected 'Titles' category is selected, if available.</p>
<p>Parameters:</p>
<ul>
<li>name - The category name, in the current language.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The Generators Browser.</li>
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
                <td><code>cp.apple.finalcutpro.main.GeneratorsBrowser:sidebar() -&gt; Table</code></td>
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
          <section id="topCategoriesUI">
            <a name="//apple_ref/cpp/Method/topCategoriesUI" class="dashAnchor"></a>
            <h5><a href="#topCategoriesUI">topCategoriesUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.GeneratorsBrowser:topCategoriesUI() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns an array of the top-level categories in the sidebar.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The array of category rows.</li>
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
                <td><code>cp.apple.finalcutpro.main.GeneratorsBrowser:UI() -&gt; axuielementObject</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the Generator Browser UI.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>axuielementObject</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
