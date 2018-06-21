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
      <h1><a href="plugins.core.preferences.panels.midi.md">docs</a> &raquo; plugins.core.preferences.panels.midi</h1>
      <p>MIDI Preferences Panel</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Variables - Configurable values</li>
          <ul>
            <li><a href="#_currentlyLearning">_currentlyLearning</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#init">init</a></li>
          </ul>
        <li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
          <ul>
            <li><a href="#lastGroup">lastGroup</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Variables</h4>
          <section id="_currentlyLearning">
            <a name="//apple_ref/cpp/Variable/_currentlyLearning" class="dashAnchor"></a>
            <h5><a href="#_currentlyLearning">_currentlyLearning</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.preferences.panels.midi._currentlyLearning -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Are we in learning mode?</p>
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
                <td><code>plugins.core.preferences.panels.midi.init(deps, env) -&gt; module</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Initialise the Module.</p>
<p>Parameters:</p>
<ul>
<li>deps - Dependancies Table</li>
<li>env - Environment Table</li>
</ul>
<p>Returns:</p>
<ul>
<li>The Module</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Fields</h4>
          <section id="lastGroup">
            <a name="//apple_ref/cpp/Field/lastGroup" class="dashAnchor"></a>
            <h5><a href="#lastGroup">lastGroup</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.preferences.panels.midi.lastGroup &lt;cp.prop: string&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Last group used in the Preferences Drop Down.</p>
</td>
              </tr>
            </table>
          </section>
