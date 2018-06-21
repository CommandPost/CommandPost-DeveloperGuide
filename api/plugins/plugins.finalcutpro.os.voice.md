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
      <h1><a href="plugins.finalcutpro.os.voice.md">docs</a> &raquo; plugins.finalcutpro.os.voice</h1>
      <p>Voice Command Plugin.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Variables - Configurable values</li>
          <ul>
            <li><a href="#active">active</a></li>
            <li><a href="#announcementsEnabled">announcementsEnabled</a></li>
            <li><a href="#commandsByTitle">commandsByTitle</a></li>
            <li><a href="#commandTitles">commandTitles</a></li>
            <li><a href="#enabled">enabled</a></li>
            <li><a href="#listening">listening</a></li>
            <li><a href="#visualAlertsEnabled">visualAlertsEnabled</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#activateCommand">activateCommand</a></li>
            <li><a href="#getCommandTitles">getCommandTitles</a></li>
            <li><a href="#new">new</a></li>
            <li><a href="#openDictationSystemPreferences">openDictationSystemPreferences</a></li>
            <li><a href="#pause">pause</a></li>
            <li><a href="#registerCommands">registerCommands</a></li>
            <li><a href="#start">start</a></li>
            <li><a href="#stop">stop</a></li>
            <li><a href="#update">update</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Variables</h4>
          <section id="active">
            <a name="//apple_ref/cpp/Variable/active" class="dashAnchor"></a>
            <h5><a href="#active">active</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.os.voice.active &lt;cp.prop: boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Are Voice Commands active? This will be true if they are both <a href="#enabled">enabled</a> and FCP is frontmost.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="announcementsEnabled">
            <a name="//apple_ref/cpp/Variable/announcementsEnabled" class="dashAnchor"></a>
            <h5><a href="#announcementsEnabled">announcementsEnabled</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.os.voice.announcementsEnabled &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Announcements Enabled?</p>
</td>
              </tr>
            </table>
          </section>
          <section id="commandsByTitle">
            <a name="//apple_ref/cpp/Variable/commandsByTitle" class="dashAnchor"></a>
            <h5><a href="#commandsByTitle">commandsByTitle</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.os.voice.commandsByTitle -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Command By Title</p>
</td>
              </tr>
            </table>
          </section>
          <section id="commandTitles">
            <a name="//apple_ref/cpp/Variable/commandTitles" class="dashAnchor"></a>
            <h5><a href="#commandTitles">commandTitles</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.os.voice.commandTitles -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Command Titles</p>
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
                <td><code>plugins.finalcutpro.os.voice.enabled &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Are Voice Commands Enabled?</p>
</td>
              </tr>
            </table>
          </section>
          <section id="listening">
            <a name="//apple_ref/cpp/Variable/listening" class="dashAnchor"></a>
            <h5><a href="#listening">listening</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.os.voice.listening &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Is the listener listening?</p>
</td>
              </tr>
            </table>
          </section>
          <section id="visualAlertsEnabled">
            <a name="//apple_ref/cpp/Variable/visualAlertsEnabled" class="dashAnchor"></a>
            <h5><a href="#visualAlertsEnabled">visualAlertsEnabled</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.os.voice.visualAlertsEnabled &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Visual Alerts Enabled?</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Functions</h4>
          <section id="activateCommand">
            <a name="//apple_ref/cpp/Function/activateCommand" class="dashAnchor"></a>
            <h5><a href="#activateCommand">activateCommand</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.os.voice.activateCommand(title) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Activate Command</p>
<p>Parameters:</p>
<ul>
<li>title - The title as a string</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="getCommandTitles">
            <a name="//apple_ref/cpp/Function/getCommandTitles" class="dashAnchor"></a>
            <h5><a href="#getCommandTitles">getCommandTitles</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.os.voice.getCommandTitles() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the Command Titles</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The command titles as a table.</li>
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
                <td><code>plugins.finalcutpro.os.voice.new() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new listener.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successful otherwise <code>false</code> if an errors occurs.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="openDictationSystemPreferences">
            <a name="//apple_ref/cpp/Function/openDictationSystemPreferences" class="dashAnchor"></a>
            <h5><a href="#openDictationSystemPreferences">openDictationSystemPreferences</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.os.voice.openDictationSystemPreferences() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Open Dictation System Preferences</p>
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
          <section id="pause">
            <a name="//apple_ref/cpp/Function/pause" class="dashAnchor"></a>
            <h5><a href="#pause">pause</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.os.voice.pause() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Stops the listener.</p>
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
          <section id="registerCommands">
            <a name="//apple_ref/cpp/Function/registerCommands" class="dashAnchor"></a>
            <h5><a href="#registerCommands">registerCommands</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.os.voice.registerCommands(commands) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Register Commands.</p>
<p>Parameters:</p>
<ul>
<li>commands - A table of commands.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The command titles as a table.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="start">
            <a name="//apple_ref/cpp/Function/start" class="dashAnchor"></a>
            <h5><a href="#start">start</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.os.voice.start() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Starts the listener.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successful otherwise <code>false</code> if an errors occurs.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="stop">
            <a name="//apple_ref/cpp/Function/stop" class="dashAnchor"></a>
            <h5><a href="#stop">stop</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.os.voice.stop() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Stops the listener.</p>
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
                <td><code>plugins.finalcutpro.os.voice.update() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Starts or stops the listener.</p>
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
