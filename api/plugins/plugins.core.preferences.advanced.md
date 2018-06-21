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
      <h1><a href="plugins.core.preferences.advanced.md">docs</a> &raquo; plugins.core.preferences.advanced</h1>
      <p>Advanced Preferences Panel.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Variables - Configurable values</li>
          <ul>
            <li><a href="#openErrorLogOnDockClick">openErrorLogOnDockClick</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#openErrorLog">openErrorLog</a></li>
            <li><a href="#toggleCommandLineTool">toggleCommandLineTool</a></li>
            <li><a href="#toggleDeveloperMode">toggleDeveloperMode</a></li>
            <li><a href="#toggleEnableAutomaticScriptReloading">toggleEnableAutomaticScriptReloading</a></li>
            <li><a href="#trashPreferences">trashPreferences</a></li>
          </ul>
        <li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
          <ul>
            <li><a href="#developerMode">developerMode</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Variables</h4>
          <section id="openErrorLogOnDockClick">
            <a name="//apple_ref/cpp/Variable/openErrorLogOnDockClick" class="dashAnchor"></a>
            <h5><a href="#openErrorLogOnDockClick">openErrorLogOnDockClick</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.preferences.advanced.openErrorLogOnDockClick &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Open Error Log on Dock Icon Click.</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Functions</h4>
          <section id="openErrorLog">
            <a name="//apple_ref/cpp/Function/openErrorLog" class="dashAnchor"></a>
            <h5><a href="#openErrorLog">openErrorLog</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.preferences.advanced.openErrorLog() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Opens the Error Log</p>
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
          <section id="toggleCommandLineTool">
            <a name="//apple_ref/cpp/Function/toggleCommandLineTool" class="dashAnchor"></a>
            <h5><a href="#toggleCommandLineTool">toggleCommandLineTool</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.preferences.advanced.toggleCommandLineTool() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Toggles the Command Line Tool</p>
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
          <section id="toggleDeveloperMode">
            <a name="//apple_ref/cpp/Function/toggleDeveloperMode" class="dashAnchor"></a>
            <h5><a href="#toggleDeveloperMode">toggleDeveloperMode</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.preferences.advanced.toggleDeveloperMode() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Toggles the Developer Mode.</p>
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
          <section id="toggleEnableAutomaticScriptReloading">
            <a name="//apple_ref/cpp/Function/toggleEnableAutomaticScriptReloading" class="dashAnchor"></a>
            <h5><a href="#toggleEnableAutomaticScriptReloading">toggleEnableAutomaticScriptReloading</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.preferences.advanced.toggleEnableAutomaticScriptReloading() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Toggles the Automatic Script Reloading.</p>
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
          <section id="trashPreferences">
            <a name="//apple_ref/cpp/Function/trashPreferences" class="dashAnchor"></a>
            <h5><a href="#trashPreferences">trashPreferences</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.preferences.advanced.trashPreferences() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Resets all of the CommandPost Preferences to their default values.</p>
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
          <section id="developerMode">
            <a name="//apple_ref/cpp/Field/developerMode" class="dashAnchor"></a>
            <h5><a href="#developerMode">developerMode</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.preferences.advanced.developerMode &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Enables or disables developer mode.</p>
</td>
              </tr>
            </table>
          </section>
