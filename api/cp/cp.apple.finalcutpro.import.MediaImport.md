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
      <h1><a href="cp.apple.finalcutpro.import.MediaImport.md">docs</a> &raquo; cp.apple.finalcutpro.import.MediaImport</h1>
      <p>Media Import</p>

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
            <li><a href="#frame">frame</a></li>
            <li><a href="#hsWindow">hsWindow</a></li>
            <li><a href="#isFullScreen">isFullScreen</a></li>
            <li><a href="#isShowing">isShowing</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#app">app</a></li>
            <li><a href="#getTitle">getTitle</a></li>
            <li><a href="#hide">hide</a></li>
            <li><a href="#show">show</a></li>
            <li><a href="#UI">UI</a></li>
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
                <td><code>cp.apple.finalcutpro.import.MediaImport.matches(element) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks to see if an element matches what we think it should be.</p>
<p>Parameters:</p>
<ul>
<li>element - An <code>axuielementObject</code> to check.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if matches otherwise <code>false</code></li>
</ul>
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
                <td><code>cp.apple.finalcutpro.import.MediaImport.new(app) -&gt; MediaImport</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new Media Import object.</p>
<p>Parameters:</p>
<ul>
<li>app - The <code>cp.apple.finalcutpro</code> object.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A new MediaImport object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Fields</h4>
          <section id="frame">
            <a name="//apple_ref/cpp/Field/frame" class="dashAnchor"></a>
            <h5><a href="#frame">frame</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.import.MediaImport.frame &lt;cp.prop: frame&gt;</code></td>
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
                <td><code>cp.apple.finalcutpro.import.MediaImport.hsWindow &lt;cp.prop: hs.window; read-only&gt;</code></td>
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
                <td><code>cp.apple.finalcutpro.import.MediaImport.isFullScreen &lt;cp.prop: boolean&gt;</code></td>
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
                <td><code>cp.apple.finalcutpro.import.MediaImport.isShowing &lt;cp.prop: boolean&gt;</code></td>
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
        <h4 class="documentation-section">Methods</h4>
          <section id="app">
            <a name="//apple_ref/cpp/Method/app" class="dashAnchor"></a>
            <h5><a href="#app">app</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.import.MediaImport:app() -&gt; App</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the App instance representing Final Cut Pro.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>App</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="getTitle">
            <a name="//apple_ref/cpp/Method/getTitle" class="dashAnchor"></a>
            <h5><a href="#getTitle">getTitle</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.import.MediaImport:getTitle() -&gt; string | nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The title of the Media Import window or <code>nil</code>.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The title of the Media Import window as a string or <code>nil</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="hide">
            <a name="//apple_ref/cpp/Method/hide" class="dashAnchor"></a>
            <h5><a href="#hide">hide</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.import.MediaImport:hide() -&gt; cp.apple.finalcutpro.import.MediaImport</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Hides the Media Import window.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.apple.finalcutpro.import.MediaImport</code> object for method chaining.</li>
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
                <td><code>cp.apple.finalcutpro.import.MediaImport:show() -&gt; cp.apple.finalcutpro.import.MediaImport</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Triggers the Import All button.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.apple.finalcutpro.import.MediaImport</code> object for method chaining.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="UI">
            <a name="//apple_ref/cpp/Method/UI" class="dashAnchor"></a>
            <h5><a href="#UI">UI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.import.MediaImport:UI() -&gt; axuielementObject</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the Media Import Accessibility Object</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>An <code>axuielementObject</code> or <code>nil</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
