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
      <h1><a href="plugins.finalcutpro.fullscreen.shortcuts.md">docs</a> &raquo; plugins.finalcutpro.fullscreen.shortcuts</h1>
      <p>Fullscreen Shortcuts</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Variables - Configurable values</li>
          <ul>
            <li><a href="#enabled">enabled</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#checkCommand">checkCommand</a></li>
            <li><a href="#ninjaKeyStroke">ninjaKeyStroke</a></li>
            <li><a href="#performCommand">performCommand</a></li>
            <li><a href="#update">update</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Variables</h4>
          <section id="enabled">
            <a name="//apple_ref/cpp/Variable/enabled" class="dashAnchor"></a>
            <h5><a href="#enabled">enabled</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.fullscreen.shortcuts.enabled &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Is the module enabled?</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Functions</h4>
          <section id="checkCommand">
            <a name="//apple_ref/cpp/Function/checkCommand" class="dashAnchor"></a>
            <h5><a href="#checkCommand">checkCommand</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.fullscreen.shortcuts.checkCommand(whichModifier, whichKey) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks to see if a shortcut has been pressed, then processes.</p>
<p>Parameters:</p>
<ul>
<li>whichModifier - Which modifier key to check.</li>
<li>whichKey - Which key to check.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="ninjaKeyStroke">
            <a name="//apple_ref/cpp/Function/ninjaKeyStroke" class="dashAnchor"></a>
            <h5><a href="#ninjaKeyStroke">ninjaKeyStroke</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.fullscreen.shortcuts.ninjaKeyStroke(whichModifier, whichKey) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Performs a Ninja Key Stoke.</p>
<p>Parameters:</p>
<ul>
<li>whichModifier - Modifier Key</li>
<li>whichKey - Key</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="performCommand">
            <a name="//apple_ref/cpp/Function/performCommand" class="dashAnchor"></a>
            <h5><a href="#performCommand">performCommand</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.fullscreen.shortcuts.performCommand(cmd, whichModifier, whichKey) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Performs a command.</p>
<p>Parameters:</p>
<ul>
<li>cmd - The Command.</li>
<li>whichModifier - Which modifier key to check.</li>
<li>whichKey - Which key to check.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successful otherwise <code>false</code></li>
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
                <td><code>plugins.finalcutpro.fullscreen.shortcuts.update() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Toggles the watches for monitoring fullscreen playback.</p>
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
