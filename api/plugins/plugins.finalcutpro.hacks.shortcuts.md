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
      <h1><a href="plugins.finalcutpro.hacks.shortcuts.md">docs</a> &raquo; plugins.finalcutpro.hacks.shortcuts</h1>
      <p>Plugin that allows the user to customise the CommandPost shortcuts
via the Final Cut Pro Command Editor.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Constants - Useful values which cannot be changed</li>
          <ul>
            <li><a href="#active">active</a></li>
            <li><a href="#installed">installed</a></li>
            <li><a href="#requiresActivation">requiresActivation</a></li>
            <li><a href="#requiresDeactivation">requiresDeactivation</a></li>
            <li><a href="#supported">supported</a></li>
            <li><a href="#uninstalled">uninstalled</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#init">init</a></li>
            <li><a href="#install">install</a></li>
            <li><a href="#refresh">refresh</a></li>
            <li><a href="#uninstall">uninstall</a></li>
            <li><a href="#update">update</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Constants</h4>
          <section id="active">
            <a name="//apple_ref/cpp/Constant/active" class="dashAnchor"></a>
            <h5><a href="#active">active</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.hacks.shortcuts.active &lt;cp.prop: boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>A property that returns <code>true</code> if the FCPX shortcuts are active.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="installed">
            <a name="//apple_ref/cpp/Constant/installed" class="dashAnchor"></a>
            <h5><a href="#installed">installed</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.hacks.shortcuts.installed &lt;cp.prop: boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>A property that returns <code>true</code> if the FCPX Hacks Shortcuts are currently installed in FCPX.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="requiresActivation">
            <a name="//apple_ref/cpp/Constant/requiresActivation" class="dashAnchor"></a>
            <h5><a href="#requiresActivation">requiresActivation</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.hacks.shortcuts.requiresActivation &lt;cp.prop: boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>A property that returns <code>true</code> if the custom shortcuts are installed in FCPX but not active.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="requiresDeactivation">
            <a name="//apple_ref/cpp/Constant/requiresDeactivation" class="dashAnchor"></a>
            <h5><a href="#requiresDeactivation">requiresDeactivation</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.hacks.shortcuts.requiresDeactivation &lt;cp.prop: boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>A property that returns <code>true</code> if the FCPX shortcuts are active but shortcuts are not installed.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="supported">
            <a name="//apple_ref/cpp/Constant/supported" class="dashAnchor"></a>
            <h5><a href="#supported">supported</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.hacks.shortcuts.supported &lt;cp.prop: boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>A property that returns <code>true</code> if the a supported version of FCPX is installed.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="uninstalled">
            <a name="//apple_ref/cpp/Constant/uninstalled" class="dashAnchor"></a>
            <h5><a href="#uninstalled">uninstalled</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.hacks.shortcuts.uninstalled &lt;cp.prop: boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>A property that returns <code>true</code> if shortcuts is working on something.</p>
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
                <td><code>plugins.finalcutpro.hacks.shortcuts.init() -&gt; none</code></td>
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
          <section id="install">
            <a name="//apple_ref/cpp/Function/install" class="dashAnchor"></a>
            <h5><a href="#install">install</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.hacks.shortcuts.install(silently) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Installs the Hacks Shortcuts.</p>
<p>Parameters:</p>
<ul>
<li><code>silently</code>   - (optional) If <code>true</code>, the user will not be prompted first.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successful.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="refresh">
            <a name="//apple_ref/cpp/Function/refresh" class="dashAnchor"></a>
            <h5><a href="#refresh">refresh</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.hacks.shortcuts.refresh() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Refresh Hacks Shortcuts if they're enabled.</p>
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
          <section id="uninstall">
            <a name="//apple_ref/cpp/Function/uninstall" class="dashAnchor"></a>
            <h5><a href="#uninstall">uninstall</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.hacks.shortcuts.uninstall(silently) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Uninstalls the Hacks Shortcuts, if they have been installed</p>
<p>Parameters:</p>
<ul>
<li><code>silently</code>   - (optional) If <code>true</code>, the user will not be prompted first.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successful.</li>
</ul>
<p>Notes:</p>
<ul>
<li>Used by Trash Preferences menubar command.</li>
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
                <td><code>plugins.finalcutpro.hacks.shortcuts.update() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Read shortcut keys from the Final Cut Pro Preferences.</p>
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
