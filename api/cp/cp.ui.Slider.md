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
      <h1><a href="cp.ui.Slider.md">docs</a> &raquo; cp.ui.Slider</h1>
      <p>Slider Module.</p>

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
            <li><a href="#app">app</a></li>
            <li><a href="#decrement">decrement</a></li>
            <li><a href="#getMaxValue">getMaxValue</a></li>
            <li><a href="#getMinValue">getMinValue</a></li>
            <li><a href="#getValue">getValue</a></li>
            <li><a href="#increment">increment</a></li>
            <li><a href="#isEnabled">isEnabled</a></li>
            <li><a href="#loadLayout">loadLayout</a></li>
            <li><a href="#parent">parent</a></li>
            <li><a href="#saveLayout">saveLayout</a></li>
            <li><a href="#setValue">setValue</a></li>
            <li><a href="#shiftValue">shiftValue</a></li>
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
                <td><code>cp.ui.Slider.matches(element) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks if the provided <code>hs._asm.axuielement</code> is a Slider.</p>
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
                <td><code>cp.ui.Slider.new(parent, finderFn) -&gt; cp.ui.Slider</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new Slider</p>
<p>Parameters:</p>
<ul>
<li>parent       - The parent object. Should have an <code>isShowing</code> property.</li>
<li>finderFn     - The function which returns an <code>hs._asm.axuielement</code> for the slider, or <code>nil</code>.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A new <code>Slider</code> instance.</li>
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
                <td><code>cp.ui.Slider:app() -&gt; App</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the app instance.</p>
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
          <section id="decrement">
            <a name="//apple_ref/cpp/Method/decrement" class="dashAnchor"></a>
            <h5><a href="#decrement">decrement</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Slider:decrement() -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Decrements the slider by one step.</p>
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
          <section id="getMaxValue">
            <a name="//apple_ref/cpp/Method/getMaxValue" class="dashAnchor"></a>
            <h5><a href="#getMaxValue">getMaxValue</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Slider:getMaxValue() -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the maximum value of the slider.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The value as a number.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="getMinValue">
            <a name="//apple_ref/cpp/Method/getMinValue" class="dashAnchor"></a>
            <h5><a href="#getMinValue">getMinValue</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Slider:getMinValue() -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the minimum value of the slider.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The value as a number.</li>
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
                <td><code>cp.ui.Slider:getValue() -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the value of the slider.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The value of the slider as a number.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="increment">
            <a name="//apple_ref/cpp/Method/increment" class="dashAnchor"></a>
            <h5><a href="#increment">increment</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Slider:increment() -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Increments the slider by one step.</p>
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
                <td><code>cp.ui.Slider:isEnabled() -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Is the slider enabled?</p>
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
                <td><code>cp.ui.Slider:loadLayout(layout) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Loads a Slider layout.</p>
<p>Parameters:</p>
<ul>
<li>layout - A table containing the Slider layout settings - created using <code>cp.ui.Slider:saveLayout()</code>.</li>
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
                <td><code>cp.ui.Slider:parent() -&gt; table</code></td>
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
          <section id="saveLayout">
            <a name="//apple_ref/cpp/Method/saveLayout" class="dashAnchor"></a>
            <h5><a href="#saveLayout">saveLayout</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Slider:saveLayout() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Saves the current Slider layout to a table.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table containing the current Slider Layout.</li>
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
                <td><code>cp.ui.Slider:setValue(value) -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Sets the value of the slider.</p>
<p>Parameters:</p>
<ul>
<li>value - The value you want to set the slider to as a number.</li>
</ul>
<p>Returns:</p>
<ul>
<li>Self</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="shiftValue">
            <a name="//apple_ref/cpp/Method/shiftValue" class="dashAnchor"></a>
            <h5><a href="#shiftValue">shiftValue</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Slider:shiftValue(value) -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Shifts the value of the slider.</p>
<p>Parameters:</p>
<ul>
<li>value - The value you want to shift the slider by as a number.</li>
</ul>
<p>Returns:</p>
<ul>
<li>Self</li>
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
                <td><code>cp.ui.Slider:snapshot([path]) -&gt; hs.image | nil</code></td>
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
<li>path - (optional) The path to save the file. Should include the extension (should be <code>.png</code>).</li>
</ul>
<p>Return:</p>
<ul>
<li>The <code>hs.image</code> that was created, or <code>nil</code> if the UI is not available.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
