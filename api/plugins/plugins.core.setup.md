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
      <h1><a href="plugins.core.setup.md">docs</a> &raquo; plugins.core.setup</h1>
      <p>Manager for the CommandPost Setup Screen.</p>

      </header>
        <h3>Submodules</h3>
        <ul>
        <li><a href="plugins.core.setup.panel.html">plugins.core.setup.panel</a></li>
        </ul>
      <h3>API Overview</h3>
      <ul>
        <li>Constants - Useful values which cannot be changed</li>
          <ul>
            <li><a href="#DEFAULT_HEIGHT">DEFAULT_HEIGHT</a></li>
            <li><a href="#DEFAULT_TITLE">DEFAULT_TITLE</a></li>
            <li><a href="#DEFAULT_WIDTH">DEFAULT_WIDTH</a></li>
            <li><a href="#enabled">enabled</a></li>
            <li><a href="#FIRST_PRIORITY">FIRST_PRIORITY</a></li>
            <li><a href="#LAST_PRIORITY">LAST_PRIORITY</a></li>
            <li><a href="#visible">visible</a></li>
          </ul>
        <li>Variables - Configurable values</li>
          <ul>
            <li><a href="#onboardingRequired">onboardingRequired</a></li>
            <li><a href="#position">position</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#addPanel">addPanel</a></li>
            <li><a href="#currentPanel">currentPanel</a></li>
            <li><a href="#delete">delete</a></li>
            <li><a href="#focus">focus</a></li>
            <li><a href="#getLabel">getLabel</a></li>
            <li><a href="#init">init</a></li>
            <li><a href="#injectScript">injectScript</a></li>
            <li><a href="#new">new</a></li>
            <li><a href="#nextPanel">nextPanel</a></li>
            <li><a href="#setPanelRenderer">setPanelRenderer</a></li>
            <li><a href="#show">show</a></li>
            <li><a href="#update">update</a></li>
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
                <td><code>plugins.core.setup.DEFAULT_HEIGHT -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The default panel height.</p>
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
                <td><code>plugins.core.setup.DEFAULT_TITLE -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The default panel title.</p>
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
                <td><code>plugins.core.setup.DEFAULT_WIDTH -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The default panel width.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="enabled">
            <a name="//apple_ref/cpp/Constant/enabled" class="dashAnchor"></a>
            <h5><a href="#enabled">enabled</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.setup.enabled &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Set to <code>true</code> if the manager is enabled. Defaults to <code>false</code>.
Panels can be added while disabled. Once enabled, the window will appear and display the panels.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="FIRST_PRIORITY">
            <a name="//apple_ref/cpp/Constant/FIRST_PRIORITY" class="dashAnchor"></a>
            <h5><a href="#FIRST_PRIORITY">FIRST_PRIORITY</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.setup.FIRST_PRIORITY -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The first panel priority.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="LAST_PRIORITY">
            <a name="//apple_ref/cpp/Constant/LAST_PRIORITY" class="dashAnchor"></a>
            <h5><a href="#LAST_PRIORITY">LAST_PRIORITY</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.setup.LAST_PRIORITY -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The last panel priority.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="visible">
            <a name="//apple_ref/cpp/Constant/visible" class="dashAnchor"></a>
            <h5><a href="#visible">visible</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.setup.visible &lt;cp.prop: boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>A property indicating if the welcome window is visible on screen.</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Variables</h4>
          <section id="onboardingRequired">
            <a name="//apple_ref/cpp/Variable/onboardingRequired" class="dashAnchor"></a>
            <h5><a href="#onboardingRequired">onboardingRequired</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.setup.onboardingRequired &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Set to <code>true</code> if on-boarding is required otherwise <code>false</code>. Defaults to <code>true</code>.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="position">
            <a name="//apple_ref/cpp/Variable/position" class="dashAnchor"></a>
            <h5><a href="#position">position</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.setup.position &lt;cp.prop: table&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The last known position of the Setup Window as a frame.</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Functions</h4>
          <section id="addPanel">
            <a name="//apple_ref/cpp/Function/addPanel" class="dashAnchor"></a>
            <h5><a href="#addPanel">addPanel</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.setup.addPanel(newPanel) -&gt; panel</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Adds the new panel to the manager. Panels are created via the
<code>plugins.core.setup.panel.new(...)</code> function.</p>
<p>If the Setup Manager is <code>enabled</code>, the window will be displayed
immediately when a panel is added.</p>
<p>Parameters:</p>
<ul>
<li><code>newPanel</code>   - The panel to add.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The manager.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="currentPanel">
            <a name="//apple_ref/cpp/Function/currentPanel" class="dashAnchor"></a>
            <h5><a href="#currentPanel">currentPanel</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.setup.currentPanel() -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The Current Panel</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The current panel as a string</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="delete">
            <a name="//apple_ref/cpp/Function/delete" class="dashAnchor"></a>
            <h5><a href="#delete">delete</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.setup.delete() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Deletes the Setup Panels.</p>
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
          <section id="focus">
            <a name="//apple_ref/cpp/Function/focus" class="dashAnchor"></a>
            <h5><a href="#focus">focus</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.setup.focus() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Focuses on the Setup Panels window.</p>
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
          <section id="getLabel">
            <a name="//apple_ref/cpp/Function/getLabel" class="dashAnchor"></a>
            <h5><a href="#getLabel">getLabel</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.setup.getLabel() -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the Webview label.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The Webview label as a string.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="init">
            <a name="//apple_ref/cpp/Function/init" class="dashAnchor"></a>
            <h5><a href="#init">init</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.setup.init(env) -&gt; module</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Initialises the module.</p>
<p>Parameters:</p>
<ul>
<li>env - The plugin environment table</li>
</ul>
<p>Returns:</p>
<ul>
<li>The Module</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="injectScript">
            <a name="//apple_ref/cpp/Function/injectScript" class="dashAnchor"></a>
            <h5><a href="#injectScript">injectScript</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.setup.injectScript(script) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Injects JavaScript into the Setup Panels.</p>
<p>Parameters:</p>
<ul>
<li>script - The JavaScript you want to inject as a string.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="new">
            <a name="//apple_ref/cpp/Function/new" class="dashAnchor"></a>
            <h5><a href="#new">new</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.setup.new() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates the Setup Panels.</p>
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
          <section id="nextPanel">
            <a name="//apple_ref/cpp/Function/nextPanel" class="dashAnchor"></a>
            <h5><a href="#nextPanel">nextPanel</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.setup.nextPanel() -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Moves to the next panel. If the window is visible, the panel will be updated.
If no panels are left in the queue, the window will be closed.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if there was another panel to move to, or <code>false</code> if no panels remain.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="setPanelRenderer">
            <a name="//apple_ref/cpp/Function/setPanelRenderer" class="dashAnchor"></a>
            <h5><a href="#setPanelRenderer">setPanelRenderer</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.setup.setPanelRenderer(renderer) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Sets a Panel Renderer</p>
<p>Parameters:</p>
<ul>
<li>renderer - The renderer</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="show">
            <a name="//apple_ref/cpp/Function/show" class="dashAnchor"></a>
            <h5><a href="#show">show</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.setup.show() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Shows the Setup Panels.</p>
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
                <td><code>plugins.core.setup.update() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Updates the Setup Panels.</p>
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
