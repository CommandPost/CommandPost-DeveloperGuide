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
      <h1><a href="cp.i18n.localeID.md">docs</a> &raquo; cp.i18n.localeID</h1>
      <p>As per <a href="https://developer.apple.com/library/content/documentation/MacOSX/Conceptual/BPInternational/LanguageandLocaleIDs/LanguageandLocaleIDs.html#//apple_ref/doc/uid/10000171i-CH15-SW6">Apple's documentation</a>,
a <code>local ID</code> is a code which identifies either a language used across multiple regions,
a dialect from a specific region, a script used in multiple regions, or a combination of all three.
See the <a href="#parse">parse</a> function for details.</p>
<p>When you parse a code with the <a href="#forCode">forCode</a> function, it will result in a table that contains a
reference to the approprate <code>cp.i18n.language</code> table, and any specified <code>cp.i18n.region</code>
or <code>cp.i18n.script</code> tables. These contain the full details for each language/regin/script, as appropriate.</p>
<p>You can also convert the resulting table back to the code via <code>tostring</code>, or the <a href="#code">code</a> method.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#is">is</a></li>
            <li><a href="#parse">parse</a></li>
          </ul>
        <li>Constructors - API calls which return an object, typically one that offers API methods</li>
          <ul>
            <li><a href="#forCode">forCode</a></li>
          </ul>
        <li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
          <ul>
            <li><a href="#code">code</a></li>
            <li><a href="#language">language</a></li>
            <li><a href="#localName">localName</a></li>
            <li><a href="#name">name</a></li>
            <li><a href="#region">region</a></li>
            <li><a href="#script">script</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#matches">matches</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Functions</h4>
          <section id="is">
            <a name="//apple_ref/cpp/Function/is" class="dashAnchor"></a>
            <h5><a href="#is">is</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.i18n.localeID.is(other) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks if the <code>other</code> is a <code>localeID</code>.</p>
<p>Parameters:</p>
<ul>
<li>other     - the other value to check.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if it is a <code>cp.i18n.locale</code>, otherwise <code>false</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="parse">
            <a name="//apple_ref/cpp/Function/parse" class="dashAnchor"></a>
            <h5><a href="#parse">parse</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.i18n.localeID.parse(code) -&gt; string, string, string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Parses a <code>language ID</code> into three possible string components:</p>
<ol>
<li>The ISO 693-1 language code</li>
<li>The ISO 15924 script code</li>
<li>The ISO 3166-1 region code</li>
</ol>
<p>This is one of the following patterns:</p>
<ul>
<li><code>[language]</code> - eg. <code>"en"</code>, or <code>"fr"</code>. This covers the language across all languages and scripts. We also allow the full name (eg. "English" or "French") since this seems common in Apple's I18N management.</li>
<li><code>[language]_[region]</code> - eg. "en_AU" for Australian English, "fr_CA" for Canadian French, etc.</li>
<li><code>[language]-[script]</code> - eg. "az-Arab" for Azerbaijani in Arabic script, "az-Latn" for Azerbaijani in Latin script.</li>
<li><code>[language]-[script]_[region]</code> - eg. "en-Latin-AU"</li>
</ul>
<p>It will then return the matched component in three return values: language, script, region.
If a <code>region</code> is specified, the <code>script</code> will be <code>nil</code>. Eg.:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">lang</span><span class="p">,</span> <span class="n">scrpt</span><span class="p">,</span> <span class="n">rgn</span> <span class="o">=</span> <span class="n">localeID</span><span class="p">.</span><span class="n">parse</span><span class="p">(</span><span class="s2">&quot;en_AU&quot;</span><span class="p">)</span> <span class="c1">-- results in &quot;en&quot;, nil, &quot;AU&quot;</span>
</pre></div>
<p>Parameters:</p>
<ul>
<li>code      - The <code>locale ID</code> code. Eg. "en_AU".</li>
</ul>
<p>Returns:</p>
<ul>
<li>language  - The two-character lower-case alpha language code.</li>
<li>script    - the four-character mixed-case alpha script code.</li>
<li>region    - The two-character upper-case alpha region code.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Constructors</h4>
          <section id="forCode">
            <a name="//apple_ref/cpp/Constructor/forCode" class="dashAnchor"></a>
            <h5><a href="#forCode">forCode</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.i18n.localeID.forCode(code) -&gt; cp.i18n.localeID or nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates, or retrieves from the cache, a <code>localeID</code> instance for the specified <code>code</code>.</p>
<p>If the code can't be parsed, or if the actual language/region/script codes don't exist,
<code>nil</code> is returned.</p>
<p>Parameters:</p>
<ul>
<li>code      - The language ID code.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The matching <code>langaugeID</code>, or <code>nil</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Fields</h4>
          <section id="code">
            <a name="//apple_ref/cpp/Field/code" class="dashAnchor"></a>
            <h5><a href="#code">code</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.i18n.localeID.code <string></code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The locale ID code.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="language">
            <a name="//apple_ref/cpp/Field/language" class="dashAnchor"></a>
            <h5><a href="#language">language</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.i18n.localeID.language &lt;cp.i18n.language&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The matching <code>language</code> details.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="localName">
            <a name="//apple_ref/cpp/Field/localName" class="dashAnchor"></a>
            <h5><a href="#localName">localName</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.i18n.localeID.localName <string></code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The local name in it's own language.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="name">
            <a name="//apple_ref/cpp/Field/name" class="dashAnchor"></a>
            <h5><a href="#name">name</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.i18n.localeID.name <string></code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The locale name in English.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="region">
            <a name="//apple_ref/cpp/Field/region" class="dashAnchor"></a>
            <h5><a href="#region">region</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.i18n.localeID.region &lt;cp.i18n.region&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The matching <code>region</code> details, if appropriate. Will be <code>nil</code> if no region was specified in the <code>code</code>.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="script">
            <a name="//apple_ref/cpp/Field/script" class="dashAnchor"></a>
            <h5><a href="#script">script</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.i18n.localeID.script &lt;cp.i18n.script&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The matching <code>script</code> details, if appropriate. Will be <code>nil</code> if no script was specified in the <code>code</code>.</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Methods</h4>
          <section id="matches">
            <a name="//apple_ref/cpp/Method/matches" class="dashAnchor"></a>
            <h5><a href="#matches">matches</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.i18n.localeID:matches(otherLocale) -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>This compares the <code>otherLocale</code> to this locale and returns a number indicating the 'strength'
of the match. It will be a value between <code>0</code> and <code>3</code>. The <code>script</code> and <code>region</code> in any locale
are optional, and if they are not provided, they are considered "open" and will match with another locale which
has the script or region defined. However, it is considered to be a weaker match.</p>
<p>For example:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">l</span> <span class="o">=</span> <span class="n">localeID</span><span class="p">.</span><span class="n">forCode</span>
<span class="kd">local</span> <span class="n">en</span><span class="p">,</span> <span class="n">en_AU</span><span class="p">,</span> <span class="n">en_Latn</span><span class="p">,</span> <span class="n">en_Latn_AU</span><span class="p">,</span> <span class="n">en_NZ</span><span class="p">,</span> <span class="n">de</span> <span class="o">=</span> <span class="n">l</span><span class="p">(</span><span class="s2">&quot;en&quot;</span><span class="p">),</span> <span class="n">l</span><span class="p">(</span><span class="s2">&quot;en_AU&quot;</span><span class="p">),</span> <span class="n">l</span><span class="p">(</span><span class="s2">&quot;en-Latn&quot;</span><span class="p">),</span> <span class="n">l</span><span class="p">(</span><span class="s2">&quot;en-Latn_AU&quot;</span><span class="p">),</span> <span class="n">l</span><span class="p">(</span><span class="s2">&quot;en_NZ&quot;</span><span class="p">),</span> <span class="n">l</span><span class="p">(</span><span class="s2">&quot;de&quot;</span><span class="p">)</span>

<span class="n">en</span><span class="p">:</span><span class="n">matches</span><span class="p">(</span><span class="n">de</span><span class="p">)</span>              <span class="o">==</span> <span class="mi">0</span>    <span class="c1">-- no match - different language</span>

<span class="n">en</span><span class="p">:</span><span class="n">matches</span><span class="p">(</span><span class="n">en</span><span class="p">)</span>              <span class="o">==</span> <span class="mi">3</span>    <span class="c1">-- language, script, and region match exactly</span>
<span class="n">en</span><span class="p">:</span><span class="n">matches</span><span class="p">(</span><span class="n">en_AU</span><span class="p">)</span>           <span class="o">==</span> <span class="mf">2.5</span>  <span class="c1">-- language and script match, region half-match with one side &quot;open&quot;.</span>
<span class="n">en</span><span class="p">:</span><span class="n">matches</span><span class="p">(</span><span class="n">en_Latn</span><span class="p">)</span>         <span class="o">==</span> <span class="mf">2.5</span>  <span class="c1">-- language and region match, script half-match with one side &quot;open&quot;.</span>
<span class="n">en</span><span class="p">:</span><span class="n">matches</span><span class="p">(</span><span class="n">en_Latn_AU</span><span class="p">)</span>      <span class="o">==</span> <span class="mi">2</span>    <span class="c1">-- language matches, two half-matches for script and region.</span>

<span class="n">en_AU</span><span class="p">:</span><span class="n">matches</span><span class="p">(</span><span class="n">en_AU</span><span class="p">)</span>        <span class="o">==</span> <span class="mi">3</span>    <span class="c1">-- exact match</span>
<span class="n">en_AU</span><span class="p">:</span><span class="n">matches</span><span class="p">(</span><span class="n">en</span><span class="p">)</span>           <span class="o">==</span> <span class="mf">2.5</span>  <span class="c1">-- language and script match, region half-match with a `nil` on one side.</span>
<span class="n">en_AU</span><span class="p">:</span><span class="n">matches</span><span class="p">(</span><span class="n">en_NZ</span><span class="p">)</span>        <span class="o">==</span> <span class="mi">2</span>    <span class="c1">-- language and script match, but no match between specific regions.</span>
<span class="n">en_AU</span><span class="p">:</span><span class="n">matches</span><span class="p">(</span><span class="n">en_Latn_AU</span><span class="p">)</span>   <span class="o">==</span> <span class="mf">2.5</span>  <span class="c1">-- language and region match exactly, and the optional `script` value is different.</span>
</pre></div>
<p>The higher the match value, the closer they are to matching. If selecting a from multiple locales which match you will generally want the highest-ranking match.</p>
<p>Parameters:</p>
<ul>
<li>otherLocale       - The other locale to compare to.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A number from <code>0</code> to <code>3</code> indicating the match strength.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
