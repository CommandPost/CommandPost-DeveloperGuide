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
      <h1><a href="cp.ui.TextField.md">docs</a> &raquo; cp.ui.TextField</h1>
      <p>Text Field Module.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Variables - Configurable values</li>
          <ul>
            <li><a href="#isShowing">isShowing</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#matches">matches</a></li>
          </ul>
        <li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
          <ul>
            <li><a href="#value">value</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#clear">clear</a></li>
            <li><a href="#getValue">getValue</a></li>
            <li><a href="#isEnabled">isEnabled</a></li>
            <li><a href="#loadLayout">loadLayout</a></li>
            <li><a href="#new">new</a></li>
            <li><a href="#parent">parent</a></li>
            <li><a href="#saveLayout">saveLayout</a></li>
            <li><a href="#setValue">setValue</a></li>
            <li><a href="#snapshot">snapshot</a></li>
            <li><a href="#UI">UI</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Variables</h4>
          <section id="isShowing">
            <a name="//apple_ref/cpp/Variable/isShowing" class="dashAnchor"></a>
            <h5><a href="#isShowing">isShowing</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.TextField.isShowing &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Is the Text Field showing?</p>
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
                <td><code>cp.ui.TextField.matches(element) -&gt; boolean</code></td>
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
        <h4 class="documentation-section">Fields</h4>
          <section id="value">
            <a name="//apple_ref/cpp/Field/value" class="dashAnchor"></a>
            <h5><a href="#value">value</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.TextField.value &lt;cp.prop: string&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The current value of the text field.</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Methods</h4>
          <section id="clear">
            <a name="//apple_ref/cpp/Method/clear" class="dashAnchor"></a>
            <h5><a href="#clear">clear</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.TextField:clear() -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Clears the value of a Text Field.</p>
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
          <section id="getValue">
            <a name="//apple_ref/cpp/Method/getValue" class="dashAnchor"></a>
            <h5><a href="#getValue">getValue</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.TextField:getValue() -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the value of the Text Field.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The value of the Text Field as a string.</li>
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
                <td><code>cp.ui.TextField:isEnabled() -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Is the Text Field enabled?</p>
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
                <td><code>cp.ui.TextField:loadLayout(layout) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Loads a Text Field layout.</p>
<p>Parameters:</p>
<ul>
<li>layout - A table containing the Text Field layout settings - created using <code>cp.ui.TextField:saveLayout()</code>.</li>
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
                <td><code>cp.ui.TextField.new(parent, finderFn[, convertFn]) -&gt; TextField</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new TextField. They have a parent and a finder function.
Additionally, an optional <code>convert</code> function can be provided, with the following signature:</p>
<p><code>function(textValue) -&gt; anything</code></p>
<p>The <code>value</code> will be passed to the function before being returned, if present. All values
passed into <code>value(x)</code> will be converted to a <code>string</code> first via <code>tostring</code>.</p>
<p>For example, to have the value be converted into a <code>number</code>, simply use <code>tonumber</code> like this:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">numberField</span> <span class="o">=</span> <span class="n">TextField</span><span class="p">.</span><span class="n">new</span><span class="p">(</span><span class="n">parent</span><span class="p">,</span> <span class="kr">function</span><span class="p">()</span> <span class="kr">return</span> <span class="p">...</span> <span class="kr">end</span><span class="p">,</span> <span class="nb">tonumber</span><span class="p">)</span>
</pre></div>
<p>Parameters:</p>
<ul>
<li>parent   - The parent object.</li>
<li>finderFn - The function will return the <code>axuielement</code> for the TextField.</li>
<li>convertFn    - (optional) If provided, will be passed the <code>string</code> value when returning.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The new <code>TextField</code>.</li>
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
                <td><code>cp.ui.TextField:parent() -&gt; table</code></td>
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
                <td><code>cp.ui.TextField:saveLayout() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Saves the current Text Field layout to a table.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table containing the current Text Field Layout.</li>
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
                <td><code>cp.ui.TextField:setValue(value) -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Sets the value of the Text Field.</p>
<p>Parameters:</p>
<ul>
<li>value - The value you want to set the Text Field to as a string.</li>
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
                <td><code>cp.ui.TextField:snapshot([path]) -&gt; hs.image | nil</code></td>
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
          <section id="UI">
            <a name="//apple_ref/cpp/Method/UI" class="dashAnchor"></a>
            <h5><a href="#UI">UI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.TextField:UI() -&gt; hs._asm.axuielement | nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the <code>axuielement</code> representing the <code>TextField</code>, or <code>nil</code> if not available.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Return:</p>
<ul>
<li>The <code>axuielement</code> or <code>nil</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
