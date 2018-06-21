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
      <h1><a href="plugins.finalcutpro.timeline.matchframe.md">docs</a> &raquo; plugins.finalcutpro.timeline.matchframe</h1>
      <p>Match Frame Tools for Final Cut Pro.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#getMulticamAngleFromSelectedClip">getMulticamAngleFromSelectedClip</a></li>
            <li><a href="#matchFrame">matchFrame</a></li>
            <li><a href="#multicamMatchFrame">multicamMatchFrame</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Functions</h4>
          <section id="getMulticamAngleFromSelectedClip">
            <a name="//apple_ref/cpp/Function/getMulticamAngleFromSelectedClip" class="dashAnchor"></a>
            <h5><a href="#getMulticamAngleFromSelectedClip">getMulticamAngleFromSelectedClip</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.timeline.matchframe.getMulticamAngleFromSelectedClip() -&gt; angle | boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Get Multicam Angle From Selected Clip</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>Angle or <code>false</code> on error</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="matchFrame">
            <a name="//apple_ref/cpp/Function/matchFrame" class="dashAnchor"></a>
            <h5><a href="#matchFrame">matchFrame</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.timeline.matchframe.matchFrame() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Performs a Single Match Frame.</p>
<p>Parameters:</p>
<ul>
<li><code>focus</code>  - If set to <code>true</code>, the library will search for the matched clip title</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="multicamMatchFrame">
            <a name="//apple_ref/cpp/Function/multicamMatchFrame" class="dashAnchor"></a>
            <h5><a href="#multicamMatchFrame">multicamMatchFrame</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.timeline.matchframe.multicamMatchFrame(goBackToTimeline) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Multicam Match Frame</p>
<p>Parameters:</p>
<ul>
<li>goBackToTimeline - <code>true</code> if you want to go back to the timeline after opening the clip in the Multicam Editor</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
