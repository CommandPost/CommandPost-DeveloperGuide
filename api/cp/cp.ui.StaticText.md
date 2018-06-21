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
      <h1><a href="cp.ui.StaticText.md">docs</a> &raquo; cp.ui.StaticText</h1>
      <p>Static Text Module.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#matches">matches</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#app">app</a></li>
            <li><a href="#clear">clear</a></li>
            <li><a href="#isEnabled">isEnabled</a></li>
            <li><a href="#loadLayout">loadLayout</a></li>
            <li><a href="#new">new</a></li>
            <li><a href="#parent">parent</a></li>
            <li><a href="#saveLayout">saveLayout</a></li>
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
                <td><code>cp.ui.StaticText.matches(element) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks if the element is a Static Text element.</p>
<p>Parameters:</p>
<ul>
<li>element      - The <code>axuielement</code> to check.</li>
</ul>
<p>Returns:</p>
<ul>
<li>If <code>true</code>, the element is a Static Text element.</li>
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
                <td><code>cp.ui.StaticText:app() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the app object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The app.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="clear">
            <a name="//apple_ref/cpp/Method/clear" class="dashAnchor"></a>
            <h5><a href="#clear">clear</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.StaticText:clear() -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Clears the value of a Static Text box.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>Self</li>
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
                <td><code>cp.ui.StaticText:isEnabled() -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Is the Static Text box enabled?</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if enabled, otherwise <code>false</code>.</li>
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
                <td><code>cp.ui.StaticText:loadLayout(layout) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Loads a Static Text layout.</p>
<p>Parameters:</p>
<ul>
<li>layout - A table containing the Static Text layout settings - created using <code>cp.ui.StaticText:saveLayout()</code>.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
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
                <td><code>cp.ui.StaticText.new(parent, finderFn[, convertFn]) -&gt; StaticText</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new StaticText. They have a parent and a finder function.
Additionally, an optional <code>convert</code> function can be provided, with the following signature:</p>
<p><code>function(textValue) -&gt; anything</code></p>
<p>The <code>value</code> will be passed to the function before being returned, if present. All values
passed into <code>value(x)</code> will be converted to a <code>string</code> first via <code>tostring</code>.</p>
<p>For example, to have the value be converted into a <code>number</code>, simply use <code>tonumber</code> like this:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">numberField</span> <span class="o">=</span> <span class="n">StaticText</span><span class="p">.</span><span class="n">new</span><span class="p">(</span><span class="n">parent</span><span class="p">,</span> <span class="kr">function</span><span class="p">()</span> <span class="kr">return</span> <span class="p">...</span> <span class="kr">end</span><span class="p">,</span> <span class="nb">tonumber</span><span class="p">)</span>
</pre></div>
<p>Parameters:</p>
<ul>
<li>parent   - The parent object.</li>
<li>finderFn - The function will return the <code>axuielement</code> for the StaticText.</li>
<li>convertFn    - (optional) If provided, will be passed the <code>string</code> value when returning.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The new <code>StaticText</code>.</li>
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
                <td><code>cp.ui.StaticText:parent() -&gt; table</code></td>
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
<li>The parent.</li>
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
                <td><code>cp.ui.StaticText:saveLayout() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Saves the current Static Text layout to a table.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table containing the current Static Text Layout.</li>
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
                <td><code>cp.ui.StaticText:snapshot([path]) -&gt; hs.image | nil</code></td>
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
