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
      <h1><a href="cp.ui.PropertyRow.md">docs</a> &raquo; cp.ui.PropertyRow</h1>
      <p>Represents a single property row, typically in a Property Inspector.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#isParent">isParent</a></li>
            <li><a href="#matches">matches</a></li>
            <li><a href="#parentUIFinder">parentUIFinder</a></li>
            <li><a href="#prepareParent">prepareParent</a></li>
          </ul>
        <li>Constructors - API calls which return an object, typically one that offers API methods</li>
          <ul>
            <li><a href="#new">new</a></li>
          </ul>
        <li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
          <ul>
            <li><a href="#isShowing">isShowing</a></li>
            <li><a href="#label">label</a></li>
            <li><a href="#labelUI">labelUI</a></li>
            <li><a href="#propertiesUI">propertiesUI</a></li>
            <li><a href="#reset">reset</a></li>
            <li><a href="#UI">UI</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#app">app</a></li>
            <li><a href="#children">children</a></li>
            <li><a href="#hide">hide</a></li>
            <li><a href="#labelKeys">labelKeys</a></li>
            <li><a href="#parent">parent</a></li>
            <li><a href="#show">show</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Functions</h4>
          <section id="isParent">
            <a name="//apple_ref/cpp/Function/isParent" class="dashAnchor"></a>
            <h5><a href="#isParent">isParent</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.PropertyRow.isParent(parent) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks if the <code>parent</code> has been prepared via <a href="#prepareParent">prepareParent</a>.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the parent is prepared.</li>
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
                <td><code>cp.ui.PropertyRow.matches(element) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks if the provided <code>axuielement</code> could be a property row.
Note: this does not guarantee that it <em>is</em> a property row element, just that it could be.</p>
<p>Parameters:</p>
<ul>
<li>element   - The element to check.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the element could be a property row.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="parentUIFinder">
            <a name="//apple_ref/cpp/Function/parentUIFinder" class="dashAnchor"></a>
            <h5><a href="#parentUIFinder">parentUIFinder</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.PropertyRow.parentUIFinder(parent) -&gt; cp.prop</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the <code>cp.prop</code> which finds the <code>hs._asm.axuielement</code> that contains property rows from the parent.
This needs to be configured first by calling the <code>prepareParent</code> function with the <code>parent</code> and finder function.</p>
<p>Parameters:</p>
<ul>
<li>parent        - The parent which has a finder assigned.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.prop</code> which provides access to the finder, or <code>nil</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="prepareParent">
            <a name="//apple_ref/cpp/Function/prepareParent" class="dashAnchor"></a>
            <h5><a href="#prepareParent">prepareParent</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.PropertyRow.prepareParent(parent, uiFinder) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Call this to make <code>parent</code> table ready to be a parent of <code>PropertyRow</code>s.
Essentially, this lets <code>PropertyRow</code> instances ask the parent for the
<code>hs._asm.axuielement</code> that contains the property row details.</p>
<p>Parameters:</p>
<ul>
<li>parent    - The parent table.</li>
<li>uiFinder  - The function or cp.prop which will be called to find the parent UI element. Functions will be passed the <code>parent</code> when being executed.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
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
                <td><code>cp.ui.PropertyRow.new(parent, labelKey[, index]) -&gt; cp.ui.PropertyRow</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new <code>PropertyRow</code> with the specified parent and label key.</p>
<p>If you have more than one row with the same label, specify the <code>index</code> - specifying <code>2</code> will
match with the second instance, for example.</p>
<p>Parameters:</p>
<ul>
<li>parent        - The parent object.</li>
<li>labelKey      - The key of the label that the row will map to.</li>
<li>index         - The row number with the same label to get. Defaults to <code>1</code>.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The new <code>PropertyRow</code> instance.</li>
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
                <td><code>cp.ui.PropertyRow.isShowing &lt;cp.prop: boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks if the row is showing.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="label">
            <a name="//apple_ref/cpp/Field/label" class="dashAnchor"></a>
            <h5><a href="#label">label</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.PropertyRow.label &lt;cp.prop: string; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The label of the property row, in the current langauge.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="labelUI">
            <a name="//apple_ref/cpp/Field/labelUI" class="dashAnchor"></a>
            <h5><a href="#labelUI">labelUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.PropertyRow.labelUI &lt;cp.prop: hs._asm.axuielement; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The <code>axuielement</code> containing the row label.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="propertiesUI">
            <a name="//apple_ref/cpp/Field/propertiesUI" class="dashAnchor"></a>
            <h5><a href="#propertiesUI">propertiesUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.PropertyRow.propertiesUI &lt;cp.prop: hs._asm.axuielement; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The <code>axuielement</code> from the parent that contains the properties.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="reset">
            <a name="//apple_ref/cpp/Field/reset" class="dashAnchor"></a>
            <h5><a href="#reset">reset</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.PropertyRow.reset &lt;cp.ui.Button&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The <code>reset</code> button for the row, which may or may not actually exist.
It can be triggered by calling <code>row:reset()</code>.</p>
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
                <td><code>cp.ui.PropertyRow.UI &lt;cp.prop: hs._asm.axuielement; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the <code>axuielement</code> for the row.</p>
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
                <td><code>cp.ui.PropertyRow:app() -&gt; App</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the app instance.</p>
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
          <section id="children">
            <a name="//apple_ref/cpp/Method/children" class="dashAnchor"></a>
            <h5><a href="#children">children</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.PropertyRow:children() -&gt; table | nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets a table of children for the Property Row.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table of children or <code>nil</code>.</li>
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
                <td><code>cp.ui.PropertyRow:hide() -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Hides the <code>PropertyRow</code>.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>self</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="labelKeys">
            <a name="//apple_ref/cpp/Method/labelKeys" class="dashAnchor"></a>
            <h5><a href="#labelKeys">labelKeys</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.PropertyRow:labelKeys() -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the key of the label that the row will map to.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>string</li>
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
                <td><code>cp.ui.PropertyRow:parent() -&gt; parent</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the parent object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>parent</li>
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
                <td><code>cp.ui.PropertyRow:show() -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Shows the <code>PropertyRow</code>.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>self</li>
</ul>
</td>
              </tr>
            </table>
          </section>
