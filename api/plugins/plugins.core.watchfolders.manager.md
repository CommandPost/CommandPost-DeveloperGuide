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
      <h1><a href="plugins.core.watchfolders.manager.md">docs</a> &raquo; plugins.core.watchfolders.manager</h1>
      <p>Manager for the CommandPost Watch Folders Panel.</p>

      </header>
        <h3>Submodules</h3>
        <ul>
        <li><a href="plugins.core.watchfolders.manager.panel.html">plugins.core.watchfolders.manager.panel</a></li>
        </ul>
      <h3>API Overview</h3>
      <ul>
        <li>Constants - Useful values which cannot be changed</li>
          <ul>
            <li><a href="#DEFAULT_HEIGHT">DEFAULT_HEIGHT</a></li>
            <li><a href="#DEFAULT_TITLE">DEFAULT_TITLE</a></li>
            <li><a href="#DEFAULT_WIDTH">DEFAULT_WIDTH</a></li>
            <li><a href="#DEFAULT_WINDOW_STYLE">DEFAULT_WINDOW_STYLE</a></li>
            <li><a href="#position">position</a></li>
            <li><a href="#WEBVIEW_LABEL">WEBVIEW_LABEL</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#addHandler">addHandler</a></li>
            <li><a href="#addPanel">addPanel</a></li>
            <li><a href="#getHandler">getHandler</a></li>
            <li><a href="#getLabel">getLabel</a></li>
            <li><a href="#hide">hide</a></li>
            <li><a href="#init">init</a></li>
            <li><a href="#injectScript">injectScript</a></li>
            <li><a href="#maxPanelHeight">maxPanelHeight</a></li>
            <li><a href="#selectPanel">selectPanel</a></li>
            <li><a href="#setPanelRenderer">setPanelRenderer</a></li>
            <li><a href="#show">show</a></li>
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
                <td><code>plugins.core.watchfolders.manager.DEFAULT_HEIGHT -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Default Height of the Watch Folder Window</p>
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
                <td><code>plugins.core.watchfolders.manager.DEFAULT_TITLE -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Default Title of the Watch Folder Window</p>
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
                <td><code>plugins.core.watchfolders.manager.DEFAULT_WIDTH -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Default Width of the Watch Folder Window</p>
</td>
              </tr>
            </table>
          </section>
          <section id="DEFAULT_WINDOW_STYLE">
            <a name="//apple_ref/cpp/Constant/DEFAULT_WINDOW_STYLE" class="dashAnchor"></a>
            <h5><a href="#DEFAULT_WINDOW_STYLE">DEFAULT_WINDOW_STYLE</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.watchfolders.manager.DEFAULT_WINDOW_STYLE -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Table of Default Window Style</p>
</td>
              </tr>
            </table>
          </section>
          <section id="position">
            <a name="//apple_ref/cpp/Constant/position" class="dashAnchor"></a>
            <h5><a href="#position">position</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.watchfolders.manager.position &lt;cp.prop: table&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the last frame saved in settings.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="WEBVIEW_LABEL">
            <a name="//apple_ref/cpp/Constant/WEBVIEW_LABEL" class="dashAnchor"></a>
            <h5><a href="#WEBVIEW_LABEL">WEBVIEW_LABEL</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.watchfolders.manager.WEBVIEW_LABEL -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>WebView Label</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Functions</h4>
          <section id="addHandler">
            <a name="//apple_ref/cpp/Function/addHandler" class="dashAnchor"></a>
            <h5><a href="#addHandler">addHandler</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.watchfolders.manager.addHandler(id, handlerFn) -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Adds a Handler</p>
<p>Parameters:</p>
<ul>
<li>id - The ID</li>
<li>handlerFn - the handler function</li>
</ul>
<p>Returns:</p>
<ul>
<li>Nothing</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="addPanel">
            <a name="//apple_ref/cpp/Function/addPanel" class="dashAnchor"></a>
            <h5><a href="#addPanel">addPanel</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.watchfolders.manager.addPanel(params) -&gt; plugins.core.watchfolders.manager.panel</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Adds a new panel with the specified <code>params</code> to the preferences manager.</p>
<p>Parameters:</p>
<ul>
<li><code>params</code> - The parameters table. Details below.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The new <code>panel</code> instance.</li>
</ul>
<p>Notes:</p>
<ul>
<li>The <code>params</code> can have the following properties. The <code>priority</code> and <code>id</code> and properties are <strong>required</strong>.
<strong> <code>priority</code>      - An integer value specifying the priority of the panel compared to others.</strong> <code>id</code>            - A string containing the unique ID of the panel.
<strong> <code>label</code>         - The human-readable label for the panel icon.</strong> <code>image</code>         - The <code>hs.image</code> for the panel icon.
** <code>tooltip</code>       - The human-readable details for the toolbar icon when the mouse is hovering over it.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="getHandler">
            <a name="//apple_ref/cpp/Function/getHandler" class="dashAnchor"></a>
            <h5><a href="#getHandler">getHandler</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.watchfolders.manager.getHandler(id) -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the handler for a given ID.</p>
<p>Parameters:</p>
<ul>
<li>id - The ID</li>
</ul>
<p>Returns:</p>
<ul>
<li>Table</li>
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
                <td><code>plugins.core.watchfolders.manager.getLabel() -&gt; string</code></td>
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
          <section id="hide">
            <a name="//apple_ref/cpp/Function/hide" class="dashAnchor"></a>
            <h5><a href="#hide">hide</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.watchfolders.manager.hide() -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Hides the Watch Folders Window</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>True if successful or nil if an error occurred</li>
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
                <td><code>plugins.core.watchfolders.manager.init() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Initialises the Watch Folder Manager.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>Nothing</li>
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
                <td><code>plugins.core.watchfolders.manager.injectScript(script) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Injects JavaScript into the Watch Folders Webview.</p>
<p>Parameters:</p>
<ul>
<li>script - The JavaScript code you want to inject in the form of a string.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="maxPanelHeight">
            <a name="//apple_ref/cpp/Function/maxPanelHeight" class="dashAnchor"></a>
            <h5><a href="#maxPanelHeight">maxPanelHeight</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.watchfolders.manager.maxPanelHeight() -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the maximum panel height as a number</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A number</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="selectPanel">
            <a name="//apple_ref/cpp/Function/selectPanel" class="dashAnchor"></a>
            <h5><a href="#selectPanel">selectPanel</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.watchfolders.manager.selectPanel(id) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Selects a Preferences Panel.</p>
<p>Parameters:</p>
<ul>
<li>id - the ID of the panel you want to select.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
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
                <td><code>plugins.core.watchfolders.manager.setPanelRenderer(renderer) -&gt; none</code></td>
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
                <td><code>plugins.core.watchfolders.manager.show() -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Shows the Watch Folders Window</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>True if successful or nil if an error occurred</li>
</ul>
</td>
              </tr>
            </table>
          </section>
