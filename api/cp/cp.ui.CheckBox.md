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
      <h1><a href="cp.ui.CheckBox.md">docs</a> &raquo; cp.ui.CheckBox</h1>
      <p>Check Box UI Module.</p>
<p>This represents an <code>hs._asm.axuielement</code> with a <code>AXCheckBox</code> role.
It allows checking and modifying the <code>checked</code> status like so:</p>
<div class="highlight"><pre><span></span><span class="n">myButton</span><span class="p">:</span><span class="n">checked</span><span class="p">()</span> <span class="o">==</span> <span class="kc">true</span>          <span class="c1">-- happens to be checked already</span>
<span class="n">myButton</span><span class="p">:</span><span class="n">checked</span><span class="p">(</span><span class="kc">false</span><span class="p">)</span> <span class="o">==</span> <span class="kc">false</span>    <span class="c1">-- update to unchecked.</span>
<span class="n">myButton</span><span class="p">.</span><span class="n">checked</span><span class="p">:</span><span class="n">toggle</span><span class="p">()</span> <span class="o">==</span> <span class="kc">true</span>   <span class="c1">-- toggled back to being checked.</span>
</pre></div>
<p>You can also call instances of <code>CheckBox</code> as a function, which will return
the <code>checked</code> status:</p>
<div class="highlight"><pre><span></span><span class="n">myButton</span><span class="p">()</span> <span class="o">==</span> <span class="kc">true</span>          <span class="c1">-- still true</span>
<span class="n">myButton</span><span class="p">(</span><span class="kc">false</span><span class="p">)</span> <span class="o">==</span> <span class="kc">false</span>    <span class="c1">-- now false</span>
</pre></div>

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
            <li><a href="#isEnabled">isEnabled</a></li>
            <li><a href="#loadLayout">loadLayout</a></li>
            <li><a href="#parent">parent</a></li>
            <li><a href="#press">press</a></li>
            <li><a href="#saveLayout">saveLayout</a></li>
            <li><a href="#snapshot">snapshot</a></li>
            <li><a href="#toggle">toggle</a></li>
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
                <td><code>cp.ui.CheckBox.matches(element) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks if the provided <code>hs._asm.axuielement</code> is a CheckBox.</p>
<p>Parameters:</p>
<ul>
<li>element      - The <code>axuielement</code> to check.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if it's a match, or <code>false</code> if not.</li>
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
                <td><code>cp.ui.CheckBox.new(parent, finderFn) -&gt; cp.ui.CheckBox</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new CheckBox.</p>
<p>Parameters:</p>
<ul>
<li>parent       - The parent object.</li>
<li>finderFn     - A function which will return the <code>hs._asm.axuielement</code> when available.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The new <code>CheckBox</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Methods</h4>
          <section id="isEnabled">
            <a name="//apple_ref/cpp/Method/isEnabled" class="dashAnchor"></a>
            <h5><a href="#isEnabled">isEnabled</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.CheckBox:isEnabled() -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns <code>true</code> if the radio button exists and is enabled.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:
<code>true</code> or <code>false</code>.</p>
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
                <td><code>cp.ui.CheckBox:loadLayout(layout) -&gt; nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Applies the settings in the provided layout table.</p>
<p>Parameters:</p>
<ul>
<li>layout       - The table containing layout settings. Usually created by the <code>saveLayout</code> method.</li>
</ul>
<p>Returns:</p>
<ul>
<li>nil</li>
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
                <td><code>cp.ui.CheckBox:parent() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The parent object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The parent object.</li>
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
                <td><code>cp.ui.CheckBox:press() -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Attempts to press the button. May fail if the <code>UI</code> is not available.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:
The <code>CheckBox</code> instance.</p>
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
                <td><code>cp.ui.CheckBox:saveLayout() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a table containing the layout settings for the checkbox.
This table may be passed to the <code>loadLayout</code> method to restore the saved layout.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A settings table.</li>
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
                <td><code>cp.ui.CheckBox:snapshot([path]) -&gt; hs.image | nil</code></td>
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
<li>path     - (optional) The path to save the file. Should include the extension (should be <code>.png</code>).</li>
</ul>
<p>Return:</p>
<ul>
<li>The <code>hs.image</code> that was created, or <code>nil</code> if the UI is not available.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="toggle">
            <a name="//apple_ref/cpp/Method/toggle" class="dashAnchor"></a>
            <h5><a href="#toggle">toggle</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.CheckBox:toggle() -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Toggles the <code>checked</code> status of the button.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>CheckBox</code> instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
