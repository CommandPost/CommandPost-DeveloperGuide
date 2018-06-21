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
      <h1><a href="cp.i18n.language.md">docs</a> &raquo; cp.i18n.language</h1>
      <p>Provides the set of ISO 693-1/2/3 language codes and names.
The return value can be iterated as a list, or you can find a
specific language by either its two-character code (<code>alpha2</code>), English-based three-character code (<code>alpha3B</code>),
local name, or English name.</p>
<p>For example:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">lang</span> <span class="o">=</span> <span class="nb">require</span><span class="p">(</span><span class="s2">&quot;cp.i18n.language&quot;</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="n">lang</span><span class="p">[</span><span class="mi">1</span><span class="p">])</span> <span class="c1">-- table for &quot;Abkhaz&quot; language</span>
<span class="nb">print</span><span class="p">(</span><span class="n">lang</span><span class="p">.</span><span class="n">fr</span><span class="p">)</span> <span class="c1">-- table for &quot;French&quot;</span>
<span class="nb">print</span><span class="p">(</span><span class="n">lang</span><span class="p">.</span><span class="n">fre</span><span class="p">)</span> <span class="c1">-- same table for &quot;French&quot;</span>
<span class="nb">print</span><span class="p">(</span><span class="n">lang</span><span class="p">[</span><span class="s2">&quot;Français&quot;</span><span class="p">])</span> <span class="c1">-- same table for &quot;French&quot;</span>
<span class="nb">print</span><span class="p">(</span><span class="n">lang</span><span class="p">.</span><span class="n">French</span><span class="p">)</span> <span class="c1">-- same table for &quot;French&quot;</span>
</pre></div>
<p>This will return a table containing the following:</p>
<ul>
<li><code>alpha2</code>       - The 2-character language code (eg. "en", "fr").</li>
<li><code>alpha3</code>       - The 3-character language code (eg. "eng", "fra").</li>
<li><code>alpha3B</code>      - The 3-character English-derived language code (eg. "eng", "fre").</li>
<li><code>alpha3T</code>      - The 3-character local-language-derived code (eg. "eng", "fra").</li>
<li><code>localName</code>   - The name in the local language (eg. "English", "Français").</li>
<li><code>name</code>        - The name in English (eg. "English", "French").</li>
</ul>
<p>Note: This data was adapted from <a href="https://github.com/anurbol/languages-iso-639-1-2-3-json">arnubol's code</a>
under an <a href="https://raw.githubusercontent.com/anurbol/languages-iso-639-1-2-3-json/master/LICENSE">MIT license</a>.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
      </ul>
      <h3>API Documentation</h3>
