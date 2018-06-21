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
      <h1><a href="cp.apple.finalcutpro.inspector.color.ColorBoardAspect.md">docs</a> &raquo; cp.apple.finalcutpro.inspector.color.ColorBoardAspect</h1>
      <p>Represents a particular aspect of the color board (Color/Saturation/Exposure).</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Constants - Useful values which cannot be changed</li>
          <ul>
            <li><a href="#ids">ids</a></li>
          </ul>
        <li>Constructors - API calls which return an object, typically one that offers API methods</li>
          <ul>
            <li><a href="#new">new</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#app">app</a></li>
            <li><a href="#hasAngle">hasAngle</a></li>
            <li><a href="#highlights">highlights</a></li>
            <li><a href="#id">id</a></li>
            <li><a href="#index">index</a></li>
            <li><a href="#isShowing">isShowing</a></li>
            <li><a href="#master">master</a></li>
            <li><a href="#midtones">midtones</a></li>
            <li><a href="#parent">parent</a></li>
            <li><a href="#reset">reset</a></li>
            <li><a href="#selected">selected</a></li>
            <li><a href="#shadows">shadows</a></li>
            <li><a href="#show">show</a></li>
            <li><a href="#UI">UI</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Constants</h4>
          <section id="ids">
            <a name="//apple_ref/cpp/Constant/ids" class="dashAnchor"></a>
            <h5><a href="#ids">ids</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoardAspect.ids -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>A table containing the list of aspect IDs ("color", "saturation", "exposure").</p>
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
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoardAspect.new(parent, index[, hasAngle]) -&gt; ColorBoardAspect</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new <code>ColorBoardAspect</code> object.</p>
<p>Parameters:</p>
<ul>
<li>parent - The parent object.</li>
<li>index - The Color Board Aspect Index.</li>
<li>hasAngle - If <code>true</code>, the aspect has an <code>angle</code> parameter. Defaults to <code>false</code></li>
</ul>
<p>Returns:</p>
<ul>
<li>A new `ColorBoardAspect object.</li>
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
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoardAspect:app() -&gt; App</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the App instance representing Final Cut Pro.</p>
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
          <section id="hasAngle">
            <a name="//apple_ref/cpp/Method/hasAngle" class="dashAnchor"></a>
            <h5><a href="#hasAngle">hasAngle</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoardAspect:hasAngle() -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks if the aspect has an <code>angle</code> property.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if it has an <code>angle</code> propery.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="highlights">
            <a name="//apple_ref/cpp/Method/highlights" class="dashAnchor"></a>
            <h5><a href="#highlights">highlights</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoardAspect:highlights() -&gt; ColorPuck</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the Highlights ColorPuck object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The Highlights ColorPuck object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="id">
            <a name="//apple_ref/cpp/Method/id" class="dashAnchor"></a>
            <h5><a href="#id">id</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoardAspect:id() -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the Color Board Aspect ID.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The ID as string.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="index">
            <a name="//apple_ref/cpp/Method/index" class="dashAnchor"></a>
            <h5><a href="#index">index</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoardAspect:index() -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the Color Board Aspect index.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A number.</li>
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
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoardAspect:isShowing() -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets whether or not the Color Board Aspect is showing.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if showing or <code>false</code> if not.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="master">
            <a name="//apple_ref/cpp/Method/master" class="dashAnchor"></a>
            <h5><a href="#master">master</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoardAspect:master() -&gt; ColorPuck</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the Master ColorPuck object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The Master ColorPuck object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="midtones">
            <a name="//apple_ref/cpp/Method/midtones" class="dashAnchor"></a>
            <h5><a href="#midtones">midtones</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoardAspect:midtones() -&gt; ColorPuck</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the Midtones ColorPuck object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The Midtones ColorPuck object.</li>
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
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoardAspect:parent() -&gt; object</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the Parent object.</p>
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
          <section id="reset">
            <a name="//apple_ref/cpp/Method/reset" class="dashAnchor"></a>
            <h5><a href="#reset">reset</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoardAspect:reset() -&gt; cp.apple.finalcutpro.inspector.color.ColorBoardAspect</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Resets the Color Board Aspect.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.apple.finalcutpro.inspector.color.ColorBoardAspect</code> object for method chaining.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="selected">
            <a name="//apple_ref/cpp/Method/selected" class="dashAnchor"></a>
            <h5><a href="#selected">selected</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoardAspect:selected() -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Is the Color Board Aspect selected?</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if selected otherwise <code>false</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="shadows">
            <a name="//apple_ref/cpp/Method/shadows" class="dashAnchor"></a>
            <h5><a href="#shadows">shadows</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoardAspect:shadows() -&gt; ColorPuck</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the Shadows ColorPuck object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The Shadows ColorPuck object.</li>
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
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoardAspect:show() -&gt; cp.apple.finalcutpro.inspector.color.ColorBoardAspect</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Shows the Color Board Aspect</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.apple.finalcutpro.inspector.color.ColorBoardAspect</code> object for method chaining.</li>
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
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoardAspect:UI() -&gt; axuielementObject</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the Color Board Aspect Accessibility Object</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>An <code>axuielementObject</code> or <code>nil</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
