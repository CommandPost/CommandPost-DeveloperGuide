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
      <h1><a href="plugins.finalcutpro.browser.playhead.md">docs</a> &raquo; plugins.finalcutpro.browser.playhead</h1>
      <p>Browser Playhead Plugin.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#changeHighlightColor">changeHighlightColor</a></li>
            <li><a href="#deleteHighlight">deleteHighlight</a></li>
            <li><a href="#getHighlightColor">getHighlightColor</a></li>
            <li><a href="#getHighlightCustomColor">getHighlightCustomColor</a></li>
            <li><a href="#getHighlightShape">getHighlightShape</a></li>
            <li><a href="#getHighlightTime">getHighlightTime</a></li>
            <li><a href="#highlight">highlight</a></li>
            <li><a href="#highlightFrame">highlightFrame</a></li>
            <li><a href="#setHighlightColor">setHighlightColor</a></li>
            <li><a href="#setHighlightCustomColor">setHighlightCustomColor</a></li>
            <li><a href="#setHighlightShape">setHighlightShape</a></li>
            <li><a href="#setHighlightTime">setHighlightTime</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Functions</h4>
          <section id="changeHighlightColor">
            <a name="//apple_ref/cpp/Function/changeHighlightColor" class="dashAnchor"></a>
            <h5><a href="#changeHighlightColor">changeHighlightColor</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.browser.playhead.changeHighlightColor([value]) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Prompts the user to change the Playhead Highlight Colour.</p>
<p>Parameters:</p>
<ul>
<li>value - An RGB table with the selected colour (see <code>hs.drawing.color</code>)</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="deleteHighlight">
            <a name="//apple_ref/cpp/Function/deleteHighlight" class="dashAnchor"></a>
            <h5><a href="#deleteHighlight">deleteHighlight</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.browser.playhead.deleteHighlight() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Delete's the highlight if it's currently visible on the screen.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="getHighlightColor">
            <a name="//apple_ref/cpp/Function/getHighlightColor" class="dashAnchor"></a>
            <h5><a href="#getHighlightColor">getHighlightColor</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.browser.playhead.getHighlightColor() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the current highlight colour.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>An RGB table with the selected colour (see <code>hs.drawing.color</code>) or <code>nil</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="getHighlightCustomColor">
            <a name="//apple_ref/cpp/Function/getHighlightCustomColor" class="dashAnchor"></a>
            <h5><a href="#getHighlightCustomColor">getHighlightCustomColor</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.browser.playhead.getHighlightCustomColor() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the current custom highlight colour.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>An RGB table with the selected colour (see <code>hs.drawing.color</code>) or <code>nil</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="getHighlightShape">
            <a name="//apple_ref/cpp/Function/getHighlightShape" class="dashAnchor"></a>
            <h5><a href="#getHighlightShape">getHighlightShape</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.browser.playhead.getHighlightShape() -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the current highlight shape.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>"Rectangle", "Circle" or "Diamond" or <code>nil</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="getHighlightTime">
            <a name="//apple_ref/cpp/Function/getHighlightTime" class="dashAnchor"></a>
            <h5><a href="#getHighlightTime">getHighlightTime</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.browser.playhead.getHighlightTime() -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the current highlight playhead time.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A number or <code>nil</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="highlight">
            <a name="//apple_ref/cpp/Function/highlight" class="dashAnchor"></a>
            <h5><a href="#highlight">highlight</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.browser.playhead.highlight() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Highlight's the Final Cut Pro Browser Playhead.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="highlightFrame">
            <a name="//apple_ref/cpp/Function/highlightFrame" class="dashAnchor"></a>
            <h5><a href="#highlightFrame">highlightFrame</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.browser.playhead.highlightFrame([frame]) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Highlights a specific frame.</p>
<p>Parameters:</p>
<ul>
<li>frame - Frame as per <code>hs.geometry.rect</code></li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="setHighlightColor">
            <a name="//apple_ref/cpp/Function/setHighlightColor" class="dashAnchor"></a>
            <h5><a href="#setHighlightColor">setHighlightColor</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.browser.playhead.setHighlightColor([value]) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Sets the Playhead Highlight Colour.</p>
<p>Parameters:</p>
<ul>
<li>value - An RGB table with the selected colour (see <code>hs.drawing.color</code>)</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="setHighlightCustomColor">
            <a name="//apple_ref/cpp/Function/setHighlightCustomColor" class="dashAnchor"></a>
            <h5><a href="#setHighlightCustomColor">setHighlightCustomColor</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.browser.playhead.setHighlightCustomColor([value]) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Sets the Custom Playhead Highlight Colour.</p>
<p>Parameters:</p>
<ul>
<li>value - An RGB table with the selected colour (see <code>hs.drawing.color</code>)</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="setHighlightShape">
            <a name="//apple_ref/cpp/Function/setHighlightShape" class="dashAnchor"></a>
            <h5><a href="#setHighlightShape">setHighlightShape</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.browser.playhead.setHighlightShape([value]) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Sets the Custom Playhead Highlight Shape.</p>
<p>Parameters:</p>
<ul>
<li>value - A string which can be "Rectangle", "Circle" or "Diamond".</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="setHighlightTime">
            <a name="//apple_ref/cpp/Function/setHighlightTime" class="dashAnchor"></a>
            <h5><a href="#setHighlightTime">setHighlightTime</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.browser.playhead.setHighlightTime([value]) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Sets the Custom Playhead Highlight Time.</p>
<p>Parameters:</p>
<ul>
<li>value - A number</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
