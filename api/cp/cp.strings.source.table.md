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
      <h1><a href="cp.strings.source.table.md">docs</a> &raquo; cp.strings.source.table</h1>
      <p>Loads strings from provided tables, allowing for a given language variation. Eg:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">src</span> <span class="o">=</span> <span class="nb">require</span><span class="p">(</span><span class="s2">&quot;cp.strings.source.table&quot;</span><span class="p">).</span><span class="n">new</span><span class="p">():</span><span class="n">add</span><span class="p">(</span><span class="s2">&quot;en&quot;</span><span class="p">,</span> <span class="p">{</span><span class="n">foo</span> <span class="o">=</span> <span class="s2">&quot;bar&quot;</span><span class="p">}):</span><span class="n">add</span><span class="p">(</span><span class="s2">&quot;en&quot;</span><span class="p">,</span> <span class="p">{</span><span class="n">foo</span> <span class="o">=</span> <span class="s2">&quot;baz&quot;</span><span class="p">})</span>
<span class="kd">local</span> <span class="n">valueEn</span> <span class="o">=</span> <span class="n">src</span><span class="p">:</span><span class="n">find</span><span class="p">(</span><span class="s2">&quot;en&quot;</span><span class="p">,</span> <span class="s2">&quot;foo&quot;</span><span class="p">)</span> <span class="c1">-- &quot;bar&quot;</span>
<span class="kd">local</span> <span class="n">valueEs</span> <span class="o">=</span> <span class="n">src</span><span class="p">:</span><span class="n">find</span><span class="p">(</span><span class="s2">&quot;en&quot;</span><span class="p">,</span> <span class="s2">&quot;foo&quot;</span><span class="p">)</span> <span class="c1">-- &quot;baz&quot;</span>
</pre></div>
<p>This will load the file for the specified language (replacing <code>${language}</code> with <code>"en"</code> in the path) and return the value.
Note: This will load the file on each request. To have values cached, use the <code>cp.strings</code> module and specify a <code>plist</code> as a source.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Constructors - API calls which return an object, typically one that offers API methods</li>
          <ul>
            <li><a href="#new">new</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#add">add</a></li>
            <li><a href="#context">context</a></li>
            <li><a href="#find">find</a></li>
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
                <td><code>cp.strings.source.table.new(context) -&gt; source</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new <code>cp.strings</code> source that loads strings from a plist file.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The new plist <code>source</code> instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Methods</h4>
          <section id="add">
            <a name="//apple_ref/cpp/Method/add" class="dashAnchor"></a>
            <h5><a href="#add">add</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.strings.source.table:add(keyValues) -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Adds the specified table of key values in the specified language code.</p>
<p>Parameters:</p>
<ul>
<li><code>keyValues</code>  - The table of key/value pairs to define.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.string.source</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="context">
            <a name="//apple_ref/cpp/Method/context" class="dashAnchor"></a>
            <h5><a href="#context">context</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.strings.source.table:context([context]) -&gt; table | self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets or sets a context to be set for the source. This typically includes a <code>language</code>, which
provides the default language code, but may have other source-specific properties.
Calling this method may may clear caches, etc.</p>
<p>Eg:</p>
<div class="highlight"><pre><span></span><span class="n">mySource</span><span class="p">:</span><span class="n">context</span><span class="p">({</span><span class="n">language</span> <span class="o">=</span> <span class="s2">&quot;fr&quot;</span><span class="p">})</span> <span class="c1">-- set the default language to French.</span>
</pre></div>
<p>Parameters:</p>
<ul>
<li>context   - A table with values which may be used by the source.</li>
</ul>
<p>Returns:</p>
<ul>
<li>If a new context is provided, the <code>cp.string.source</code> is returned, otherwise the current context table is returned.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="find">
            <a name="//apple_ref/cpp/Method/find" class="dashAnchor"></a>
            <h5><a href="#find">find</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.strings.source.table:find(key) -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Finds the specified <code>key</code> value in the plist file for the specified optional <code>context</code>,
if the plist can be found, and contains matching key value.</p>
<p>Parameters:</p>
<ul>
<li><code>key</code>        - The key to retrieve the value for.</li>
<li><code>context</code>    - An optional table with additional context.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The value of the key, or <code>nil</code> if not found.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
