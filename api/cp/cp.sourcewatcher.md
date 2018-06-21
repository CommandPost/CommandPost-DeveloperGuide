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
      <h1><a href="cp.sourcewatcher.md">docs</a> &raquo; cp.sourcewatcher</h1>
      <p>Watches folders for specific file extensions and reloads the app if they change.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#filesChanged">filesChanged</a></li>
            <li><a href="#matchesExtensions">matchesExtensions</a></li>
            <li><a href="#new">new</a></li>
            <li><a href="#start">start</a></li>
            <li><a href="#stop">stop</a></li>
            <li><a href="#watchPath">watchPath</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Methods</h4>
          <section id="filesChanged">
            <a name="//apple_ref/cpp/Method/filesChanged" class="dashAnchor"></a>
            <h5><a href="#filesChanged">filesChanged</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.sourcewatcher:filesChanged(files, flagTables) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks that the file that triggered the Path Watcher matches the extension given.</p>
<p>Parameters:</p>
<ul>
<li><code>files</code>      - Table of files to check as strings</li>
<li><code>flagTables</code> - Table of flagTables (see: <code>hs.pathwatcher.new</code>)</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="matchesExtensions">
            <a name="//apple_ref/cpp/Method/matchesExtensions" class="dashAnchor"></a>
            <h5><a href="#matchesExtensions">matchesExtensions</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.sourcewatcher:matchesExtensions(file) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks that the file that triggered the Path Watcher matches the extension given.</p>
<p>Parameters:</p>
<ul>
<li><code>file</code>       - The file as string</li>
</ul>
<p>Returns:</p>
<ul>
<li>A boolean value</li>
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
                <td><code>cp.sourcewatcher.new(extensions) -&gt; sourcewatcher</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new <code>sourcewatcher</code> instance.</p>
<p>Parameters:</p>
<ul>
<li><code>extensions</code>     - Extensions</li>
</ul>
<p>Returns:</p>
<ul>
<li>A sourcewatcher instance</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="start">
            <a name="//apple_ref/cpp/Method/start" class="dashAnchor"></a>
            <h5><a href="#start">start</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.sourcewatcher:start() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Starts a Source Watcher.</p>
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
          <section id="stop">
            <a name="//apple_ref/cpp/Method/stop" class="dashAnchor"></a>
            <h5><a href="#stop">stop</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.sourcewatcher:stop() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Stops a Source Watcher.</p>
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
          <section id="watchPath">
            <a name="//apple_ref/cpp/Method/watchPath" class="dashAnchor"></a>
            <h5><a href="#watchPath">watchPath</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.sourcewatcher:watchPath(path) -&gt; sourcewatcher</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Watches a path.</p>
<p>Parameters:</p>
<ul>
<li><code>path</code>       - The path you want to watch as a string.</li>
</ul>
<p>Returns:</p>
<ul>
<li>sourcewatcher</li>
</ul>
</td>
              </tr>
            </table>
          </section>
