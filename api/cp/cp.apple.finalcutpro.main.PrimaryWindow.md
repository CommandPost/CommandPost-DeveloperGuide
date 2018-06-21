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
      <h1><a href="cp.apple.finalcutpro.main.PrimaryWindow.md">docs</a> &raquo; cp.apple.finalcutpro.main.PrimaryWindow</h1>
      <p>Primary Window Module.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#matches">matches</a></li>
          </ul>
        <li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
          <ul>
            <li><a href="#bottomGroupUI">bottomGroupUI</a></li>
            <li><a href="#browserGroupUI">browserGroupUI</a></li>
            <li><a href="#frame">frame</a></li>
            <li><a href="#hsWindow">hsWindow</a></li>
            <li><a href="#isFullScreen">isFullScreen</a></li>
            <li><a href="#isShowing">isShowing</a></li>
            <li><a href="#leftGroupUI">leftGroupUI</a></li>
            <li><a href="#rightGroupUI">rightGroupUI</a></li>
            <li><a href="#rootGroupUI">rootGroupUI</a></li>
            <li><a href="#timelineGroupUI">timelineGroupUI</a></li>
            <li><a href="#topGroupUI">topGroupUI</a></li>
            <li><a href="#UI">UI</a></li>
            <li><a href="#viewerGroupUI">viewerGroupUI</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#alert">alert</a></li>
            <li><a href="#app">app</a></li>
            <li><a href="#colorBoard">colorBoard</a></li>
            <li><a href="#inspector">inspector</a></li>
            <li><a href="#new">new</a></li>
            <li><a href="#show">show</a></li>
            <li><a href="#toolbar">toolbar</a></li>
            <li><a href="#window">window</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Functions</h4>
          <section id="matches">
            <a name="//apple_ref/cpp/Function/matches" class="dashAnchor"></a>
            <h5><a href="#matches">matches</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.PrimaryWindow.matches(w) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks to see if a window matches the PrimaryWindow requirements</p>
<p>Parameters:</p>
<ul>
<li>w - The window to check</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if matched otherwise <code>false</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Fields</h4>
          <section id="bottomGroupUI">
            <a name="//apple_ref/cpp/Field/bottomGroupUI" class="dashAnchor"></a>
            <h5><a href="#bottomGroupUI">bottomGroupUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.PrimaryWindow:bottomGroupUI &lt;cp.prop: hs._asm.axuielement; read-only; live&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the bottom group UI as a <code>hs._asm.axuielement</code> object.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="browserGroupUI">
            <a name="//apple_ref/cpp/Field/browserGroupUI" class="dashAnchor"></a>
            <h5><a href="#browserGroupUI">browserGroupUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.PrimaryWindow.browserGroupUI &lt;cp.prop: hs._asm.axuielement; read-only; live&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the UI which contains the Browser.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="frame">
            <a name="//apple_ref/cpp/Field/frame" class="dashAnchor"></a>
            <h5><a href="#frame">frame</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.PrimaryWindow.frame &lt;cp.prop: frame&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The current position (x, y, width, height) of the window.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="hsWindow">
            <a name="//apple_ref/cpp/Field/hsWindow" class="dashAnchor"></a>
            <h5><a href="#hsWindow">hsWindow</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.PrimaryWindow.hsWindow &lt;cp.prop: hs.window; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The <code>hs.window</code> instance for the window, or <code>nil</code> if it can't be found.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="isFullScreen">
            <a name="//apple_ref/cpp/Field/isFullScreen" class="dashAnchor"></a>
            <h5><a href="#isFullScreen">isFullScreen</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.PrimaryWindow.isFullScreen &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Is <code>true</code> if the window is full-screen.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="isShowing">
            <a name="//apple_ref/cpp/Field/isShowing" class="dashAnchor"></a>
            <h5><a href="#isShowing">isShowing</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.PrimaryWindow.isShowing &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Is <code>true</code> if the window is visible.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="leftGroupUI">
            <a name="//apple_ref/cpp/Field/leftGroupUI" class="dashAnchor"></a>
            <h5><a href="#leftGroupUI">leftGroupUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.PrimaryWindow.leftGroupUI &lt;cp.prop: hs._asm.axuielement; read-only; live&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the left group UI as a <code>hs._asm.axuielement</code> object</p>
</td>
              </tr>
            </table>
          </section>
          <section id="rightGroupUI">
            <a name="//apple_ref/cpp/Field/rightGroupUI" class="dashAnchor"></a>
            <h5><a href="#rightGroupUI">rightGroupUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.PrimaryWindow.rightGroupUI &lt;cp.prop: hs._asm.axuielement; read-only; live&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the right group UI as a <code>hs._asm.axuielement</code> object.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="rootGroupUI">
            <a name="//apple_ref/cpp/Field/rootGroupUI" class="dashAnchor"></a>
            <h5><a href="#rootGroupUI">rootGroupUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.PrimaryWindow.rootGroupUI() &lt;cp.prop: hs._asm.axuielement; read-only; live&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the top AXSplitGroup as a <code>hs._asm.axuielement</code> object</p>
</td>
              </tr>
            </table>
          </section>
          <section id="timelineGroupUI">
            <a name="//apple_ref/cpp/Field/timelineGroupUI" class="dashAnchor"></a>
            <h5><a href="#timelineGroupUI">timelineGroupUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.PrimaryWindow.timelineGroupUI &lt;cp.prop: hs._asm.axuielement; read-only; live&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the UI that contains the <code>Timeline</code>.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="topGroupUI">
            <a name="//apple_ref/cpp/Field/topGroupUI" class="dashAnchor"></a>
            <h5><a href="#topGroupUI">topGroupUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.PrimaryWindow.topGroupUI &lt;cp.prop: hs._asm.axuielement; read-only; live&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the top group UI as a <code>hs._asm.axuielement</code> object.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="UI">
            <a name="//apple_ref/cpp/Field/UI" class="dashAnchor"></a>
            <h5><a href="#UI">UI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.PrimaryWindow.UI &lt;cp.prop: axuielement; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The <code>axuielement</code> for the window.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="viewerGroupUI">
            <a name="//apple_ref/cpp/Field/viewerGroupUI" class="dashAnchor"></a>
            <h5><a href="#viewerGroupUI">viewerGroupUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.PrimaryWindow.viewerGroupUI &lt;cp.prop: hs._asm.axuielement; read-only; live&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the UI that contains the <code>Viewer</code>.</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Methods</h4>
          <section id="alert">
            <a name="//apple_ref/cpp/Method/alert" class="dashAnchor"></a>
            <h5><a href="#alert">alert</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.PrimaryWindow:alert() -&gt; cp.ui.Alert</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Provides access to any 'Alert' windows on the PrimaryWindow.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A <code>cp.ui.Alert</code> object</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="app">
            <a name="//apple_ref/cpp/Method/app" class="dashAnchor"></a>
            <h5><a href="#app">app</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.PrimaryWindow:app() -&gt; hs.application</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the application the display belongs to.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The app instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="colorBoard">
            <a name="//apple_ref/cpp/Method/colorBoard" class="dashAnchor"></a>
            <h5><a href="#colorBoard">colorBoard</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.PrimaryWindow:colorBoard() -&gt; ColorBoard</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the ColorBoard object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>ColorBoard</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="inspector">
            <a name="//apple_ref/cpp/Method/inspector" class="dashAnchor"></a>
            <h5><a href="#inspector">inspector</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.PrimaryWindow:inspector() -&gt; Inspector</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the Inspector object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>Inspector</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="new">
            <a name="//apple_ref/cpp/Method/new" class="dashAnchor"></a>
            <h5><a href="#new">new</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.PrimaryWindow.new(app) -&gt; PrimaryWindow object</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new PrimaryWindow.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>PrimaryWindow</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="show">
            <a name="//apple_ref/cpp/Method/show" class="dashAnchor"></a>
            <h5><a href="#show">show</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.PrimaryWindow:show() -&gt; PrimaryWindow</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Shows the Primary Window.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>PrimaryWindow</code> instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="toolbar">
            <a name="//apple_ref/cpp/Method/toolbar" class="dashAnchor"></a>
            <h5><a href="#toolbar">toolbar</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.PrimaryWindow:toolbar() -&gt; PrimaryToolbar</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the PrimaryToolbar element.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>PrimaryToolbar</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="window">
            <a name="//apple_ref/cpp/Method/window" class="dashAnchor"></a>
            <h5><a href="#window">window</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.PrimaryWindow:window() -&gt; cp.ui.Window</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the <code>Window</code> instance.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>Window</code> instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
