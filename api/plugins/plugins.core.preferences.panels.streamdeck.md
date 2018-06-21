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
      <h1><a href="plugins.core.preferences.panels.streamdeck.md">docs</a> &raquo; plugins.core.preferences.panels.streamdeck</h1>
      <p>Stream Deck Preferences Panel</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Variables - Configurable values</li>
          <ul>
            <li><a href="#defaultIconPath">defaultIconPath</a></li>
            <li><a href="#supportedExtensions">supportedExtensions</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#getGroupEditor">getGroupEditor</a></li>
            <li><a href="#init">init</a></li>
            <li><a href="#setGroupEditor">setGroupEditor</a></li>
          </ul>
        <li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
          <ul>
            <li><a href="#enabled">enabled</a></li>
            <li><a href="#lastGroup">lastGroup</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Variables</h4>
          <section id="defaultIconPath">
            <a name="//apple_ref/cpp/Variable/defaultIconPath" class="dashAnchor"></a>
            <h5><a href="#defaultIconPath">defaultIconPath</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.preferences.panels.streamdeck.defaultIconPath -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Default Path where built-in icons are stored</p>
</td>
              </tr>
            </table>
          </section>
          <section id="supportedExtensions">
            <a name="//apple_ref/cpp/Variable/supportedExtensions" class="dashAnchor"></a>
            <h5><a href="#supportedExtensions">supportedExtensions</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.preferences.panels.streamdeck.supportedExtensions -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Table of supported extensions for Stream Deck Icons.</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Functions</h4>
          <section id="getGroupEditor">
            <a name="//apple_ref/cpp/Function/getGroupEditor" class="dashAnchor"></a>
            <h5><a href="#getGroupEditor">getGroupEditor</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.preferences.panels.streamdeck.getGroupEditor(groupId) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the Group Editor</p>
<p>Parameters:</p>
<ul>
<li>groupId - Group ID</li>
</ul>
<p>Returns:</p>
<ul>
<li>Group Editor</li>
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
                <td><code>plugins.core.preferences.panels.streamdeck.init(deps, env) -&gt; module</code></td>
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
          <section id="setGroupEditor">
            <a name="//apple_ref/cpp/Function/setGroupEditor" class="dashAnchor"></a>
            <h5><a href="#setGroupEditor">setGroupEditor</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.preferences.panels.streamdeck.setGroupEditor(groupId, editorFn) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Sets the Group Editor</p>
<p>Parameters:</p>
<ul>
<li>groupId - Group ID</li>
<li>editorFn - Editor Function</li>
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
          <section id="enabled">
            <a name="//apple_ref/cpp/Field/enabled" class="dashAnchor"></a>
            <h5><a href="#enabled">enabled</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.preferences.panels.streamdeck.enabled &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Enable or disable Stream Deck Support.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="lastGroup">
            <a name="//apple_ref/cpp/Field/lastGroup" class="dashAnchor"></a>
            <h5><a href="#lastGroup">lastGroup</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.preferences.panels.streamdeck.lastGroup &lt;cp.prop: string&gt;</code></td>
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
