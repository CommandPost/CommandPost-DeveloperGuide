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
      <h1><a href="plugins.finalcutpro.timeline.playhead.md">docs</a> &raquo; plugins.finalcutpro.timeline.playhead</h1>
      <p>Manages features relating to the Timeline Playhead.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Variables - Configurable values</li>
          <ul>
            <li><a href="#alwaysCentered">alwaysCentered</a></li>
            <li><a href="#scrollingTimeline">scrollingTimeline</a></li>
            <li><a href="#tracking">tracking</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Variables</h4>
          <section id="alwaysCentered">
            <a name="//apple_ref/cpp/Variable/alwaysCentered" class="dashAnchor"></a>
            <h5><a href="#alwaysCentered">alwaysCentered</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.timeline.playhead.alwaysCentered &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>If <code>true</code>, the playhead will be centered in the view while scrolling.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="scrollingTimeline">
            <a name="//apple_ref/cpp/Variable/scrollingTimeline" class="dashAnchor"></a>
            <h5><a href="#scrollingTimeline">scrollingTimeline</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.timeline.playhead.scrollingTimeline &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Enables or disables the scrolling timeline.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="tracking">
            <a name="//apple_ref/cpp/Variable/tracking" class="dashAnchor"></a>
            <h5><a href="#tracking">tracking</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.timeline.playhead.tracking &lt;cp.prop: boolean; read-only; live&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>If <code>true</code>, we are tracking the playhead position.</p>
</td>
              </tr>
            </table>
          </section>
