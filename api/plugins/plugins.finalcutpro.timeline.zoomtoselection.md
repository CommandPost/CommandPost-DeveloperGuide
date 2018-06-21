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
      <h1><a href="plugins.finalcutpro.timeline.zoomtoselection.md">docs</a> &raquo; plugins.finalcutpro.timeline.zoomtoselection</h1>
      <p>Zoom the Timeline to fit the currently-selected clips.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Constants - Useful values which cannot be changed</li>
          <ul>
            <li><a href="#DEFAULT_SHIFT">DEFAULT_SHIFT</a></li>
            <li><a href="#MIN_SHIFT">MIN_SHIFT</a></li>
            <li><a href="#SELECTION_BUFFER">SELECTION_BUFFER</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#init">init</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#zoomToSelection">zoomToSelection</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Constants</h4>
          <section id="DEFAULT_SHIFT">
            <a name="//apple_ref/cpp/Constant/DEFAULT_SHIFT" class="dashAnchor"></a>
            <h5><a href="#DEFAULT_SHIFT">DEFAULT_SHIFT</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.timeline.zoomtoselection.DEFAULT_SHIFT -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Default Shift.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="MIN_SHIFT">
            <a name="//apple_ref/cpp/Constant/MIN_SHIFT" class="dashAnchor"></a>
            <h5><a href="#MIN_SHIFT">MIN_SHIFT</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.timeline.zoomtoselection.MIN_SHIFT -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Minimum Shift.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="SELECTION_BUFFER">
            <a name="//apple_ref/cpp/Constant/SELECTION_BUFFER" class="dashAnchor"></a>
            <h5><a href="#SELECTION_BUFFER">SELECTION_BUFFER</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.timeline.zoomtoselection.SELECTION_BUFFER -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The number of pixels of buffer space to allow the selection zoom to fit.</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Functions</h4>
          <section id="init">
            <a name="//apple_ref/cpp/Function/init" class="dashAnchor"></a>
            <h5><a href="#init">init</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.timeline.zoomtoselection.init() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Initialise the module.</p>
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
        <h4 class="documentation-section">Methods</h4>
          <section id="zoomToSelection">
            <a name="//apple_ref/cpp/Method/zoomToSelection" class="dashAnchor"></a>
            <h5><a href="#zoomToSelection">zoomToSelection</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.timeline.zoomtoselection.zoomToSelection() -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Zooms the view to fit the currently-selected clips.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if there is selected content in the timeline and zooming was successful.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
