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
      <h1><a href="plugins.core.setup.panel.md">docs</a> &raquo; plugins.core.setup.panel</h1>
      <p>CommandPost Setup Window Panel.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Constants - Useful values which cannot be changed</li>
          <ul>
            <li><a href="#WEBVIEW_LABEL">WEBVIEW_LABEL</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#panelCount">panelCount</a></li>
            <li><a href="#panelNumber">panelNumber</a></li>
            <li><a href="#panelQueue">panelQueue</a></li>
          </ul>
        <li>Constructors - API calls which return an object, typically one that offers API methods</li>
          <ul>
            <li><a href="#new">new</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#addButton">addButton</a></li>
            <li><a href="#addCheckbox">addCheckbox</a></li>
            <li><a href="#addContent">addContent</a></li>
            <li><a href="#addFooter">addFooter</a></li>
            <li><a href="#addHandler">addHandler</a></li>
            <li><a href="#addHeading">addHeading</a></li>
            <li><a href="#addIcon">addIcon</a></li>
            <li><a href="#addParagraph">addParagraph</a></li>
            <li><a href="#addPassword">addPassword</a></li>
            <li><a href="#addSelect">addSelect</a></li>
            <li><a href="#addSubHeading">addSubHeading</a></li>
            <li><a href="#addTextbox">addTextbox</a></li>
            <li><a href="#getHandler">getHandler</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Constants</h4>
          <section id="WEBVIEW_LABEL">
            <a name="//apple_ref/cpp/Constant/WEBVIEW_LABEL" class="dashAnchor"></a>
            <h5><a href="#WEBVIEW_LABEL">WEBVIEW_LABEL</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.setup.panel.WEBVIEW_LABEL -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The ID for the Webview</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Functions</h4>
          <section id="panelCount">
            <a name="//apple_ref/cpp/Function/panelCount" class="dashAnchor"></a>
            <h5><a href="#panelCount">panelCount</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.setup.panelCount() -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The number of panels currently being processed in this session.
This includes panels already processed, the current panel, and remaining panels.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The number of panels.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="panelNumber">
            <a name="//apple_ref/cpp/Function/panelNumber" class="dashAnchor"></a>
            <h5><a href="#panelNumber">panelNumber</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.setup.panelNumber() -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The number of the panel currently being viewed.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>the current panel number, or <code>0</code> if no panels are registered.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="panelQueue">
            <a name="//apple_ref/cpp/Function/panelQueue" class="dashAnchor"></a>
            <h5><a href="#panelQueue">panelQueue</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.setup.panelQueue() -&gt; table of panels</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The table of panels remaining to be processed. Panels are removed from the queue
one at a time and idisplayed in the window via the <code>nextPanel()</code> function.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The table of panels remaining to be processed.</li>
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
                <td><code>plugins.core.setup.panel.new(id, priority) -&gt; plugins.core.setup.panel</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Constructs a new panel with the specified priority and ID.</p>
<p>Parameters:</p>
<ul>
<li>priority - Defines the order in which the panel appears.</li>
<li>id       - The unique ID for the panel.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Methods</h4>
          <section id="addButton">
            <a name="//apple_ref/cpp/Method/addButton" class="dashAnchor"></a>
            <h5><a href="#addButton">addButton</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.setup.panel:addButton(params) -&gt; panel</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Adds a button to the panel.</p>
<p>Parameters:</p>
<ul>
<li>params - The list of parameters.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The same panel.</li>
</ul>
<p>Notes:</p>
<ul>
<li>The <code>params</code> table may contain:
<strong> <code>id</code>        - (optional) the unique ID for the button. If none is provided, one is generated.</strong> <code>value</code>     - The value of the button. This is sent to the <code>onclick</code> function.
<strong> <code>label</code>     - The text label for the button. Defaults to the <code>value</code> if not provided.</strong> <code>width</code>     - The width of the button in pixels.
** <code>onclick</code>   - the function to execute when the button is clicked. The function should have the signature of <code>function(id, value)</code>, where <code>id</code> is the id of the button that was clicked, and <code>value</code> is the value of the button.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="addCheckbox">
            <a name="//apple_ref/cpp/Method/addCheckbox" class="dashAnchor"></a>
            <h5><a href="#addCheckbox">addCheckbox</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.setup.panel:addCheckbox(params) -&gt; panel</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Adds a checkbox to the panel with the specified <code>priority</code> and <code>params</code>.</p>
<p>Parameters:</p>
<ul>
<li><code>priority</code>   - The priority number for the checkbox.</li>
<li><code>params</code>     - The set of parameters for the checkbox.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The panel object.</li>
</ul>
<p>Notes:</p>
<ul>
<li>The <code>params</code> can contain the following fields:
<strong> <code>id</code>        - (optional) The unique ID. If none is provided, one will be generated.</strong> <code>name</code>      - (optional) The name of the checkbox field.
<strong> <code>label</code>     - (optional) The text label to display after the checkbox.</strong> <code>onchange</code>  - (optional) a function that will get called when the checkbox value changes. It will be passed two parameters, <code>id</code> and <code>params</code>, the latter of which is a table containing the <code>value</code> and <code>checked</code> values of the checkbox.
** <code>class</code>     - (optional) the CSS class list to apply to the checkbox.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="addContent">
            <a name="//apple_ref/cpp/Method/addContent" class="dashAnchor"></a>
            <h5><a href="#addContent">addContent</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.setup.panel:addContent(content[, escaped]) -&gt; panel</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Adds the specified <code>content</code> to the panel.</p>
<p>Parameters:</p>
<ul>
<li><code>content</code> - a value that can be converted to a string.</li>
<li><code>escaped</code> - if <code>true</code>, the content will not be escaped. Defaults to true.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The panel.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="addFooter">
            <a name="//apple_ref/cpp/Method/addFooter" class="dashAnchor"></a>
            <h5><a href="#addFooter">addFooter</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.setup.panel:addFooter(content, unescaped) -&gt; panel</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Adds the specified <code>content</code> to the panel's footer.</p>
<p>Parameters:</p>
<ul>
<li><code>content</code> - a value that can be converted to a string.</li>
<li><code>unescaped</code> - if <code>true</code>, the content will not be escaped. Defaults to true.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The panel.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="addHandler">
            <a name="//apple_ref/cpp/Method/addHandler" class="dashAnchor"></a>
            <h5><a href="#addHandler">addHandler</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.setup.panel:addHandler(event, id, handlerFn, keys) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets a handler from an Handler ID</p>
<p>Parameters:</p>
<ul>
<li>event - The event</li>
<li>id - the Handler ID</li>
<li>handlerFn - The Handler function</li>
<li>keys - Keys</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="addHeading">
            <a name="//apple_ref/cpp/Method/addHeading" class="dashAnchor"></a>
            <h5><a href="#addHeading">addHeading</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.setup.panel:addHeading(text) -&gt; panel</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Adds a heading to the panel</p>
<p>Parameters:</p>
<ul>
<li>text - The text of the heading as a string</li>
</ul>
<p>Returns:</p>
<ul>
<li>The panel object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="addIcon">
            <a name="//apple_ref/cpp/Method/addIcon" class="dashAnchor"></a>
            <h5><a href="#addIcon">addIcon</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.setup.panel:addIcon(src) -&gt; panel</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Adds an icon to the panel.</p>
<p>Parameters:</p>
<ul>
<li>src - Location of the icon.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The panel object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="addParagraph">
            <a name="//apple_ref/cpp/Method/addParagraph" class="dashAnchor"></a>
            <h5><a href="#addParagraph">addParagraph</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.setup.panel:addParagraph(content[, escaped[, class]]) -&gt; panel</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Adds a Paragraph to the panel</p>
<p>Parameters:</p>
<ul>
<li>content - The content as a string</li>
<li>escaped - Whether or not the HTML should be escaped as a boolean</li>
<li>class - The class as a string</li>
</ul>
<p>Returns:</p>
<ul>
<li>The panel object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="addPassword">
            <a name="//apple_ref/cpp/Method/addPassword" class="dashAnchor"></a>
            <h5><a href="#addPassword">addPassword</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.setup.panel:addPassword(params) -&gt; panel</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Adds a password text-box to the panel.</p>
<p>Parameters:</p>
<ul>
<li>params - A table of parameters</li>
</ul>
<p>Returns:</p>
<ul>
<li>The panel object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="addSelect">
            <a name="//apple_ref/cpp/Method/addSelect" class="dashAnchor"></a>
            <h5><a href="#addSelect">addSelect</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.setup.panel:addSelect(params) -&gt; panel</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Adds a select to the panel.</p>
<p>Parameters:</p>
<ul>
<li>params - A table of parameters</li>
</ul>
<p>Returns:</p>
<ul>
<li>The panel object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="addSubHeading">
            <a name="//apple_ref/cpp/Method/addSubHeading" class="dashAnchor"></a>
            <h5><a href="#addSubHeading">addSubHeading</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.setup.panel:addSubHeading(text) -&gt; panel</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Adds a sub-heading to the panel</p>
<p>Parameters:</p>
<ul>
<li>text - The text of the sub-heading as a string</li>
</ul>
<p>Returns:</p>
<ul>
<li>The panel object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="addTextbox">
            <a name="//apple_ref/cpp/Method/addTextbox" class="dashAnchor"></a>
            <h5><a href="#addTextbox">addTextbox</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.setup.panel:addTextbox(params) -&gt; panel</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Adds a text-box to the panel</p>
<p>Parameters:</p>
<ul>
<li>params - A table of parameters</li>
</ul>
<p>Returns:</p>
<ul>
<li>The panel object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="getHandler">
            <a name="//apple_ref/cpp/Method/getHandler" class="dashAnchor"></a>
            <h5><a href="#getHandler">getHandler</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.setup.panel:getHandler(id) -&gt; handler</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets a handler from an Handler ID</p>
<p>Parameters:</p>
<ul>
<li><code>id</code> - the Handler ID</li>
</ul>
<p>Returns:</p>
<ul>
<li>A handler.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
