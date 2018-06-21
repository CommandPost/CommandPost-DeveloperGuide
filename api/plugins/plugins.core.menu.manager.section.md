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
      <h1><a href="plugins.core.menu.manager.section.md">docs</a> &raquo; plugins.core.menu.manager.section</h1>
      <p>Controls sections for the CommandPost menu.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Constants - Useful values which cannot be changed</li>
          <ul>
            <li><a href="#DEFAULT_PRIORITY">DEFAULT_PRIORITY</a></li>
            <li><a href="#WARNING_LIMIT">WARNING_LIMIT</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#_addGenerator">_addGenerator</a></li>
            <li><a href="#addItem">addItem</a></li>
            <li><a href="#addItems">addItems</a></li>
            <li><a href="#addMenu">addMenu</a></li>
            <li><a href="#addSection">addSection</a></li>
            <li><a href="#addSeparator">addSeparator</a></li>
            <li><a href="#generateTable">generateTable</a></li>
            <li><a href="#isDisabled">isDisabled</a></li>
            <li><a href="#new">new</a></li>
            <li><a href="#setDisabledFn">setDisabledFn</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Constants</h4>
          <section id="DEFAULT_PRIORITY">
            <a name="//apple_ref/cpp/Constant/DEFAULT_PRIORITY" class="dashAnchor"></a>
            <h5><a href="#DEFAULT_PRIORITY">DEFAULT_PRIORITY</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.menu.manager.section.DEFAULT_PRIORITY -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The default priority</p>
</td>
              </tr>
            </table>
          </section>
          <section id="WARNING_LIMIT">
            <a name="//apple_ref/cpp/Constant/WARNING_LIMIT" class="dashAnchor"></a>
            <h5><a href="#WARNING_LIMIT">WARNING_LIMIT</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.menu.manager.section.WARNING_LIMIT -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The limit of how much time a menu item takes to load before we post warnings to the Error Log</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Methods</h4>
          <section id="_addGenerator">
            <a name="//apple_ref/cpp/Method/_addGenerator" class="dashAnchor"></a>
            <h5><a href="#_addGenerator">_addGenerator</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.menu.manager.section:_addGenerator() -&gt; section</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>A private method for registering a generator. This should not be called directly.</p>
<p>Parameters:</p>
<ul>
<li><code>generator</code>  - The generator being added.</li>
</ul>
<p>Returns:</p>
<ul>
<li>section - The section.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="addItem">
            <a name="//apple_ref/cpp/Method/addItem" class="dashAnchor"></a>
            <h5><a href="#addItem">addItem</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.menu.manager.section:addItem(priority, itemFn) -&gt; section</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Registers a function which will generate a single table item.</p>
<p>Parameters:</p>
<ul>
<li><code>priority</code>   - The priority of the item within the section. Lower numbers appear first.</li>
<li><code>itemFn</code>     - A function which will return a table representing a single menu item. See <code>hs.menubar</code> for details.</li>
</ul>
<p>Returns:</p>
<ul>
<li>section - The section the item was added to.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="addItems">
            <a name="//apple_ref/cpp/Method/addItems" class="dashAnchor"></a>
            <h5><a href="#addItems">addItems</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.menu.manager.section:addItems(priority, itemsFn) -&gt; section</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Registers a function which will generate multiple table items.</p>
<p>Parameters:</p>
<ul>
<li><code>priority</code>   - The priority of the items within the section. Lower numbers appear first.</li>
<li><code>itemsFn</code>    - A function which will return a table containing multiple table items. See <code>hs.menubar</code> for details.</li>
</ul>
<p>Returns:</p>
<ul>
<li>section - The section the item was added to.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="addMenu">
            <a name="//apple_ref/cpp/Method/addMenu" class="dashAnchor"></a>
            <h5><a href="#addMenu">addMenu</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.menu.manager.section:addMenu(priority, titleFn) -&gt; section</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Adds a new sub-menu with the specified priority. The section that will contain
the items in the menu is returned.</p>
<p>Parameters:</p>
<ul>
<li><code>priority</code>   - The priority of the item within the section. Lower numbers appear first.</li>
<li><code>titleFn</code>    - The function which will return the menu title.</li>
</ul>
<p>Returns:</p>
<ul>
<li>section - The new section that was created.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="addSection">
            <a name="//apple_ref/cpp/Method/addSection" class="dashAnchor"></a>
            <h5><a href="#addSection">addSection</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.menu.manager.section:addSection(priority, itemFn) -&gt; section</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Adds a new sub-section with the specified priority. The new sub-section is returned.</p>
<p>Parameters:</p>
<ul>
<li><code>priority</code>   - The priority of the item within the section. Lower numbers appear first.</li>
</ul>
<p>Returns:</p>
<ul>
<li>section - The new section that was created.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="addSeparator">
            <a name="//apple_ref/cpp/Method/addSeparator" class="dashAnchor"></a>
            <h5><a href="#addSeparator">addSeparator</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.menu.manager.section:addSeparator(priority) -&gt; section</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Adds a new seperator with specified priority.</p>
<p>Parameters:</p>
<ul>
<li><code>priority</code>   - The priority of the items within the section. Lower numbers appear first.</li>
</ul>
<p>Returns:</p>
<ul>
<li>section - The new section that was created.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="generateTable">
            <a name="//apple_ref/cpp/Method/generateTable" class="dashAnchor"></a>
            <h5><a href="#generateTable">generateTable</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.menu.manager.section:generateTable() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Generates a new menu table based on the registered items and sections inside this section.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>table</code>  - The menu table for this section. See <code>hs.menubar</code> for details on the format.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="isDisabled">
            <a name="//apple_ref/cpp/Method/isDisabled" class="dashAnchor"></a>
            <h5><a href="#isDisabled">isDisabled</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.menu.manager.section:isDisabled() -&gt; voolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the disabled status</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the section is disabled, otherwise <code>false</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="new">
            <a name="//apple_ref/cpp/Method/new" class="dashAnchor"></a>
            <h5><a href="#new">new</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.menu.manager.section:new() -&gt; section</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new menu section, which can have items and sub-menus added to it.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>section - The section that was created.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="setDisabledFn">
            <a name="//apple_ref/cpp/Method/setDisabledFn" class="dashAnchor"></a>
            <h5><a href="#setDisabledFn">setDisabledFn</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.menu.manager.section:setDisabledFn(disabledFn) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Sets the Disabled Function</p>
<p>Parameters:</p>
<ul>
<li>disabledFn - The disabled function.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
