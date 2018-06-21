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
      <h1><a href="cp.apple.finalcutpro.inspector.color.ValueIndicator.md">docs</a> &raquo; cp.apple.finalcutpro.inspector.color.ValueIndicator</h1>
      <p>ValueIndicator Module.</p>

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
            <li><a href="#decrement">decrement</a></li>
            <li><a href="#increment">increment</a></li>
            <li><a href="#isEnabled">isEnabled</a></li>
            <li><a href="#isShowing">isShowing</a></li>
            <li><a href="#loadLayout">loadLayout</a></li>
            <li><a href="#parent">parent</a></li>
            <li><a href="#saveLayout">saveLayout</a></li>
            <li><a href="#shiftValue">shiftValue</a></li>
            <li><a href="#UI">UI</a></li>
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
                <td><code>cp.apple.finalcutpro.inspector.color.ValueIndicator.matches(element) -&gt; boolean</code></td>
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
                <td><code>cp.apple.finalcutpro.inspector.color.ValueIndicator.new(parent, finderFn, minValue, maxValue, toAXValueFn, fromAXValueFn) -&gt; ValueIndicator</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new ValueIndicator.</p>
<p>Parameters:</p>
<ul>
<li><code>parent</code>         - The parent table.</li>
<li><code>finderFn</code>       - The function which returns the <code>axuielement</code>.</li>
<li><code>minValue</code>       - The minimum value allowed for the value.</li>
<li><code>maxValue</code>       - The maximum value allowed for the value.</li>
<li><code>toAXValueFn</code>    - The function which will convert the user value to the actual AXValue.</li>
<li><code>fromAXValueFn</code>  - The function which will convert the current AXValue to a user value.</li>
</ul>
<p>Returns:</p>
<ul>
<li>New <code>ValueIndicator</code> instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Methods</h4>
          <section id="decrement">
            <a name="//apple_ref/cpp/Method/decrement" class="dashAnchor"></a>
            <h5><a href="#decrement">decrement</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ValueIndicator:decrement() -&gt; cp.apple.finalcutpro.inspector.color.ValueIndicator</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Decrements the value indicator.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.apple.finalcutpro.inspector.color.ValueIndicator</code> object.</li>
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
                <td><code>cp.apple.finalcutpro.inspector.color.ValueIndicator:increment() -&gt; cp.apple.finalcutpro.inspector.color.ValueIndicator</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Increments the value indicator.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.apple.finalcutpro.inspector.color.ValueIndicator</code> object.</li>
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
                <td><code>cp.apple.finalcutpro.inspector.color.ValueIndicator:isEnabled() -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Is the value indicator enabled?</p>
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
          <section id="isShowing">
            <a name="//apple_ref/cpp/Method/isShowing" class="dashAnchor"></a>
            <h5><a href="#isShowing">isShowing</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ValueIndicator:isShowing() -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Is the Value Indicator currently showing?</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if showing, otherwise <code>false</code></li>
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
                <td><code>cp.apple.finalcutpro.inspector.color.ValueIndicator:loadLayout(layout) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Loads a layout.</p>
<p>Parameters:</p>
<ul>
<li><code>layout</code> - The layout table you want to load.</li>
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
                <td><code>cp.apple.finalcutpro.inspector.color.ValueIndicator:parent() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the Value Indicators parent table</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The parent object as a table</li>
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
                <td><code>cp.apple.finalcutpro.inspector.color.ValueIndicator:saveLayout() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Saves the layout.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table containing the layout.</li>
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
                <td><code>cp.apple.finalcutpro.inspector.color.ValueIndicator:shiftValue(value) -&gt; cp.apple.finalcutpro.inspector.color.ValueIndicator</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Shifts the Value Indicator value.</p>
<p>Parameters:</p>
<ul>
<li><code>value</code> - The amount to shift the value indicator by as a number.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.apple.finalcutpro.inspector.color.ValueIndicator</code> object.</li>
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
                <td><code>cp.apple.finalcutpro.inspector.color.ValueIndicator:UI() -&gt; hs._asm.axuielement | nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the <code>hs._asm.axuielement</code> object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A <code>hs._asm.axuielement</code> object or <code>nil</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
