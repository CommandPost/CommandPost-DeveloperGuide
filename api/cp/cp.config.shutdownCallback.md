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
      <h1><a href="cp.config.shutdownCallback.md">docs</a> &raquo; cp.config.shutdownCallback</h1>
      <p>Shutdown Callback Module.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#callbackFn">callbackFn</a></li>
            <li><a href="#get">get</a></li>
            <li><a href="#getAll">getAll</a></li>
            <li><a href="#id">id</a></li>
            <li><a href="#new">new</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Methods</h4>
          <section id="callbackFn">
            <a name="//apple_ref/cpp/Method/callbackFn" class="dashAnchor"></a>
            <h5><a href="#callbackFn">callbackFn</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.config.shutdownCallback:callbackFn() -&gt; function</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the callbackFn of the current Shutdown Callback</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The callbackFn of the current Shutdown Callback</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="get">
            <a name="//apple_ref/cpp/Method/get" class="dashAnchor"></a>
            <h5><a href="#get">get</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.config.shutdownCallback:get(id) -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new Shutdown Callback.</p>
<p>Parameters:</p>
<ul>
<li><code>id</code>      - The unique ID for the callback you want to return.</li>
</ul>
<p>Returns:</p>
<ul>
<li>table containing the callback</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="getAll">
            <a name="//apple_ref/cpp/Method/getAll" class="dashAnchor"></a>
            <h5><a href="#getAll">getAll</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.config.shutdownCallback:getAll() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns all of the created Shutdown Callbacks</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>table containing all of the created callbacks</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="id">
            <a name="//apple_ref/cpp/Method/id" class="dashAnchor"></a>
            <h5><a href="#id">id</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.config.shutdownCallback:id() -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the ID of the current Shutdown Callback</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The ID of the current Shutdown Callback as a <code>string</code></li>
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
                <td><code>cp.config.shutdownCallback:new(id, callbackFn) -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new Shutdown Callback.</p>
<p>Parameters:</p>
<ul>
<li><code>id</code>      - The unique ID for this callback.</li>
</ul>
<p>Returns:</p>
<ul>
<li>table that has been created</li>
</ul>
</td>
              </tr>
            </table>
          </section>
