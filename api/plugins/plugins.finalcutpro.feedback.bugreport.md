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
      <h1><a href="plugins.finalcutpro.feedback.bugreport.md">docs</a> &raquo; plugins.finalcutpro.feedback.bugreport</h1>
      <p>Sends Apple a Bug Report or Feature Request for Final Cut Pro.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Constants - Useful values which cannot be changed</li>
          <ul>
            <li><a href="#DEFAULT_HEIGHT">DEFAULT_HEIGHT</a></li>
            <li><a href="#DEFAULT_TITLE">DEFAULT_TITLE</a></li>
            <li><a href="#DEFAULT_WIDTH">DEFAULT_WIDTH</a></li>
            <li><a href="#DEFAULT_WINDOW_STYLE">DEFAULT_WINDOW_STYLE</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#open">open</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Constants</h4>
          <section id="DEFAULT_HEIGHT">
            <a name="//apple_ref/cpp/Constant/DEFAULT_HEIGHT" class="dashAnchor"></a>
            <h5><a href="#DEFAULT_HEIGHT">DEFAULT_HEIGHT</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.feedback.bugreport.DEFAULT_HEIGHT -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Default Window Height</p>
</td>
              </tr>
            </table>
          </section>
          <section id="DEFAULT_TITLE">
            <a name="//apple_ref/cpp/Constant/DEFAULT_TITLE" class="dashAnchor"></a>
            <h5><a href="#DEFAULT_TITLE">DEFAULT_TITLE</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.feedback.bugreport.DEFAULT_TITLE -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Default Window Title</p>
</td>
              </tr>
            </table>
          </section>
          <section id="DEFAULT_WIDTH">
            <a name="//apple_ref/cpp/Constant/DEFAULT_WIDTH" class="dashAnchor"></a>
            <h5><a href="#DEFAULT_WIDTH">DEFAULT_WIDTH</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.feedback.bugreport.DEFAULT_WIDTH -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Default Window Width</p>
</td>
              </tr>
            </table>
          </section>
          <section id="DEFAULT_WINDOW_STYLE">
            <a name="//apple_ref/cpp/Constant/DEFAULT_WINDOW_STYLE" class="dashAnchor"></a>
            <h5><a href="#DEFAULT_WINDOW_STYLE">DEFAULT_WINDOW_STYLE</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.feedback.bugreport.DEFAULT_WINDOW_STYLE -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Default Window Style</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Functions</h4>
          <section id="open">
            <a name="//apple_ref/cpp/Function/open" class="dashAnchor"></a>
            <h5><a href="#open">open</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.feedback.bugreport.open(bugReport) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Opens Final Cut Pro Feedback Screen</p>
<p>Parameters:</p>
<ul>
<li>bugReport - Is it a bug report or an enhancement request?</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
