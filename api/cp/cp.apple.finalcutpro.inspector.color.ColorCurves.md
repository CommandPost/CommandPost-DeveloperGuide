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
      <h1><a href="cp.apple.finalcutpro.inspector.color.ColorCurves.md">docs</a> &raquo; cp.apple.finalcutpro.inspector.color.ColorCurves</h1>
      <p>Color Curves Module.</p>
<p>Requires Final Cut Pro 10.4 or later.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Constants - Useful values which cannot be changed</li>
          <ul>
            <li><a href="#CURVES">CURVES</a></li>
            <li><a href="#VIEW_MODES">VIEW_MODES</a></li>
          </ul>
        <li>Constructors - API calls which return an object, typically one that offers API methods</li>
          <ul>
            <li><a href="#new">new</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#app">app</a></li>
            <li><a href="#isShowing">isShowing</a></li>
            <li><a href="#mix">mix</a></li>
            <li><a href="#parent">parent</a></li>
            <li><a href="#preserveLuma">preserveLuma</a></li>
            <li><a href="#show">show</a></li>
            <li><a href="#viewMode">viewMode</a></li>
            <li><a href="#visibleCurve">visibleCurve</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Constants</h4>
          <section id="CURVES">
            <a name="//apple_ref/cpp/Constant/CURVES" class="dashAnchor"></a>
            <h5><a href="#CURVES">CURVES</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorCurves.CURVES -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Table containing all the different types of Color Curves</p>
</td>
              </tr>
            </table>
          </section>
          <section id="VIEW_MODES">
            <a name="//apple_ref/cpp/Constant/VIEW_MODES" class="dashAnchor"></a>
            <h5><a href="#VIEW_MODES">VIEW_MODES</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorCurves.VIEW_MODES -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>View Modes for Color Curves</p>
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
                <td><code>cp.apple.finalcutpro.inspector.color.ColorCurves.new(parent) -&gt; ColorCurves object</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new ColorCurves object</p>
<p>Parameters:</p>
<ul>
<li><code>parent</code>     - The parent</li>
</ul>
<p>Returns:</p>
<ul>
<li>A ColorInspector object</li>
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
                <td><code>cp.apple.finalcutpro.inspector.color.ColorCurves:app() -&gt; table</code></td>
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
          <section id="isShowing">
            <a name="//apple_ref/cpp/Method/isShowing" class="dashAnchor"></a>
            <h5><a href="#isShowing">isShowing</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorCurves:isShowing() -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Is the Color Curves panel currently showing?</p>
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
          <section id="mix">
            <a name="//apple_ref/cpp/Method/mix" class="dashAnchor"></a>
            <h5><a href="#mix">mix</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorCurves:mix([value]) -&gt; number | nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Sets or gets the color curves mix value.</p>
<p>Parameters:</p>
<ul>
<li>[value] - An optional value you want to set the mix value to as number (0 to 1).</li>
</ul>
<p>Returns:</p>
<ul>
<li>A number containing the mix value or <code>nil</code> if an error occurs.</li>
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
                <td><code>cp.apple.finalcutpro.inspector.color.ColorCurves:parent() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the ColorCurves's parent table</p>
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
          <section id="preserveLuma">
            <a name="//apple_ref/cpp/Method/preserveLuma" class="dashAnchor"></a>
            <h5><a href="#preserveLuma">preserveLuma</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorCurves:preserveLuma([value]) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Sets or gets whether or not Preserve Luma is active.</p>
<p>Parameters:</p>
<ul>
<li>[value] - An optional boolean value to set the Preserve Luma option.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if Preserve Luma is selected, otherwise <code>false</code>.</li>
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
                <td><code>cp.apple.finalcutpro.inspector.color.ColorCurves:show() -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Show's the Color Board within the Color Inspector.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>ColorCurves object</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="viewMode">
            <a name="//apple_ref/cpp/Method/viewMode" class="dashAnchor"></a>
            <h5><a href="#viewMode">viewMode</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorCurves:viewMode([value]) -&gt; string | nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Sets or gets the View Mode for the Color Curves.</p>
<p>Parameters:</p>
<ul>
<li>[value] - An optional value to set the View Mode, as defined in <code>cp.apple.finalcutpro.inspector.color.ColorCurves.VIEW_MODES</code>.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A string containing the View Mode or <code>nil</code> if an error occurs.</li>
</ul>
<p>Notes:</p>
<ul>
<li>Value can be:<ul>
<li>All Curves</li>
<li>Single Curves</li>
</ul>
</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="visibleCurve">
            <a name="//apple_ref/cpp/Method/visibleCurve" class="dashAnchor"></a>
            <h5><a href="#visibleCurve">visibleCurve</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorCurves:visibleCurve([value]) -&gt; string | nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Sets or gets the selected color curve.</p>
<p>Parameters:</p>
<ul>
<li>[value] - An optional value to set the visible curve, as defined in <code>cp.apple.finalcutpro.inspector.color.ColorCurves.CURVES</code>.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A string containing the selected color curve or <code>nil</code> if an error occurs.</li>
</ul>
<p>Notes:</p>
<ul>
<li>Value can be:<ul>
<li>All Curves</li>
<li>Luma</li>
<li>Red</li>
<li>Green</li>
<li>Blue</li>
</ul>
</li>
<li>Example Usage:
<code>require("cp.apple.finalcutpro"):inspector():color():colorCurves():visibleCurve("Luma")</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
