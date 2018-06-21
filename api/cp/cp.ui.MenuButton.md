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
      <h1><a href="cp.ui.MenuButton.md">docs</a> &raquo; cp.ui.MenuButton</h1>
      <p>Pop Up Button Module.</p>

      </header>
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
            <li><a href="#getTitle">getTitle</a></li>
            <li><a href="#getValue">getValue</a></li>
            <li><a href="#isEnabled">isEnabled</a></li>
            <li><a href="#loadLayout">loadLayout</a></li>
            <li><a href="#parent">parent</a></li>
            <li><a href="#press">press</a></li>
            <li><a href="#saveLayout">saveLayout</a></li>
            <li><a href="#selectItem">selectItem</a></li>
            <li><a href="#selectItemMatching">selectItemMatching</a></li>
            <li><a href="#setValue">setValue</a></li>
            <li><a href="#show">show</a></li>
            <li><a href="#snapshot">snapshot</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Functions</h4>
          <section id="matches">
            <a name="//apple_ref/cpp/Function/matches" class="dashAnchor"></a>
            <h5><a href="#matches">matches</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.MenuButton.matches(element) -&gt; boolean</code></td>
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
                <td><code>cp.ui.MenuButton.new(parent, finderFn) -&gt; MenuButton</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new MenuButton.</p>
<p>Parameters:</p>
<ul>
<li>parent        - The parent object. Should have an <code>isShowing</code> property.</li>
<li>finderFn      - A <code>cp.prop</code> or function which will return a <code>hs._asm.axuielement</code>, or <code>nil</code> if it's not available.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Methods</h4>
          <section id="getTitle">
            <a name="//apple_ref/cpp/Method/getTitle" class="dashAnchor"></a>
            <h5><a href="#getTitle">getTitle</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.MenuButton:getTitle() -&gt; string | nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the <code>MenuButton</code> title.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>MenuButton</code> title as string, or <code>nil</code> if the title cannot be determined.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="getValue">
            <a name="//apple_ref/cpp/Method/getValue" class="dashAnchor"></a>
            <h5><a href="#getValue">getValue</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.MenuButton:getValue() -&gt; string | nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the <code>MenuButton</code> value.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>MenuButton</code> value as string, or <code>nil</code> if the value cannot be determined.</li>
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
                <td><code>cp.ui.MenuButton:isEnabled() -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Is the <code>MenuButton</code> enabled?</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if enabled otherwise <code>false</code>.</li>
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
                <td><code>cp.ui.MenuButton:loadLayout(layout) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Loads a <code>MenuButton</code> layout.</p>
<p>Parameters:</p>
<ul>
<li>layout - A table containing the <code>MenuButton</code> layout settings - created using <code>cp.ui.MenuButton:saveLayout()</code>.</li>
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
                <td><code>cp.ui.MenuButton:parent() -&gt; parent</code></td>
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
          <section id="press">
            <a name="//apple_ref/cpp/Method/press" class="dashAnchor"></a>
            <h5><a href="#press">press</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.MenuButton:press() -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Presses the MenuButton.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>self</li>
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
                <td><code>cp.ui.MenuButton:saveLayout() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Saves the current <code>MenuButton</code> layout to a table.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table containing the current <code>MenuButton</code> Layout.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="selectItem">
            <a name="//apple_ref/cpp/Method/selectItem" class="dashAnchor"></a>
            <h5><a href="#selectItem">selectItem</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.MenuButton:selectItem(index) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Select an item on the <code>MenuButton</code> by index.</p>
<p>Parameters:</p>
<ul>
<li>index - The index of the item you want to select.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successfully selected, otherwise <code>false</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="selectItemMatching">
            <a name="//apple_ref/cpp/Method/selectItemMatching" class="dashAnchor"></a>
            <h5><a href="#selectItemMatching">selectItemMatching</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.MenuButton:selectItemMatching(pattern) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Select an item on the <code>MenuButton</code> by pattern.</p>
<p>Parameters:</p>
<ul>
<li>pattern - A pattern used to select the <code>MenuButton</code> item.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successfully selected, otherwise <code>false</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="setValue">
            <a name="//apple_ref/cpp/Method/setValue" class="dashAnchor"></a>
            <h5><a href="#setValue">setValue</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.MenuButton:setValue(value) -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Sets the <code>MenuButton</code> value.</p>
<p>Parameters:</p>
<ul>
<li>value - The value you want to set the <code>MenuButton</code> to.</li>
</ul>
<p>Returns:</p>
<ul>
<li>self</li>
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
                <td><code>cp.ui.MenuButton:show() -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Show's the MenuButton.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>self</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="snapshot">
            <a name="//apple_ref/cpp/Method/snapshot" class="dashAnchor"></a>
            <h5><a href="#snapshot">snapshot</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.MenuButton:snapshot([path]) -&gt; hs.image | nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Takes a snapshot of the UI in its current state as a PNG and returns it.
If the <code>path</code> is provided, the image will be saved at the specified location.</p>
<p>Parameters:</p>
<ul>
<li>path      - (optional) The path to save the file. Should include the extension (should be <code>.png</code>).</li>
</ul>
<p>Return:</p>
<ul>
<li>The <code>hs.image</code> that was created, or <code>nil</code> if the UI is not available.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
