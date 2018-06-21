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
      <h1><a href="cp.apple.finalcutpro.inspector.color.ColorWheel.md">docs</a> &raquo; cp.apple.finalcutpro.inspector.color.ColorWheel</h1>
      <p>Represents a single Color Well in the Color Wheels Inspector.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Constants - Useful values which cannot be changed</li>
          <ul>
            <li><a href="#TYPE">TYPE</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#matches">matches</a></li>
          </ul>
        <li>Constructors - API calls which return an object, typically one that offers API methods</li>
          <ul>
            <li><a href="#new">new</a></li>
          </ul>
        <li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
          <ul>
            <li><a href="#brightnessValue">brightnessValue</a></li>
            <li><a href="#colorOrientation">colorOrientation</a></li>
            <li><a href="#colorPosition">colorPosition</a></li>
            <li><a href="#colorValue">colorValue</a></li>
            <li><a href="#focused">focused</a></li>
            <li><a href="#isShowing">isShowing</a></li>
            <li><a href="#puckPosition">puckPosition</a></li>
            <li><a href="#saturationValue">saturationValue</a></li>
            <li><a href="#UI">UI</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#brightness">brightness</a></li>
            <li><a href="#colorWell">colorWell</a></li>
            <li><a href="#nudgeColor">nudgeColor</a></li>
            <li><a href="#reset">reset</a></li>
            <li><a href="#resetButton">resetButton</a></li>
            <li><a href="#saturation">saturation</a></li>
            <li><a href="#select">select</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Constants</h4>
          <section id="TYPE">
            <a name="//apple_ref/cpp/Constant/TYPE" class="dashAnchor"></a>
            <h5><a href="#TYPE">TYPE</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorWheel.TYPE</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The possible types of ColorWheels: MASTER, SHADOWS, MIDTONES, HIGHLIGHTS.</p>
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
                <td><code>cp.apple.finalcutpro.inspector.color.ColorWheel.matches(element)</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks if the specified element is a Color Well.</p>
<p>Parameters:</p>
<ul>
<li>element   - The element to check</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the element is a Color Well.</li>
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
                <td><code>cp.apple.finalcutpro.inspector.color.ColorWheel.new(parent, type) -&gt; ColorWheel</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new <code>ColorWheel</code> instance, with the specified parent and type.</p>
<p>Parameters:</p>
<ul>
<li>parent    - The parent object.</li>
<li>type      - The type of color wheel. Must be one of the <code>ColorWheel.TYPE</code> values.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A new <code>ColorWheel</code> instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Fields</h4>
          <section id="brightnessValue">
            <a name="//apple_ref/cpp/Field/brightnessValue" class="dashAnchor"></a>
            <h5><a href="#brightnessValue">brightnessValue</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorWheel.brightnessValue &lt;cp.prop: number&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The current brightness value, as a number between -12 and 10.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="colorOrientation">
            <a name="//apple_ref/cpp/Field/colorOrientation" class="dashAnchor"></a>
            <h5><a href="#colorOrientation">colorOrientation</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorWheel.colorOrientation &lt;cp.prop: table&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Provides the orientation of the color as a table containing an <code>up</code> and <code>right</code> value.
The values will have a range between <code>-1</code> and <code>1</code>.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="colorPosition">
            <a name="//apple_ref/cpp/Field/colorPosition" class="dashAnchor"></a>
            <h5><a href="#colorPosition">colorPosition</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorWheel.colorPosition &lt;cp.prop: point&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>X/Y screen position for the current color value of the Color Well. This ignores the bounds of the
actual Color Well circle, which only extends to 85 out of 255 values.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="colorValue">
            <a name="//apple_ref/cpp/Field/colorValue" class="dashAnchor"></a>
            <h5><a href="#colorValue">colorValue</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorWheel.colorValue &lt;cp.prop: hs.drawing.color&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The current color value, as a <code>hs.drawing.color</code> table.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="focused">
            <a name="//apple_ref/cpp/Field/focused" class="dashAnchor"></a>
            <h5><a href="#focused">focused</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorWheel.focused &lt;cp.pref: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets and sets whether the Color Well has focus.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="isShowing">
            <a name="//apple_ref/cpp/Field/isShowing" class="dashAnchor"></a>
            <h5><a href="#isShowing">isShowing</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorWheel.isShowing &lt;cp.prop: boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks if the ColorWheel is showing on screen.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="puckPosition">
            <a name="//apple_ref/cpp/Field/puckPosition" class="dashAnchor"></a>
            <h5><a href="#puckPosition">puckPosition</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorWheel.puckPosition &lt;cp.prop: point&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Absolute X/Y screen position for the puck in the Color Well. Colours outside the bounds are clamped inside the color well.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="saturationValue">
            <a name="//apple_ref/cpp/Field/saturationValue" class="dashAnchor"></a>
            <h5><a href="#saturationValue">saturationValue</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorWheel.saturationValue &lt;cp.prop: number&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The current saturation value, as a number between 0 and 10.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="UI">
            <a name="//apple_ref/cpp/Field/UI" class="dashAnchor"></a>
            <h5><a href="#UI">UI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorWheel.UI &lt;cp.prop: hs._asm.axuielement; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The <code>axuielement</code> for the ColorWheel.</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Methods</h4>
          <section id="brightness">
            <a name="//apple_ref/cpp/Method/brightness" class="dashAnchor"></a>
            <h5><a href="#brightness">brightness</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorWheel:brightness() -&gt; ValueIndicator</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the brightness <code>ValueIndicator</code> for this ColorWheel.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The brightness <code>ValueIndicator</code> instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="colorWell">
            <a name="//apple_ref/cpp/Method/colorWell" class="dashAnchor"></a>
            <h5><a href="#colorWell">colorWell</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorWheel:colorWell() -&gt; ColorWell</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the <code>ColorWell</code> for this ColorWheel.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>ColorWell</code> instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="nudgeColor">
            <a name="//apple_ref/cpp/Method/nudgeColor" class="dashAnchor"></a>
            <h5><a href="#nudgeColor">nudgeColor</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorWheel:nudgeColor(right, up) -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Nudges the <code>colorPosition</code> by <code>right</code>/<code>up</code> values. Negative <code>right</code> values shift left,
negative <code>up</code> values shift down. You may have decimal shift values.</p>
<p>Parameters:</p>
<ul>
<li><code>right</code> - The number of steps to shift right. May be negative to shift left.</li>
<li><code>up</code> - The number of pixels to shift down. May be negative to shift down.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>ColorWheel</code> instance.</li>
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
                <td><code>cp.apple.finalcutpro.inspector.color.ColorWheel:reset() -&gt; ColorWheel</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Resets the color wheel values, if the ColorWheel is showing.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The ColorWheel instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="resetButton">
            <a name="//apple_ref/cpp/Method/resetButton" class="dashAnchor"></a>
            <h5><a href="#resetButton">resetButton</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorWheel:resetButton() -&gt; Button</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the <code>Button</code> that triggers a value reset.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The reset <code>Button</code> instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="saturation">
            <a name="//apple_ref/cpp/Method/saturation" class="dashAnchor"></a>
            <h5><a href="#saturation">saturation</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorWheel:saturation() -&gt; ValueIndicator</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the saturation <code>ValueIndicator</code> for this ColorWheel.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The saturation <code>ValueIndicator</code> instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="select">
            <a name="//apple_ref/cpp/Method/select" class="dashAnchor"></a>
            <h5><a href="#select">select</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorWheel:select() -&gt; cp.apple.finalcutpro.inspector.color.ColorWheel</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Shows and selects this color wheel.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>ColorWheel</code> instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
