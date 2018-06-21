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
      <h1><a href="cp.apple.finalcutpro.main.Playhead.md">docs</a> &raquo; cp.apple.finalcutpro.main.Playhead</h1>
      <p>Playhead Module.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#find">find</a></li>
            <li><a href="#matches">matches</a></li>
          </ul>
        <li>Constructors - API calls which return an object, typically one that offers API methods</li>
          <ul>
            <li><a href="#new">new</a></li>
          </ul>
        <li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
          <ul>
            <li><a href="#center">center</a></li>
            <li><a href="#currentViewer">currentViewer</a></li>
            <li><a href="#frame">frame</a></li>
            <li><a href="#isPersistent">isPersistent</a></li>
            <li><a href="#isShowing">isShowing</a></li>
            <li><a href="#position">position</a></li>
            <li><a href="#timecode">timecode</a></li>
            <li><a href="#UI">UI</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#app">app</a></li>
            <li><a href="#hide">hide</a></li>
            <li><a href="#parent">parent</a></li>
            <li><a href="#show">show</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Functions</h4>
          <section id="find">
            <a name="//apple_ref/cpp/Function/find" class="dashAnchor"></a>
            <h5><a href="#find">find</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.Playhead.find(containerUI, skimming) -&gt; hs._asm.axuielement object | nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Finds the playhead (either persistent or skimming) in the specified container. Defaults to persistent.</p>
<p>Parameters:</p>
<ul>
<li><code>containerUI</code> - The container UI</li>
<li><code>skimming</code> - Whether or not you want the skimming playhead as boolean.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The playhead <code>hs._asm.axuielement</code> object or <code>nil</code> if not found.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="matches">
            <a name="//apple_ref/cpp/Function/matches" class="dashAnchor"></a>
            <h5><a href="#matches">matches</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.Playhead.matches(element) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks to see if a GUI element is the Playhead or not</p>
<p>Parameters:</p>
<ul>
<li><code>element</code>    - The element you want to check</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the <code>element</code> is the Playhead otherwise <code>false</code></li>
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
                <td><code>cp.apple.finalcutpro.main.Playhead.new(parent[, skimming[, containerFn[, useEventViewer]]]) -&gt; Playhead</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Constructs a new Playhead</p>
<p>Parameters:</p>
<ul>
<li>parent        - The parent object</li>
<li>skimming      - (optional) if <code>true</code>, this links to the 'skimming' playhead created under the mouse, if present.</li>
<li>containerUI   - (optional) a <code>cp.prop</code> which returns the container axuielement which contains the playheads. If not present, it will use the parent's UI element.</li>
<li>useEventViewer - (optional) if <code>true</code>, this will use the Event Viewer's timecode, when available.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The new <code>Playhead</code> instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Fields</h4>
          <section id="center">
            <a name="//apple_ref/cpp/Field/center" class="dashAnchor"></a>
            <h5><a href="#center">center</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.Playhead.center &lt;cp.prop: hs.geometry.point; read-only; live?&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the centre point (<code>{x, y}</code>) of the playhead.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="currentViewer">
            <a name="//apple_ref/cpp/Field/currentViewer" class="dashAnchor"></a>
            <h5><a href="#currentViewer">currentViewer</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.Playhead.currentViewer &lt;cp.prop: cp.apple.finalcutpro.main.Viewer; read-only; live&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Represents the current viewer for the playhead. This may be either the primary Viewer or the Event Viewer,
depending on the Playhead instance and whether the Event Viewer is enabled.</p>
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
                <td><code>cp.apple.finalcutpro.main.Playhead.frame &lt;cp.prop: hs.geometry.frame; read-only; live?&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the frame of the playhead.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="isPersistent">
            <a name="//apple_ref/cpp/Field/isPersistent" class="dashAnchor"></a>
            <h5><a href="#isPersistent">isPersistent</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.Playhead.isPersistent &lt;cp.prop: boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Is the playhead persistent?</p>
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
                <td><code>cp.apple.finalcutpro.main.Playhead.isShowing &lt;cp.prop: boolean; read-only; live?&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Is the playhead showing?</p>
</td>
              </tr>
            </table>
          </section>
          <section id="position">
            <a name="//apple_ref/cpp/Field/position" class="dashAnchor"></a>
            <h5><a href="#position">position</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.Playhead.position &lt;cp.prop; number; read-only; live?&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the horizontal position of the playhead line, which may be different to the <code>x</code> position of the playhead.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="timecode">
            <a name="//apple_ref/cpp/Field/timecode" class="dashAnchor"></a>
            <h5><a href="#timecode">timecode</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.Playhead.timecode &lt;cp.prop: string; live?&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets and sets the current timecode.</p>
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
                <td><code>cp.apple.finalcutpro.main.Playhead.UI &lt;cp.prop: hs._asm.axuielement; read-only; live?&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the <code>hs._asm.axuielement</code> object for the Playhead</p>
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
                <td><code>cp.apple.finalcutpro.main.Playhead:app() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the <code>cp.apple.finalcutpro</code> app table</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The application object as a table</li>
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
                <td><code>cp.apple.finalcutpro.main.Playhead:hide() -&gt; Playhead object</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Hides the Playhead</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>Playhead object</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="parent">
            <a name="//apple_ref/cpp/Method/parent" class="dashAnchor"></a>
            <h5><a href="#parent">parent</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.Playhead:parent() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the Playhead's parent table</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The parent object as a table</li>
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
                <td><code>cp.apple.finalcutpro.main.Playhead:show() -&gt; Playhead object</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Shows the Playhead</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>Playhead object</li>
</ul>
</td>
              </tr>
            </table>
          </section>
