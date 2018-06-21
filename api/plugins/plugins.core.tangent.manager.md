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
      <h1><a href="plugins.core.tangent.manager.md">docs</a> &raquo; plugins.core.tangent.manager</h1>
      <p>Tangent Control Surface Manager</p>
<p>This plugin allows CommandPost to communicate with Tangent's range of
panels (Element, Virtual Element Apps, Wave, Ripple and any future panels).</p>
<p>Download the Tangent Developer Support Pack &amp; Tangent Hub Installer for Mac
here: <a href="http://www.tangentwave.co.uk/developer-support">http://www.tangentwave.co.uk/developer-support</a></p>

      </header>
        <h3>Submodules</h3>
        <ul>
        <li><a href="plugins.core.tangent.manager.action.html">plugins.core.tangent.manager.action</a></li>
        <li><a href="plugins.core.tangent.manager.binding.html">plugins.core.tangent.manager.binding</a></li>
        <li><a href="plugins.core.tangent.manager.controls.html">plugins.core.tangent.manager.controls</a></li>
        <li><a href="plugins.core.tangent.manager.group.html">plugins.core.tangent.manager.group</a></li>
        <li><a href="plugins.core.tangent.manager.menu.html">plugins.core.tangent.manager.menu</a></li>
        <li><a href="plugins.core.tangent.manager.mode.html">plugins.core.tangent.manager.mode</a></li>
        <li><a href="plugins.core.tangent.manager.named.html">plugins.core.tangent.manager.named</a></li>
        <li><a href="plugins.core.tangent.manager.parameter.html">plugins.core.tangent.manager.parameter</a></li>
        </ul>
      <h3>API Overview</h3>
      <ul>
        <li>Constants - Useful values which cannot be changed</li>
          <ul>
            <li><a href="#activeMode">activeMode</a></li>
            <li><a href="#FCP_KEYPRESS_APPS_PATH">FCP_KEYPRESS_APPS_PATH</a></li>
            <li><a href="#HIDE_FILE_PATH">HIDE_FILE_PATH</a></li>
            <li><a href="#TANGENT_MAPPER_BUNDLE_ID">TANGENT_MAPPER_BUNDLE_ID</a></li>
          </ul>
        <li>Variables - Configurable values</li>
          <ul>
            <li><a href="#connectable">connectable</a></li>
            <li><a href="#connected">connected</a></li>
            <li><a href="#enabled">enabled</a></li>
            <li><a href="#interrupted">interrupted</a></li>
            <li><a href="#requiresConnection">requiresConnection</a></li>
            <li><a href="#requiresDisconnection">requiresDisconnection</a></li>
            <li><a href="#tangentHubInstalled">tangentHubInstalled</a></li>
            <li><a href="#tangentMapperInstalled">tangentMapperInstalled</a></li>
            <li><a href="#tangentMapperRunning">tangentMapperRunning</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#addMode">addMode</a></li>
            <li><a href="#areMappingsInstalled">areMappingsInstalled</a></li>
            <li><a href="#disableFinalCutProInTangentHub">disableFinalCutProInTangentHub</a></li>
            <li><a href="#getMode">getMode</a></li>
            <li><a href="#interruptWhen">interruptWhen</a></li>
            <li><a href="#launchTangentMapper">launchTangentMapper</a></li>
            <li><a href="#update">update</a></li>
            <li><a href="#updateControls">updateControls</a></li>
            <li><a href="#writeControlsXML">writeControlsXML</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Constants</h4>
          <section id="activeMode">
            <a name="//apple_ref/cpp/Constant/activeMode" class="dashAnchor"></a>
            <h5><a href="#activeMode">activeMode</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.activeMode &lt;cp.prop: mode&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Represents the currently active <code>mode</code>.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="FCP_KEYPRESS_APPS_PATH">
            <a name="//apple_ref/cpp/Constant/FCP_KEYPRESS_APPS_PATH" class="dashAnchor"></a>
            <h5><a href="#FCP_KEYPRESS_APPS_PATH">FCP_KEYPRESS_APPS_PATH</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.FCP_KEYPRESS_APPS_PATH -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Final Cut Pro Keypress Apps Path for Tangent Mapper.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="HIDE_FILE_PATH">
            <a name="//apple_ref/cpp/Constant/HIDE_FILE_PATH" class="dashAnchor"></a>
            <h5><a href="#HIDE_FILE_PATH">HIDE_FILE_PATH</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.HIDE_FILE_PATH -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Tangent Mapper Hide File Path.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="TANGENT_MAPPER_BUNDLE_ID">
            <a name="//apple_ref/cpp/Constant/TANGENT_MAPPER_BUNDLE_ID" class="dashAnchor"></a>
            <h5><a href="#TANGENT_MAPPER_BUNDLE_ID">TANGENT_MAPPER_BUNDLE_ID</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.TANGENT_MAPPER_BUNDLE_ID -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Tangent Mapper Bundle ID.</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Variables</h4>
          <section id="connectable">
            <a name="//apple_ref/cpp/Variable/connectable" class="dashAnchor"></a>
            <h5><a href="#connectable">connectable</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.connectable &lt;cp.prop: boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Is the Tangent Enabled, Not Interrupted, and the Tangent Hub Installed?</p>
</td>
              </tr>
            </table>
          </section>
          <section id="connected">
            <a name="//apple_ref/cpp/Variable/connected" class="dashAnchor"></a>
            <h5><a href="#connected">connected</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.connected &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>A <code>cp.prop</code> that tracks the connection status to the Tangent Hub.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="enabled">
            <a name="//apple_ref/cpp/Variable/enabled" class="dashAnchor"></a>
            <h5><a href="#enabled">enabled</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.enabled &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Enable or disables the Tangent Manager.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="interrupted">
            <a name="//apple_ref/cpp/Variable/interrupted" class="dashAnchor"></a>
            <h5><a href="#interrupted">interrupted</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.interrupted &lt;cp.prop: boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>If this property is <code>true</code> it will temporarily interrupt the Tangent connection, if it is enabled.
Other plugins can add interruptions via the <code>interruptWhen</code> function.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="requiresConnection">
            <a name="//apple_ref/cpp/Variable/requiresConnection" class="dashAnchor"></a>
            <h5><a href="#requiresConnection">requiresConnection</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.requiresConnection &lt;cp.prop: boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Is <code>true</code> when the Tangent Manager is both <code>enabled</code> but not <code>connected</code>.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="requiresDisconnection">
            <a name="//apple_ref/cpp/Variable/requiresDisconnection" class="dashAnchor"></a>
            <h5><a href="#requiresDisconnection">requiresDisconnection</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.requiresDisconnection &lt;cp.prop: boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Is <code>true</code> when the Tangent Manager is both not <code>enabled</code> but is <code>connected</code>.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="tangentHubInstalled">
            <a name="//apple_ref/cpp/Variable/tangentHubInstalled" class="dashAnchor"></a>
            <h5><a href="#tangentHubInstalled">tangentHubInstalled</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.tangentHubInstalled &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Is Tangent Hub Installed?</p>
</td>
              </tr>
            </table>
          </section>
          <section id="tangentMapperInstalled">
            <a name="//apple_ref/cpp/Variable/tangentMapperInstalled" class="dashAnchor"></a>
            <h5><a href="#tangentMapperInstalled">tangentMapperInstalled</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.tangentMapperInstalled &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Is Tangent Mapper Installed?</p>
</td>
              </tr>
            </table>
          </section>
          <section id="tangentMapperRunning">
            <a name="//apple_ref/cpp/Variable/tangentMapperRunning" class="dashAnchor"></a>
            <h5><a href="#tangentMapperRunning">tangentMapperRunning</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.tangentMapperRunning &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Is Tangent Mapper Running?</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Functions</h4>
          <section id="addMode">
            <a name="//apple_ref/cpp/Function/addMode" class="dashAnchor"></a>
            <h5><a href="#addMode">addMode</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.addMode(id, name) -&gt; plugins.core.tangent.manager.mode</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Adds a new <code>mode</code> with the specified details and returns it.</p>
<p>Parameters:</p>
<ul>
<li>id            - The id number of the Mode.</li>
<li>name          - The name of the Mode.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The new <code>mode</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="areMappingsInstalled">
            <a name="//apple_ref/cpp/Function/areMappingsInstalled" class="dashAnchor"></a>
            <h5><a href="#areMappingsInstalled">areMappingsInstalled</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.areMappingsInstalled() -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Are mapping files installed?</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if mapping files are installed otherwise <code>false</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="disableFinalCutProInTangentHub">
            <a name="//apple_ref/cpp/Function/disableFinalCutProInTangentHub" class="dashAnchor"></a>
            <h5><a href="#disableFinalCutProInTangentHub">disableFinalCutProInTangentHub</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.disableFinalCutProInTangentHub() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Disables the Final Cut Pro preset in the Tangent Hub Application.</p>
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
          <section id="getMode">
            <a name="//apple_ref/cpp/Function/getMode" class="dashAnchor"></a>
            <h5><a href="#getMode">getMode</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.getMode(id) -&gt; plugins.core.tangent.manager.mode</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the <code>mode</code> with the specified ID, or <code>nil</code>.</p>
<p>Parameters:</p>
<ul>
<li>id    - The ID to find.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>mode</code>, or <code>nil</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="interruptWhen">
            <a name="//apple_ref/cpp/Function/interruptWhen" class="dashAnchor"></a>
            <h5><a href="#interruptWhen">interruptWhen</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.interruptWhen(aProp) -&gt; nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Adds a <code>cp.prop</code> that will cause an interruption to the Tangent connection when it is <code>true</code>.</p>
<p>Parameters:</p>
<ul>
<li>aProp     - The <code>cp.prop</code> that may interrupt the connection.</li>
</ul>
<p>Returns:</p>
<ul>
<li>Nothing.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="launchTangentMapper">
            <a name="//apple_ref/cpp/Function/launchTangentMapper" class="dashAnchor"></a>
            <h5><a href="#launchTangentMapper">launchTangentMapper</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.launchTangentMapper() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Launches the Tangent Mapper.</p>
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
          <section id="update">
            <a name="//apple_ref/cpp/Function/update" class="dashAnchor"></a>
            <h5><a href="#update">update</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.update() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Updates the Tangent GUIs.</p>
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
          <section id="updateControls">
            <a name="//apple_ref/cpp/Function/updateControls" class="dashAnchor"></a>
            <h5><a href="#updateControls">updateControls</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.updateControls() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Update Controls.</p>
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
          <section id="writeControlsXML">
            <a name="//apple_ref/cpp/Function/writeControlsXML" class="dashAnchor"></a>
            <h5><a href="#writeControlsXML">writeControlsXML</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.writeControlsXML() -&gt; boolean, string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Writes the Tangent controls.xml File to the User's Application Support folder.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successfully created otherwise <code>false</code> if an error occurred.</li>
<li>If an error occurs an error message will also be returned as a string.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
