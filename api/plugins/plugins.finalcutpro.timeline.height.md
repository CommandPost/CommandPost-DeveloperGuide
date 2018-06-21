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
      <h1><a href="plugins.finalcutpro.timeline.height.md">docs</a> &raquo; plugins.finalcutpro.timeline.height</h1>
      <p>Shortcut for changing Final Cut Pro's Timeline Height</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Variables - Configurable values</li>
          <ul>
            <li><a href="#changeTimelineClipHeightAlreadyInProgress">changeTimelineClipHeightAlreadyInProgress</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#changeTimelineClipHeight">changeTimelineClipHeight</a></li>
            <li><a href="#changeTimelineClipHeightRelease">changeTimelineClipHeightRelease</a></li>
            <li><a href="#shiftClipHeight">shiftClipHeight</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Variables</h4>
          <section id="changeTimelineClipHeightAlreadyInProgress">
            <a name="//apple_ref/cpp/Variable/changeTimelineClipHeightAlreadyInProgress" class="dashAnchor"></a>
            <h5><a href="#changeTimelineClipHeightAlreadyInProgress">changeTimelineClipHeightAlreadyInProgress</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.timeline.height.changeTimelineClipHeightAlreadyInProgress -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Change timeline clip height already in progress.</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Functions</h4>
          <section id="changeTimelineClipHeight">
            <a name="//apple_ref/cpp/Function/changeTimelineClipHeight" class="dashAnchor"></a>
            <h5><a href="#changeTimelineClipHeight">changeTimelineClipHeight</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.timeline.height.changeTimelineClipHeight(direction) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Change the Timeline Clip Height</p>
<p>Parameters:</p>
<ul>
<li>direction - "up" or "down"</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="changeTimelineClipHeightRelease">
            <a name="//apple_ref/cpp/Function/changeTimelineClipHeightRelease" class="dashAnchor"></a>
            <h5><a href="#changeTimelineClipHeightRelease">changeTimelineClipHeightRelease</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.timeline.height.changeTimelineClipHeightRelease() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Change Timeline Clip Height Release.</p>
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
          <section id="shiftClipHeight">
            <a name="//apple_ref/cpp/Function/shiftClipHeight" class="dashAnchor"></a>
            <h5><a href="#shiftClipHeight">shiftClipHeight</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.timeline.height.shiftClipHeight(direction) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Shift Clip Height</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successful otherwise <code>false</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
