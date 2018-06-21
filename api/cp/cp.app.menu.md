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
      <h1><a href="cp.app.menu.md">docs</a> &raquo; cp.app.menu</h1>
      <p>Represents an app's menu bar, providing multi-lingual access to find and
trigger menu items.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Constants - Useful values which cannot be changed</li>
          <ul>
            <li><a href="#NIB_FILE">NIB_FILE</a></li>
            <li><a href="#ROLE">ROLE</a></li>
          </ul>
        <li>Constructors - API calls which return an object, typically one that offers API methods</li>
          <ul>
            <li><a href="#new">new</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#addMenuFinder">addMenuFinder</a></li>
            <li><a href="#app">app</a></li>
            <li><a href="#findMenuItems">findMenuItems</a></li>
            <li><a href="#findMenuItemsUI">findMenuItemsUI</a></li>
            <li><a href="#findMenuUI">findMenuUI</a></li>
            <li><a href="#findUI">findUI</a></li>
            <li><a href="#getMenuTitles">getMenuTitles</a></li>
            <li><a href="#isChecked">isChecked</a></li>
            <li><a href="#isEnabled">isEnabled</a></li>
            <li><a href="#selectMenu">selectMenu</a></li>
            <li><a href="#selectMenuItem">selectMenuItem</a></li>
            <li><a href="#visitMenuItems">visitMenuItems</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Constants</h4>
          <section id="NIB_FILE">
            <a name="//apple_ref/cpp/Constant/NIB_FILE" class="dashAnchor"></a>
            <h5><a href="#NIB_FILE">NIB_FILE</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.app.menu.NIB_FILE -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Main NIB File.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="ROLE">
            <a name="//apple_ref/cpp/Constant/ROLE" class="dashAnchor"></a>
            <h5><a href="#ROLE">ROLE</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.app.menu.ROLE -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The menu role</p>
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
                <td><code>cp.app.menu.new(app) -&gt; menu</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Constructs a new menu for the specified App.</p>
<p>Parameters:</p>
<ul>
<li>app - The <code>cp.app</code> instance the menu belongs to.</li>
</ul>
<p>Returns:</p>
<ul>
<li>a new menu instance</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Methods</h4>
          <section id="addMenuFinder">
            <a name="//apple_ref/cpp/Method/addMenuFinder" class="dashAnchor"></a>
            <h5><a href="#addMenuFinder">addMenuFinder</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.app.menu:addMenuFinder(finder) -&gt; nothing</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Registers an <code>AXMenuItem</code> finder function. The finder's job is to take an individual 'find' step and return either the matching child, or nil if it can't be found. It is used by the <a href="#addMenuFinder">addMenuFinder</a> function. The <code>finder</code> should have the following signature:</p>
<div class="highlight"><pre><span></span><span class="kr">function</span><span class="p">(</span><span class="n">parentItem</span><span class="p">,</span> <span class="n">path</span><span class="p">,</span> <span class="n">childName</span><span class="p">,</span> <span class="n">locale</span><span class="p">)</span> <span class="o">-&gt;</span> <span class="n">childItem</span>
</pre></div>
<p>The elements are:</p>
<ul>
<li>parentItem    - The <code>AXMenuItem</code> containing the children. E.g. the <code>Go To</code> menu under <code>Window</code>.</li>
<li>path          - An array of strings in the specified locale leading to the parent item. E.g. <code>{"Window", "Go To"}</code>.</li>
<li>childName     - The name of the next child to find, in the specified locale. E.g. <code>"Libraries"</code>.</li>
<li>locale        - The <code>cp.i18n.localeID</code> that the menu titles are in.</li>
<li>childItem     - The <code>AXMenuItem</code> that was found, or <code>nil</code> if not found.</li>
</ul>
<p>Parameters:</p>
<ul>
<li><code>finder</code>     - The finder function</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>AXMenuItem</code> found, or <code>nil</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="app">
            <a name="//apple_ref/cpp/Method/app" class="dashAnchor"></a>
            <h5><a href="#app">app</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.app.menu:app() -&gt; cp.app</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the <code>cp.app</code> instance this belongs to.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.app</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="findMenuItems">
            <a name="//apple_ref/cpp/Method/findMenuItems" class="dashAnchor"></a>
            <h5><a href="#findMenuItems">findMenuItems</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.app.menu:findMenuItems(path[, options]) -&gt; cp.rx.Observable &lt;hs._asm.axuielement&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns an <code>Observable</code> that will emit each of the menu items along the path.</p>
<p>Each step on the path can be either one of:</p>
<ul>
<li>a string     - The exact name of the menu item.</li>
<li>a number     - The menu item number, starting from 1.</li>
<li>a function   - Passed one argument - the Menu UI to check - returning <code>true</code> if it matches.</li>
</ul>
<p>Options:</p>
<ul>
<li>locale   - The locale that any strings in the path are in. Defaults to "en".</li>
<li>timeout  - The amount of time to wait for the menu to become available. Defaults to 10 seconds.</li>
</ul>
<p>Examples:</p>
<div class="highlight"><pre><span></span><span class="c1">-- check if the final item is enabled</span>
<span class="n">myApp</span><span class="p">:</span><span class="n">menu</span><span class="p">():</span><span class="n">findMenuItems</span><span class="p">({</span><span class="s2">&quot;Edit&quot;</span><span class="p">,</span> <span class="s2">&quot;Copy&quot;</span><span class="p">}):</span><span class="n">last</span><span class="p">():</span><span class="n">subscribe</span><span class="p">(</span><span class="kr">function</span><span class="p">(</span><span class="n">item</span><span class="p">)</span> <span class="nb">print</span><span class="p">(</span><span class="s2">&quot;Copy Enabled: &quot;</span><span class="p">,</span> <span class="n">item</span><span class="p">:</span><span class="n">enabled</span><span class="p">())</span> <span class="kr">end</span><span class="p">)</span>

<span class="c1">-- check if all items are enabled</span>
<span class="n">myApp</span><span class="p">:</span><span class="n">menu</span><span class="p">():</span><span class="n">findMenuItems</span><span class="p">({</span><span class="s2">&quot;Edit&quot;</span><span class="p">,</span> <span class="s2">&quot;Copy&quot;</span><span class="p">}):</span><span class="n">all</span><span class="p">(</span><span class="kr">function</span><span class="p">(</span><span class="n">item</span><span class="p">)</span> <span class="kr">return</span> <span class="n">item</span><span class="p">:</span><span class="n">enabled</span><span class="p">()</span> <span class="kr">end</span><span class="p">):</span><span class="n">subscribe</span><span class="p">(</span><span class="kr">function</span><span class="p">(</span><span class="n">enabled</span><span class="p">)</span> <span class="nb">print</span><span class="p">(</span><span class="s2">&quot;All Enabled: &quot;</span><span class="p">,</span> <span class="n">enabled</span><span class="p">)</span> <span class="kr">end</span><span class="p">)</span>
</pre></div>
<p>Parameters:</p>
<ul>
<li>path         - the table of path items.</li>
<li>options      - (optional) table of additional configuration options.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>Observable</code> instance.</li>
</ul>
<p>Notes:</p>
<ul>
<li>This will not act until something <code>subscribes</code> to the returned <code>Observable</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="findMenuItemsUI">
            <a name="//apple_ref/cpp/Method/findMenuItemsUI" class="dashAnchor"></a>
            <h5><a href="#findMenuItemsUI">findMenuItemsUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.app.menu:findMenuItemsUI(path[, locale]) -&gt; axuielementObject</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the set of menu items in the provided path. If the path contains a menu, the
actual children of that menu are returned, otherwise the menu item itself is returned.</p>
<p>Parameters:</p>
<ul>
<li>path - A table containing the path to the menu.</li>
<li>locale - The locale the path is in. Defaults to "en".</li>
</ul>
<p>Returns:</p>
<ul>
<li>An <code>axuielementObject</code> for the menu items.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="findMenuUI">
            <a name="//apple_ref/cpp/Method/findMenuUI" class="dashAnchor"></a>
            <h5><a href="#findMenuUI">findMenuUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.app.menu:findMenuUI(path[, options]) -&gt; Menu UI, table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Finds a specific Menu UI element for the provided path.
E.g. <code>findMenuUI({"Edit", "Copy"})</code> returns the 'Copy' menu item in the 'Edit' menu.</p>
<p>Each step on the path can be either one of:</p>
<ul>
<li>a string     - The exact name of the menu item.</li>
<li>a number     - The menu item number, starting from 1.</li>
<li>a function   - Passed one argument - the Menu UI to check - returning <code>true</code> if it matches.</li>
</ul>
<p>Options:</p>
<ul>
<li>locale   - The <code>localeID</code> or <code>string</code> with the locale code. Defaults to "en".</li>
</ul>
<p>Parameters:</p>
<ul>
<li>path         - The path list to search for.</li>
<li>options      - (Optional) The table of options.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The Menu UI, or <code>nil</code> if it could not be found.</li>
<li>The full list of Menu UIs for the path in a table.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="findUI">
            <a name="//apple_ref/cpp/Method/findUI" class="dashAnchor"></a>
            <h5><a href="#findUI">findUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.app.menu:findUI([timeout]) -&gt; cp.rx.Observable &lt;hs._asm.axuielement&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns an <code>Observable</code> that will emit the next available instance of
the Menu's UI once only, then complete.</p>
<p>Parameters:</p>
<ul>
<li>timeout - (optional) the number of seconds to wait for the UI. It not provided, defaults to forever.</li>
</ul>
<p>Returns:</p>
<ul>
<li>An <code>Observer</code> that emits the UI.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="getMenuTitles">
            <a name="//apple_ref/cpp/Method/getMenuTitles" class="dashAnchor"></a>
            <h5><a href="#getMenuTitles">getMenuTitles</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.app.menu:getMenuTitles([locales]) -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a table with the available menus, items and sub-menu, in the specified locales (if available).
If no <code>locales</code> are specified, the app's current locale is loaded.</p>
<p>This menu may get added to over time if additional locales are loaded - previously loaded locales
are not removed from the cache.</p>
<p>Parameters:</p>
<ul>
<li>locales       - An optional single <code>localeID</code> or a list of <code>localeID</code>s to ensure are loaded.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table of Menu Bar Values</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="isChecked">
            <a name="//apple_ref/cpp/Method/isChecked" class="dashAnchor"></a>
            <h5><a href="#isChecked">isChecked</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.app.menu:isChecked(path[, options]) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Is a menu item checked?</p>
<p>Options:</p>
<ul>
<li>locale   - The <code>localeID</code> or <code>string</code> with the locale code. Defaults to "en".</li>
</ul>
<p>Parameters:</p>
<ul>
<li>path - At table containing the path to the menu bar item.</li>
<li>options - The locale the path is in. Defaults to "en".</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if checked otherwise <code>false</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="isEnabled">
            <a name="//apple_ref/cpp/Method/isEnabled" class="dashAnchor"></a>
            <h5><a href="#isEnabled">isEnabled</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.app.menu:isEnabled(path[, options]) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Is a menu item enabled?</p>
<p>Options:</p>
<ul>
<li>locale   - The <code>localeID</code> or <code>string</code> with the locale code. Defaults to "en".</li>
</ul>
<p>Parameters:</p>
<ul>
<li>path - At table containing the path to the menu bar item.</li>
<li>options - The optional table of options.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if enabled otherwise <code>false</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="selectMenu">
            <a name="//apple_ref/cpp/Method/selectMenu" class="dashAnchor"></a>
            <h5><a href="#selectMenu">selectMenu</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.app.menu:selectMenu(path[, options]) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Selects a Menu Item based on the list of menu titles in English.</p>
<p>Each step on the path can be either one of:</p>
<ul>
<li>a string     - The exact name of the menu item.</li>
<li>a number     - The menu item number, starting from 1.</li>
<li>a function   - Passed one argument - the Menu UI to check - returning <code>true</code> if it matches.</li>
</ul>
<p>Options supported include:</p>
<ul>
<li>locale - The <code>localeID</code> or <code>string</code> for the locale that the path values are in.</li>
<li>pressAll - If <code>true</code>, all menu items will be pressed on the way to the final destination.</li>
</ul>
<p>Parameters:</p>
<ul>
<li>path - The list of menu items you'd like to activate.</li>
<li>options - (optional) The table of options to apply.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the press was successful.</li>
</ul>
<p>Notes:</p>
<ul>
<li>Example usage:
<code>require("cp.app").forBundleID("com.apple.FinalCut"):menu():selectMenu({"View", "Browser", "Toggle Filmstrip/List View"})</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="selectMenuItem">
            <a name="//apple_ref/cpp/Method/selectMenuItem" class="dashAnchor"></a>
            <h5><a href="#selectMenuItem">selectMenuItem</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.app.menu:selectMenuItem(path, options) -&gt; cp.rx.Observable &lt;hs._asm.axuielement&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Selects a Menu Item based on the provided menu path.</p>
<p>Each step on the path can be either one of:</p>
<ul>
<li>a string     - The exact name of the menu item.</li>
<li>a number     - The menu item number, starting from 1.</li>
<li>a function   - Passed one argument - the Menu UI to check - returning <code>true</code> if it matches.</li>
</ul>
<p>Options supported include:</p>
<ul>
<li>locale - The <code>localeID</code> or <code>string</code> for the locale that the path values are in.</li>
<li>pressAll - If <code>true</code>, all menu items will be pressed on the way to the final destination.</li>
<li>timeout - The maximum time to wait for the menu to be available before producing an error. Defaults to 10 seconds.</li>
</ul>
<p>Examples:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">preview</span> <span class="o">=</span> <span class="nb">require</span><span class="p">(</span><span class="s2">&quot;cp.app&quot;</span><span class="p">).</span><span class="n">forBundleID</span><span class="p">(</span><span class="s2">&quot;com.apple.Preview&quot;</span><span class="p">)</span>
<span class="n">preview</span><span class="p">:</span><span class="n">launch</span><span class="p">():</span><span class="n">menu</span><span class="p">():</span><span class="n">selectMenuItem</span><span class="p">({</span><span class="s2">&quot;File&quot;</span><span class="p">,</span> <span class="s2">&quot;Take Screenshot&quot;</span><span class="p">,</span> <span class="s2">&quot;From Entire Screen&quot;</span><span class="p">})</span>
</pre></div>
<p>Parameters:</p>
<ul>
<li>path - The list of menu items you'd like to activate.</li>
<li>options - (optional) The table of options to apply.</li>
</ul>
<p>Returns:</p>
<ul>
<li>An <code>Observable</code> which emits the final menu item, or an error if the selection failed.</li>
</ul>
<p>Notes:</p>
<ul>
<li>The returned <code>Observable</code> will be 'hot', in that it will execute even if no subscription is made to the result. However, it will potentially be run asynchronously, so the actual execution may occur later.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="visitMenuItems">
            <a name="//apple_ref/cpp/Method/visitMenuItems" class="dashAnchor"></a>
            <h5><a href="#visitMenuItems">visitMenuItems</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.app.menu:visitMenuItems(visitFn[, options]]) -&gt; nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Walks the menu tree, calling the <code>visitFn</code> on all the 'item' values - that is,
<code>AXMenuItem</code>s that don't have any sub-menus.</p>
<p>The <code>visitFn</code> will be called on each menu item with the following parameters:</p>

<pre><code>function(path, menuItem)</code></pre>
<p>The <code>menuItem</code> is the AXMenuItem object, and the <code>path</code> is an array with the path to that
menu item. For example, if it is the "Copy" item in the "Edit" menu, the path will be
<code>{ "Edit" }</code>.</p>
<p>Options:</p>
<ul>
<li>locale   - The <code>localeID</code> or <code>string</code> with the locale code. Defaults to "en".</li>
<li>startPath - The path to the menu item to start at.</li>
</ul>
<p>Parameters:</p>
<ul>
<li>visitFn - The function called for each menu item.</li>
<li>options - (optional) The table of options.</li>
</ul>
<p>Returns:</p>
<ul>
<li>Nothing</li>
</ul>
</td>
              </tr>
            </table>
          </section>
