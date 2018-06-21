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
      <h1><a href="cp.ids.md">docs</a> &raquo; cp.ids</h1>
      <p>Allows managing values/IDs which can vary between versions.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#new">new</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#currentVersion">currentVersion</a></li>
            <li><a href="#load">load</a></li>
            <li><a href="#of">of</a></li>
            <li><a href="#ofCurrent">ofCurrent</a></li>
            <li><a href="#previousVersion">previousVersion</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Functions</h4>
          <section id="new">
            <a name="//apple_ref/cpp/Function/new" class="dashAnchor"></a>
            <h5><a href="#new">new</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ids.new(path[, currentVersionFn]) -&gt; cp.ids</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new <code>ids</code> instance with the specified path to the version files and
a function to find the current version, if appropriate.</p>
<p>Parameters:</p>
<ul>
<li><code>path</code>                - The path to the version files.</li>
<li><code>currentVersionFn</code>    - An optional function that will return the current version as a string or <code>semver</code>.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A new <code>cp.ids</code> instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Methods</h4>
          <section id="currentVersion">
            <a name="//apple_ref/cpp/Method/currentVersion" class="dashAnchor"></a>
            <h5><a href="#currentVersion">currentVersion</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ids:currentVersion() -&gt; semver</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the current version number for the <code>IDs</code> library. May be <code>nil</code>.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A <code>semver</code> with the version number or <code>nil</code> if none is available.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="load">
            <a name="//apple_ref/cpp/Method/load" class="dashAnchor"></a>
            <h5><a href="#load">load</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ids:load([version]) -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Loads and caches IDs for the given version. It will search through previous versions,
with each subsequent version file overriding the previous version's value, if present.</p>
<p>Parameters:</p>
<ul>
<li>version - The version number you want to load as a string (i.e. "10.4.0"). If not provided, the current version is loaded.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table containing all the IDs</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="of">
            <a name="//apple_ref/cpp/Method/of" class="dashAnchor"></a>
            <h5><a href="#of">of</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ids:of(version, subset) -&gt; function</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a function which can be called to retrieve a specific value for the specified version.</p>
<p>Eg:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">id</span> <span class="o">=</span> <span class="n">ids</span><span class="p">:</span><span class="n">of</span><span class="p">(</span><span class="s2">&quot;10.4.0&quot;</span><span class="p">,</span> <span class="s2">&quot;CommandEditor&quot;</span><span class="p">)</span>
<span class="nb">print</span> <span class="s2">&quot;bar = &quot;</span><span class="o">..</span><span class="n">id</span><span class="p">(</span><span class="s2">&quot;bar&quot;</span><span class="p">)</span>
</pre></div>
<p>Parameters:</p>
<ul>
<li>version - The version number you want to load as a string (i.e. "10.4.0")</li>
<li>subset - A string containing the subset of data you want to load</li>
</ul>
<p>Returns:</p>
<ul>
<li>A function that will return the value of the specified <code>subset</code> ID for the specified version.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="ofCurrent">
            <a name="//apple_ref/cpp/Method/ofCurrent" class="dashAnchor"></a>
            <h5><a href="#ofCurrent">ofCurrent</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ids:ofCurrent(subset) -&gt; function</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a function which can be called with an ID to retrieve a specific value for the current version.</p>
<p>Parameters:</p>
<ul>
<li>subset - A string containing the subset of data you want to load</li>
</ul>
<p>Returns:</p>
<ul>
<li>A function that will return the value of the specified <code>subset</code> ID for the current version.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="previousVersion">
            <a name="//apple_ref/cpp/Method/previousVersion" class="dashAnchor"></a>
            <h5><a href="#previousVersion">previousVersion</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ids:previousVersion([version]) -&gt; semver</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the previous version number that has stored IDs.</p>
<p>Parameters:</p>
<ul>
<li>version      - The version number you want to load as a string (i.e. "10.4.0") or a <code>semver</code>, or <code>nil</code> to use the current version.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A <code>semver</code> instance for the previous version.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
