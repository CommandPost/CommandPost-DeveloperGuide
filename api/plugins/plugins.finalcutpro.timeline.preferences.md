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
      <h1><a href="plugins.finalcutpro.timeline.preferences.md">docs</a> &raquo; plugins.finalcutpro.timeline.preferences</h1>
      <p>Final Cut Pro Timeline Preferences.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Variables - Configurable values</li>
          <ul>
            <li><a href="#backgroundRender">backgroundRender</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#getAutoRenderDelay">getAutoRenderDelay</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Variables</h4>
          <section id="backgroundRender">
            <a name="//apple_ref/cpp/Variable/backgroundRender" class="dashAnchor"></a>
            <h5><a href="#backgroundRender">backgroundRender</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.timeline.preferences.backgroundRender &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Is Background Render enabled?</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Functions</h4>
          <section id="getAutoRenderDelay">
            <a name="//apple_ref/cpp/Function/getAutoRenderDelay" class="dashAnchor"></a>
            <h5><a href="#getAutoRenderDelay">getAutoRenderDelay</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.timeline.preferences.getAutoRenderDelay() -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the 'FFAutoRenderDelay' value from the Final Cut Pro Preferences file.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>'FFAutoRenderDelay' value as number.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
