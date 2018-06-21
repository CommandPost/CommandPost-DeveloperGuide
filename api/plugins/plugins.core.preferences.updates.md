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
      <h1><a href="plugins.core.preferences.updates.md">docs</a> &raquo; plugins.core.preferences.updates</h1>
      <p>Updates Module.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#checkForUpdates">checkForUpdates</a></li>
            <li><a href="#toggleCheckForUpdates">toggleCheckForUpdates</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Functions</h4>
          <section id="checkForUpdates">
            <a name="//apple_ref/cpp/Function/checkForUpdates" class="dashAnchor"></a>
            <h5><a href="#checkForUpdates">checkForUpdates</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.preferences.updates.checkForUpdates() -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the 'Check for Updates' status</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> or <code>false</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="toggleCheckForUpdates">
            <a name="//apple_ref/cpp/Function/toggleCheckForUpdates" class="dashAnchor"></a>
            <h5><a href="#toggleCheckForUpdates">toggleCheckForUpdates</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.preferences.updates.toggleCheckForUpdates() -&gt; nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Toggles 'Check For Updates'</p>
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
