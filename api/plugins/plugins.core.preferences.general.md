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
      <h1><a href="plugins.core.preferences.general.md">docs</a> &raquo; plugins.core.preferences.general</h1>
      <p>General Preferences Panel.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#openPrivacyPolicy">openPrivacyPolicy</a></li>
          </ul>
        <li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
          <ul>
            <li><a href="#autoLaunch">autoLaunch</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Functions</h4>
          <section id="openPrivacyPolicy">
            <a name="//apple_ref/cpp/Function/openPrivacyPolicy" class="dashAnchor"></a>
            <h5><a href="#openPrivacyPolicy">openPrivacyPolicy</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.preferences.general.openPrivacyPolicy() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Opens the CommandPost Privacy Policy in your browser.</p>
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
        <h4 class="documentation-section">Fields</h4>
          <section id="autoLaunch">
            <a name="//apple_ref/cpp/Field/autoLaunch" class="dashAnchor"></a>
            <h5><a href="#autoLaunch">autoLaunch</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.preferences.general.autoLaunch &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Controls if CommandPost will automatically upload crash data to the developer.</p>
</td>
              </tr>
            </table>
          </section>
