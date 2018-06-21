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
      <h1><a href="plugins.finalcutpro.export.batch.manager.md">docs</a> &raquo; plugins.finalcutpro.export.batch.manager</h1>
      <p>Manager for the Batch Export Window.</p>

      </header>
        <h3>Submodules</h3>
        <ul>
        <li><a href="plugins.finalcutpro.export.batch.manager.panel.html">plugins.finalcutpro.export.batch.manager.panel</a></li>
        </ul>
      <h3>API Overview</h3>
      <ul>
        <li>Constants - Useful values which cannot be changed</li>
          <ul>
            <li><a href="#DEFAULT_HEIGHT">DEFAULT_HEIGHT</a></li>
            <li><a href="#DEFAULT_TITLE">DEFAULT_TITLE</a></li>
            <li><a href="#DEFAULT_WIDTH">DEFAULT_WIDTH</a></li>
            <li><a href="#DEFAULT_WINDOW_STYLE">DEFAULT_WINDOW_STYLE</a></li>
            <li><a href="#lastTab">lastTab</a></li>
            <li><a href="#position">position</a></li>
            <li><a href="#WEBVIEW_LABEL">WEBVIEW_LABEL</a></li>
          </ul>
        <li>Variables - Configurable values</li>
          <ul>
            <li><a href="#_handlers">_handlers</a></li>
            <li><a href="#_panels">_panels</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#addHandler">addHandler</a></li>
            <li><a href="#addPanel">addPanel</a></li>
            <li><a href="#disabledPanels">disabledPanels</a></li>
            <li><a href="#focus">focus</a></li>
            <li><a href="#getHandler">getHandler</a></li>
            <li><a href="#getLabel">getLabel</a></li>
            <li><a href="#getWebview">getWebview</a></li>
            <li><a href="#hide">hide</a></li>
            <li><a href="#init">init</a></li>
            <li><a href="#injectScript">injectScript</a></li>
            <li><a href="#maxPanelHeight">maxPanelHeight</a></li>
            <li><a href="#new">new</a></li>
            <li><a href="#refresh">refresh</a></li>
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
                <td><code>plugins.finalcutpro.export.batch.manager.DEFAULT_HEIGHT -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Default Height of Preferences Window</p>
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
                <td><code>plugins.finalcutpro.export.batch.manager.DEFAULT_TITLE -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Default Title of Preferences Window</p>
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
                <td><code>plugins.finalcutpro.export.batch.manager.DEFAULT_WIDTH -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Default Width of Preferences Window</p>
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
                <td><code>plugins.finalcutpro.export.batch.manager.DEFAULT_WINDOW_STYLE -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Default Webview Window Style of Preferences Window</p>
</td>
              </tr>
            </table>
          </section>
          <section id="lastTab">
            <a name="//apple_ref/cpp/Constant/lastTab" class="dashAnchor"></a>
            <h5><a href="#lastTab">lastTab</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.export.batch.manager.lastTab</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the last tab saved in settings.</p>
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
                <td><code>plugins.finalcutpro.export.batch.manager.position</code></td>
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
                <td><code>plugins.finalcutpro.export.batch.manager.WEBVIEW_LABEL -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The WebView Label</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Variables</h4>
          <section id="_handlers">
            <a name="//apple_ref/cpp/Variable/_handlers" class="dashAnchor"></a>
            <h5><a href="#_handlers">_handlers</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.export.batch.manager._handlers -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Table containing handlers.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="_panels">
            <a name="//apple_ref/cpp/Variable/_panels" class="dashAnchor"></a>
            <h5><a href="#_panels">_panels</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.export.batch.manager._panels -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Table containing panels.</p>
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
                <td><code>plugins.finalcutpro.export.batch.manager.addHandler(id, handlerFn) -&gt; string</code></td>
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
                <td><code>plugins.finalcutpro.export.batch.manager.addPanel(params) -&gt; plugins.finalcutpro.export.batch.manager.panel</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Adds a new panel with the specified <code>params</code> to the Batch Export manager.</p>
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
<strong> <code>tooltip</code>       - The human-readable details for the toolbar icon when the mouse is hovering over it.</strong> <code>closeFn</code>       - A callback function that's triggered when the Preferences window is closed.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="disabledPanels">
            <a name="//apple_ref/cpp/Function/disabledPanels" class="dashAnchor"></a>
            <h5><a href="#disabledPanels">disabledPanels</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.export.batch.manager.disabledPanels(ids) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Sets which panels are disabled.</p>
<p>Parameters:</p>
<ul>
<li>ids - A table of panel ID's to disable</li>
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
                <td><code>plugins.finalcutpro.export.batch.manager.focus() -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Puts focus on the Batch Export Window.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successful or otherwise <code>false</code>.</li>
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
                <td><code>plugins.finalcutpro.export.batch.manager.getHandler(id) -&gt; string</code></td>
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
                <td><code>plugins.finalcutpro.export.batch.manager.getLabel() -&gt; string</code></td>
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
          <section id="getWebview">
            <a name="//apple_ref/cpp/Function/getWebview" class="dashAnchor"></a>
            <h5><a href="#getWebview">getWebview</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.export.batch.manager.getWebview() -&gt; hs.webview</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the Webview of the Preferences Window.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A <code>hs.webview</code></li>
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
                <td><code>plugins.finalcutpro.export.batch.manager.hide() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Hides the Batch Export Window.</p>
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
          <section id="init">
            <a name="//apple_ref/cpp/Function/init" class="dashAnchor"></a>
            <h5><a href="#init">init</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.export.batch.manager.init() -&gt; nothing</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Initialises the preferences panel.</p>
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
                <td><code>plugins.finalcutpro.export.batch.manager.injectScript(script) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Injects JavaScript into the Batch Export Webview.</p>
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
                <td><code>plugins.finalcutpro.export.batch.manager.maxPanelHeight() -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the maximum size defined by a panel.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The maximum panel height.</li>
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
                <td><code>plugins.finalcutpro.export.batch.manager.new() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new Preferences Window.</p>
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
          <section id="refresh">
            <a name="//apple_ref/cpp/Function/refresh" class="dashAnchor"></a>
            <h5><a href="#refresh">refresh</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.export.batch.manager.refresh() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Refreshes the Batch Export Window.</p>
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
          <section id="selectPanel">
            <a name="//apple_ref/cpp/Function/selectPanel" class="dashAnchor"></a>
            <h5><a href="#selectPanel">selectPanel</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.export.batch.manager.selectPanel(id) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Selects a Batch Export Panel.</p>
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
                <td><code>plugins.finalcutpro.export.batch.manager.setPanelRenderer(renderer) -&gt; none</code></td>
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
                <td><code>plugins.finalcutpro.export.batch.manager.show() -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Shows the Preferences Window</p>
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
