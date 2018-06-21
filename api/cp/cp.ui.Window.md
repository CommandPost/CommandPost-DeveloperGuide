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
      <h1><a href="cp.ui.Window.md">docs</a> &raquo; cp.ui.Window</h1>
      <p>A Window UI element.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#matches">matches</a></li>
          </ul>
        <li>Constructors - API calls which return an object, typically one that offers API methods</li>
          <ul>
            <li><a href="#new">new</a></li>
          </ul>
        <li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
          <ul>
            <li><a href="#exists">exists</a></li>
            <li><a href="#focused">focused</a></li>
            <li><a href="#frame">frame</a></li>
            <li><a href="#fullScreen">fullScreen</a></li>
            <li><a href="#hsWindow">hsWindow</a></li>
            <li><a href="#id">id</a></li>
            <li><a href="#minimized">minimized</a></li>
            <li><a href="#visible">visible</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#close">close</a></li>
            <li><a href="#focus">focus</a></li>
            <li><a href="#snapshot">snapshot</a></li>
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
                <td><code>cp.ui.Window.matches(element) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks if the provided element is a valid window.</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Constructors</h4>
          <section id="new">
            <a name="//apple_ref/cpp/Constructor/new" class="dashAnchor"></a>
            <h5><a href="#new">new</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Window.new(uiProp) -&gt; Window</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new Window</p>
<p>Parameters:</p>
<ul>
<li><code>uiProp</code>   - a <code>cp.prop</code> that returns the <code>hs._asm.axuielement</code> for the window.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A new <code>Window</code> instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Fields</h4>
          <section id="exists">
            <a name="//apple_ref/cpp/Field/exists" class="dashAnchor"></a>
            <h5><a href="#exists">exists</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Window.exists &lt;cp.prop: boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns <code>true</code> if the window exists. It may not be visible.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="focused">
            <a name="//apple_ref/cpp/Field/focused" class="dashAnchor"></a>
            <h5><a href="#focused">focused</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Window.focused &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Is <code>true</code> if the window has mouse/keyboard focused.
Note: Setting to <code>false</code> has no effect, since 'defocusing' isn't definable.</p>
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
                <td><code>cp.ui.Window.frame &lt;cp.prop: hs.geometry rect&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The <code>hs.geometry</code> rect value describing the window's position.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="fullScreen">
            <a name="//apple_ref/cpp/Field/fullScreen" class="dashAnchor"></a>
            <h5><a href="#fullScreen">fullScreen</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Window.fullScreen &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns <code>true</code> if the window is full-screen.</p>
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
                <td><code>cp.ui.Window.hsWindow &lt;cp.prop: hs.window; read-only&gt;</code></td>
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
          <section id="id">
            <a name="//apple_ref/cpp/Field/id" class="dashAnchor"></a>
            <h5><a href="#id">id</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Window.id &lt;cp.prop: number; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The unique ID for the window.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="minimized">
            <a name="//apple_ref/cpp/Field/minimized" class="dashAnchor"></a>
            <h5><a href="#minimized">minimized</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Window.minimized &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns <code>true</code> if the window exists and is minimised.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="visible">
            <a name="//apple_ref/cpp/Field/visible" class="dashAnchor"></a>
            <h5><a href="#visible">visible</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Window.visible &lt;cp.prop: boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns <code>true</code> if the window is visible on a screen.</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Methods</h4>
          <section id="close">
            <a name="//apple_ref/cpp/Method/close" class="dashAnchor"></a>
            <h5><a href="#close">close</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Window.close() -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Attempts to close the window.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the window was successfully closed.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="focus">
            <a name="//apple_ref/cpp/Method/focus" class="dashAnchor"></a>
            <h5><a href="#focus">focus</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Window.focus() -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Attempts to focus the window.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the window was successfully focused.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="snapshot">
            <a name="//apple_ref/cpp/Method/snapshot" class="dashAnchor"></a>
            <h5><a href="#snapshot">snapshot</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Window:snapshot([path]) -&gt; hs.image | nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Takes a snapshot of the UI in its current state as a PNG and returns it.
If the <code>path</code> is provided, the image will be saved at the specified location.</p>
<p>Parameters:</p>
<ul>
<li>path      - (optional) The path to save the file. Should include the extension (should be <code>.png</code>).</li>
</ul>
<p>Return:</p>
<ul>
<li>The <code>hs.image</code> that was created, or <code>nil</code> if the UI is not available.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
