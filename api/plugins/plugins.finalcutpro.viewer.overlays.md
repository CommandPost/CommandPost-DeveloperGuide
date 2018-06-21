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
      <h1><a href="plugins.finalcutpro.viewer.overlays.md">docs</a> &raquo; plugins.finalcutpro.viewer.overlays</h1>
      <p>Final Cut Pro Viewer Overlays.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Variables - Configurable values</li>
          <ul>
            <li><a href="#activeMemory">activeMemory</a></li>
            <li><a href="#basicGridEnabled">basicGridEnabled</a></li>
            <li><a href="#customGridColor">customGridColor</a></li>
            <li><a href="#disabled">disabled</a></li>
            <li><a href="#draggableGuideEnabled">draggableGuideEnabled</a></li>
            <li><a href="#gridAlpha">gridAlpha</a></li>
            <li><a href="#gridColor">gridColor</a></li>
            <li><a href="#gridSpacing">gridSpacing</a></li>
            <li><a href="#guidePosition">guidePosition</a></li>
            <li><a href="#stillsLayout">stillsLayout</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#getMemory">getMemory</a></li>
            <li><a href="#getStillsFolderPath">getStillsFolderPath</a></li>
            <li><a href="#getViewerUI">getViewerUI</a></li>
            <li><a href="#hide">hide</a></li>
            <li><a href="#saveMemory">saveMemory</a></li>
            <li><a href="#setCustomGridColor">setCustomGridColor</a></li>
            <li><a href="#setGridAlpha">setGridAlpha</a></li>
            <li><a href="#setGridColor">setGridColor</a></li>
            <li><a href="#setGridSpacing">setGridSpacing</a></li>
            <li><a href="#show">show</a></li>
            <li><a href="#update">update</a></li>
            <li><a href="#viewMemory">viewMemory</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Variables</h4>
          <section id="activeMemory">
            <a name="//apple_ref/cpp/Variable/activeMemory" class="dashAnchor"></a>
            <h5><a href="#activeMemory">activeMemory</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.viewer.overlays.activeMemory &lt;cp.prop: number&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Viewer Custom Grid Color as HTML value</p>
</td>
              </tr>
            </table>
          </section>
          <section id="basicGridEnabled">
            <a name="//apple_ref/cpp/Variable/basicGridEnabled" class="dashAnchor"></a>
            <h5><a href="#basicGridEnabled">basicGridEnabled</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.viewer.overlays.basicGridEnabled &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Is Viewer Grid Enabled?</p>
</td>
              </tr>
            </table>
          </section>
          <section id="customGridColor">
            <a name="//apple_ref/cpp/Variable/customGridColor" class="dashAnchor"></a>
            <h5><a href="#customGridColor">customGridColor</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.viewer.overlays.customGridColor &lt;cp.prop: string&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Viewer Custom Grid Color as HTML value</p>
</td>
              </tr>
            </table>
          </section>
          <section id="disabled">
            <a name="//apple_ref/cpp/Variable/disabled" class="dashAnchor"></a>
            <h5><a href="#disabled">disabled</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.viewer.overlays.disabled &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Are all the Viewer Overlay's disabled?</p>
</td>
              </tr>
            </table>
          </section>
          <section id="draggableGuideEnabled">
            <a name="//apple_ref/cpp/Variable/draggableGuideEnabled" class="dashAnchor"></a>
            <h5><a href="#draggableGuideEnabled">draggableGuideEnabled</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.viewer.overlays.draggableGuideEnabled &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Is Viewer Grid Enabled?</p>
</td>
              </tr>
            </table>
          </section>
          <section id="gridAlpha">
            <a name="//apple_ref/cpp/Variable/gridAlpha" class="dashAnchor"></a>
            <h5><a href="#gridAlpha">gridAlpha</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.viewer.overlays.gridAlpha &lt;cp.prop: number&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Viewer Grid Alpha</p>
</td>
              </tr>
            </table>
          </section>
          <section id="gridColor">
            <a name="//apple_ref/cpp/Variable/gridColor" class="dashAnchor"></a>
            <h5><a href="#gridColor">gridColor</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.viewer.overlays.gridColor &lt;cp.prop: string&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Viewer Grid Color as HTML value</p>
</td>
              </tr>
            </table>
          </section>
          <section id="gridSpacing">
            <a name="//apple_ref/cpp/Variable/gridSpacing" class="dashAnchor"></a>
            <h5><a href="#gridSpacing">gridSpacing</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.viewer.overlays.gridSpacing &lt;cp.prop: number&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Viewer Custom Grid Color as HTML value</p>
</td>
              </tr>
            </table>
          </section>
          <section id="guidePosition">
            <a name="//apple_ref/cpp/Variable/guidePosition" class="dashAnchor"></a>
            <h5><a href="#guidePosition">guidePosition</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.viewer.overlays.guidePosition &lt;cp.prop: table&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Guide Position.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="stillsLayout">
            <a name="//apple_ref/cpp/Variable/stillsLayout" class="dashAnchor"></a>
            <h5><a href="#stillsLayout">stillsLayout</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.viewer.overlays.stillsLayout &lt;cp.prop: string&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Stills layout.</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Functions</h4>
          <section id="getMemory">
            <a name="//apple_ref/cpp/Function/getMemory" class="dashAnchor"></a>
            <h5><a href="#getMemory">getMemory</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.viewer.overlays.getMemory(id) -&gt; image | nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets an image from memory.</p>
<p>Parameters:</p>
<ul>
<li>id - The ID of the memory you want to retrieve.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The memory as a <code>hs.image</code> or <code>nil</code> if the memory could not be retrieved.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="getStillsFolderPath">
            <a name="//apple_ref/cpp/Function/getStillsFolderPath" class="dashAnchor"></a>
            <h5><a href="#getStillsFolderPath">getStillsFolderPath</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.viewer.overlays.getStillsFolderPath() -&gt; string | nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the stills folder path.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The stills folder path as a string or <code>nil</code> if an error occurs.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="getViewerUI">
            <a name="//apple_ref/cpp/Function/getViewerUI" class="dashAnchor"></a>
            <h5><a href="#getViewerUI">getViewerUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.viewer.overlays.getViewerUI() -&gt; axuielementObject</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the Viewer UI.</p>
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
          <section id="hide">
            <a name="//apple_ref/cpp/Function/hide" class="dashAnchor"></a>
            <h5><a href="#hide">hide</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.viewer.overlays.hide() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Hides the Viewer Grid.</p>
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
          <section id="saveMemory">
            <a name="//apple_ref/cpp/Function/saveMemory" class="dashAnchor"></a>
            <h5><a href="#saveMemory">saveMemory</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.viewer.overlays.saveMemory() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Saves a still frame to file.</p>
<p>Parameters:</p>
<ul>
<li>id - An identifier in the form of a number.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="setCustomGridColor">
            <a name="//apple_ref/cpp/Function/setCustomGridColor" class="dashAnchor"></a>
            <h5><a href="#setCustomGridColor">setCustomGridColor</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.viewer.overlays.setCustomGridColor() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Pops up a Color Dialog box allowing the user to select a custom colour for grid lines.</p>
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
          <section id="setGridAlpha">
            <a name="//apple_ref/cpp/Function/setGridAlpha" class="dashAnchor"></a>
            <h5><a href="#setGridAlpha">setGridAlpha</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.viewer.overlays.setGridAlpha(value) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Sets Grid Alpha.</p>
<p>Parameters:</p>
<ul>
<li>value - The value you want to set.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="setGridColor">
            <a name="//apple_ref/cpp/Function/setGridColor" class="dashAnchor"></a>
            <h5><a href="#setGridColor">setGridColor</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.viewer.overlays.setGridColor(value) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Sets Grid Color.</p>
<p>Parameters:</p>
<ul>
<li>value - The value you want to set.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="setGridSpacing">
            <a name="//apple_ref/cpp/Function/setGridSpacing" class="dashAnchor"></a>
            <h5><a href="#setGridSpacing">setGridSpacing</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.viewer.overlays.setGridSpacing(value) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Sets Grid Spacing.</p>
<p>Parameters:</p>
<ul>
<li>value - The value you want to set.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="show">
            <a name="//apple_ref/cpp/Function/show" class="dashAnchor"></a>
            <h5><a href="#show">show</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.viewer.overlays.show() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Show's the Viewer Grid.</p>
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
          <section id="update">
            <a name="//apple_ref/cpp/Function/update" class="dashAnchor"></a>
            <h5><a href="#update">update</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.viewer.overlays.update() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Updates the Viewer Grid.</p>
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
          <section id="viewMemory">
            <a name="//apple_ref/cpp/Function/viewMemory" class="dashAnchor"></a>
            <h5><a href="#viewMemory">viewMemory</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.viewer.overlays.viewMemory(id) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>View a memory.</p>
<p>Parameters:</p>
<ul>
<li>id - The ID of the memory you want to retrieve.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
