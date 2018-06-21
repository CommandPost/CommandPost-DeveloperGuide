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
      <h1><a href="cp.apple.finalcutpro.export.ExportDialog.md">docs</a> &raquo; cp.apple.finalcutpro.export.ExportDialog</h1>
      <p>Export Dialog Module.</p>

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
            <li><a href="#isShowing">isShowing</a></li>
            <li><a href="#title">title</a></li>
            <li><a href="#UI">UI</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#app">app</a></li>
            <li><a href="#getTitle">getTitle</a></li>
            <li><a href="#hide">hide</a></li>
            <li><a href="#pressCancel">pressCancel</a></li>
            <li><a href="#pressNext">pressNext</a></li>
            <li><a href="#saveSheet">saveSheet</a></li>
            <li><a href="#show">show</a></li>
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
                <td><code>cp.apple.finalcutpro.export.ExportDialog.matches(element) -&gt; boolean</code></td>
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
                <td><code>cp.apple.finalcutpro.export.ExportDialog.new(app) -&gt; ExportDialog</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new Export Dialog object.</p>
<p>Parameters:</p>
<ul>
<li>app - The <code>cp.apple.finalcutpro</code> object.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A new ExportDialog object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Fields</h4>
          <section id="isShowing">
            <a name="//apple_ref/cpp/Field/isShowing" class="dashAnchor"></a>
            <h5><a href="#isShowing">isShowing</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.export.ExportDialog.isShowing &lt;cp.prop: boolean; read-only; live&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Is the window showing?</p>
</td>
              </tr>
            </table>
          </section>
          <section id="title">
            <a name="//apple_ref/cpp/Field/title" class="dashAnchor"></a>
            <h5><a href="#title">title</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.export.ExportDialog.title &lt;cp.prop: string; read-only; live&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The window title, or <code>nil</code> if not available.</p>
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
                <td><code>cp.apple.finalcutpro.export.ExportDialog.UI &lt;cp.prop: hs._asm.axuielement: read-only; live&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the Export Dialog <code>axuielement</code>.</p>
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
                <td><code>cp.apple.finalcutpro.export.ExportDialog:app() -&gt; App</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the app instance representing Final Cut Pro.</p>
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
                <td><code>cp.apple.finalcutpro.export.ExportDialog:getTitle() -&gt; string | nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The title of the Go To Prompt window or <code>nil</code>.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The title of the Go To Prompt window as a string or <code>nil</code>.</li>
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
                <td><code>cp.apple.finalcutpro.export.ExportDialog:hide() -&gt; cp.apple.finalcutpro.export.ExportDialog</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Hides the Export Dialog</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.apple.finalcutpro.export.ExportDialog</code> object for method chaining.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="pressCancel">
            <a name="//apple_ref/cpp/Method/pressCancel" class="dashAnchor"></a>
            <h5><a href="#pressCancel">pressCancel</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.export.ExportDialog:pressCancel() -&gt; cp.apple.finalcutpro.export.ExportDialog</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Presses the Cancel Button.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.apple.finalcutpro.export.ExportDialog</code> object for method chaining.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="pressNext">
            <a name="//apple_ref/cpp/Method/pressNext" class="dashAnchor"></a>
            <h5><a href="#pressNext">pressNext</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.export.ExportDialog:pressNext() -&gt; cp.apple.finalcutpro.export.ExportDialog</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Presses the Next Button.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.apple.finalcutpro.export.ExportDialog</code> object for method chaining.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="saveSheet">
            <a name="//apple_ref/cpp/Method/saveSheet" class="dashAnchor"></a>
            <h5><a href="#saveSheet">saveSheet</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.export.ExportDialog:saveSheet() -&gt; SaveSheet</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new Save Sheet.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The SaveSheet.</li>
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
                <td><code>cp.apple.finalcutpro.export.ExportDialog:show(destinationSelect, ignoreProxyWarning, ignoreMissingMedia, quiet) -&gt; cp.apple.finalcutpro.export.ExportDialog, string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Shows the Export Dialog with the Destination that matches the <code>destinationSelect</code>.</p>
<p>Parameters:</p>
<ul>
<li>destinationSelect    - The name, number or match function of the destination to export with.</li>
<li>ignoreProxyWarning   - if <code>true</code>, the warning regarding exporting Proxies will be ignored.</li>
<li>ignoreMissingMedia   - if <code>true</code>, the warning regarding exporting with missing media will be ignored.</li>
<li>quiet                - if <code>true</code>, no dialogs will be shown if there is an error.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.apple.finalcutpro.export.ExportDialog</code> object for method chaining.</li>
<li>If an error occurred, the message is returned as the second value</li>
</ul>
<p>Notes:</p>
<ul>
<li>If providing a function, it will be passed one item - the name of the destination, and should return <code>true</code> to indicate a match. The name will not contain " (default)" if present.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
