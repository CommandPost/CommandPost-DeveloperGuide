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
      <h1><a href="cp.apple.finalcutpro.inspector.text.TextInspector.md">docs</a> &raquo; cp.apple.finalcutpro.inspector.text.TextInspector</h1>
      <p>Text Inspector Module.</p>
<p>Section Rows (<code>compositing</code>, <code>transform</code>, etc.) have the following properties:</p>
<ul>
<li>enabled   - (cp.ui.CheckBox) Indicates if the section is enabled.</li>
<li>toggle    - (cp.ui.Button) Will toggle the Hide/Show button.</li>
<li>reset     - (cp.ui.Button) Will reset the contents of the section.</li>
<li>expanded  - (cp.prop <boolean>) Get/sets whether the section is expanded.</li>
</ul>
<p>Property Rows depend on the type of property:</p>
<p>Menu Property:</p>
<ul>
<li>value     - (cp.ui.PopUpButton) The current value of the property.</li>
</ul>
<p>Slider Property:</p>
<ul>
<li>value     - (cp.ui.Slider) The current value of the property.</li>
</ul>
<p>XY Property:</p>
<ul>
<li>x         - (cp.ui.TextField) The current 'X' value.</li>
<li>y         - (cp.ui.TextField) The current 'Y' value.</li>
</ul>
<p>CheckBox Property:</p>
<ul>
<li>value     - (cp.ui.CheckBox) The currently value.</li>
</ul>
<p>For example:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">text</span> <span class="o">=</span> <span class="n">fcp</span><span class="p">:</span><span class="n">inspector</span><span class="p">():</span><span class="n">text</span><span class="p">()</span>
<span class="c1">-- Menu Property:</span>
<span class="n">text</span><span class="p">:</span><span class="n">compositing</span><span class="p">():</span><span class="n">blendMode</span><span class="p">():</span><span class="n">value</span><span class="p">(</span><span class="s2">&quot;Subtract&quot;</span><span class="p">)</span>
<span class="c1">-- Slider Property:</span>
<span class="n">text</span><span class="p">:</span><span class="n">compositing</span><span class="p">():</span><span class="n">opacity</span><span class="p">():</span><span class="n">value</span><span class="p">(</span><span class="mf">50.0</span><span class="p">)</span>
<span class="c1">-- XY Property:</span>
<span class="n">text</span><span class="p">:</span><span class="n">transform</span><span class="p">():</span><span class="n">position</span><span class="p">():</span><span class="n">x</span><span class="p">(</span><span class="o">-</span><span class="mf">10.0</span><span class="p">)</span>
<span class="c1">-- CheckBox property:</span>
<span class="n">text</span><span class="p">:</span><span class="n">stabilization</span><span class="p">():</span><span class="n">tripodMode</span><span class="p">():</span><span class="n">value</span><span class="p">(</span><span class="kc">true</span><span class="p">)</span>
</pre></div>
<p>You should also be able to show a specific property and it will be revealed:</p>
<div class="highlight"><pre><span></span><span class="n">text</span><span class="p">:</span><span class="n">stabilization</span><span class="p">():</span><span class="n">smoothing</span><span class="p">():</span><span class="n">show</span><span class="p">():</span><span class="n">value</span><span class="p">(</span><span class="mf">1.5</span><span class="p">)</span>
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
            <li><a href="#app">app</a></li>
            <li><a href="#parent">parent</a></li>
            <li><a href="#show">show</a></li>
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
                <td><code>cp.apple.finalcutpro.inspector.text.TextInspector.matches(element)</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks if the provided element could be a TextInspector.</p>
<p>Parameters:</p>
<ul>
<li>element   - The element to check</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if it matches, <code>false</code> if not.</li>
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
                <td><code>cp.apple.finalcutpro.inspector.text.TextInspector.new(parent) -&gt; cp.apple.finalcutpro.text.TextInspector</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new <code>TextInspector</code> object</p>
<p>Parameters:</p>
<ul>
<li><code>parent</code>     - The parent</li>
</ul>
<p>Returns:</p>
<ul>
<li>A <code>TextInspector</code> object</li>
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
                <td><code>cp.apple.finalcutpro.inspector.text.TextInspector:app() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the <code>cp.apple.finalcutpro</code> app table</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The application object as a table</li>
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
                <td><code>cp.apple.finalcutpro.inspector.text.TextInspector:parent() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the TextInspector's parent table</p>
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
          <section id="show">
            <a name="//apple_ref/cpp/Method/show" class="dashAnchor"></a>
            <h5><a href="#show">show</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.text.TextInspector:show() -&gt; TextInspector</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Shows the Text Inspector</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>TextInspector</li>
</ul>
</td>
              </tr>
            </table>
          </section>
