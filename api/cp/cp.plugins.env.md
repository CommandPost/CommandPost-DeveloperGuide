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
      <h1><a href="cp.plugins.env.md">docs</a> &raquo; cp.plugins.env</h1>
      <p>Provides access to resources in the plugin environment. In generally, this will be files stored in a Complex Plugin's folder.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Constructors - API calls which return an object, typically one that offers API methods</li>
          <ul>
            <li><a href="#new">new</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#compileTemplate">compileTemplate</a></li>
            <li><a href="#pathToAbsolute">pathToAbsolute</a></li>
            <li><a href="#pathToURL">pathToURL</a></li>
            <li><a href="#readResource">readResource</a></li>
            <li><a href="#renderTemplate">renderTemplate</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Constructors</h4>
          <section id="new">
            <a name="//apple_ref/cpp/Constructor/new" class="dashAnchor"></a>
            <h5><a href="#new">new</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.plugins.env.new(rootPath) -&gt; cp.plugins.env</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new <code>env</code> pointing at the specified root folder path.</p>
<p>Parameters:</p>
<ul>
<li><code>rootPath</code> the path to the plugin's root folder.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The new <code>env</code> instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Methods</h4>
          <section id="compileTemplate">
            <a name="//apple_ref/cpp/Method/compileTemplate" class="dashAnchor"></a>
            <h5><a href="#compileTemplate">compileTemplate</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.plugins.env:compileTemplate(view[, layout]) -&gt; function</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Compiles a Resty Template within the context of the plugin. The <code>view</code> may be a resource path pointing at a template file in the plugin, or may be raw template markup. The <code>layout</code> is an optional path/template for a layout template. See the <a href="https://github.com/bungle/lua-resty-template">Resty Template</a> documentation for details.</p>
<p>It returns a function which can have a <code>model</code> table passed in which will provide variables/functions/etc that the template can access while rendering. The function can be reused multiple times with different context values.</p>
<p>Parameters:</p>
<ul>
<li><code>view</code>    - The local path inside the plugin to the template file, or raw template markup.</li>
<li><code>layout</code>  - The local path inside the plugin to the layout file.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A function which will render the template.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="pathToAbsolute">
            <a name="//apple_ref/cpp/Method/pathToAbsolute" class="dashAnchor"></a>
            <h5><a href="#pathToAbsolute">pathToAbsolute</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.plugins.env:pathToAbsolute(resourcePath) -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the absolute path to the file referred to by the relative resource path. If an image is stored as <code>images/my.jpg</code> in the plugin, the resource path will be <code>"images/my.jpg"</code>. The result will be the full path to that file. If the file cannot be found in the plugin, it will look in the <code>cp/resources/assets</code> folder for globally-shared resources.</p>
<p>Parameters:</p>
<ul>
<li><code>resourcePath</code>    - The local path to the resource inside the plugin.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The absolute path to the resource, or <code>nil</code> if it does not exist.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="pathToURL">
            <a name="//apple_ref/cpp/Method/pathToURL" class="dashAnchor"></a>
            <h5><a href="#pathToURL">pathToURL</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.plugins.env:pathToURL(resourcePath) -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns an absolute <code>file://</code> URL to the file referred to by the relative resource path. If an image is stored as <code>images/my.jpg</code> in the plugin, the resource path will be <code>"images/my.jpg"</code>. The result will be a URL to that file. If the file cannot be found in the plugin, it will look in the <code>cp/resources/assets</code> folder for globally-shared resources.</p>
<p>Parameters:</p>
<ul>
<li><code>resourcePath</code>    - The local path to the resource inside the plugin.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The absolute URL to the resource, or <code>nil</code> if it does not exist.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="readResource">
            <a name="//apple_ref/cpp/Method/readResource" class="dashAnchor"></a>
            <h5><a href="#readResource">readResource</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.plugins.env:readResource(resourcePath) -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Reads the contents of the resource at the specified resource path. This is returned as a string of data (which may or may not be an actual readable string, depending on the source content).</p>
<p>Parameters:</p>
<ul>
<li><code>resourcePath</code>    - The local path to the resource inside the plugin.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The contents of the resouce, or <code>nil</code> if the file does not exist.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="renderTemplate">
            <a name="//apple_ref/cpp/Method/renderTemplate" class="dashAnchor"></a>
            <h5><a href="#renderTemplate">renderTemplate</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.plugins.env:renderTemplate(view[, model[, layout]]) -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Renders a Resty Template within the context of the plugin. The <code>view</code> may be a resource path pointing at a template file in the plugin, or may be raw template markup. The <code>layout</code> is an optional path/template for a layout template. See the <a href="https://github.com/bungle/lua-resty-template">Resty Template</a> documentation for details.</p>
<p>The <code>model</code> is a table which will provide variables/functions/etc that the template can access while rendering.</p>
<p>Parameters:</p>
<ul>
<li><code>view</code>    - The local path inside the plugin to the template file, or raw template markup.</li>
<li><code>model</code>   - The model which provides variables/functions/etc to the template.</li>
<li><code>layout</code>  - The local path inside the plugin to the layout file.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A function which will render the template.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
