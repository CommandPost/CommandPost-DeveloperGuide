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
      <h1><a href="cp.i18n.script.md">docs</a> &raquo; cp.i18n.script</h1>
      <p>Provides the set of ISO 15924 language scripts.
The return value can be iterated as a list, or you can find a
specific language by either its four-character code (<code>alpha4</code>), three-character numeric code (<code>numeric3</code>),
local name, or English name.</p>
<p>For example:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">script</span> <span class="o">=</span> <span class="nb">require</span><span class="p">(</span><span class="s2">&quot;cp.i18n.script&quot;</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="n">script</span><span class="p">[</span><span class="mi">1</span><span class="p">])</span>        <span class="c1">-- table for &quot;Adlam&quot; script</span>
<span class="nb">print</span><span class="p">(</span><span class="n">script</span><span class="p">.</span><span class="n">Hani</span><span class="p">)</span>      <span class="c1">-- table for &quot;Han&quot; script (matches `alpha4`)</span>
<span class="nb">print</span><span class="p">(</span><span class="n">script</span><span class="p">[</span><span class="s2">&quot;500&quot;</span><span class="p">])</span>    <span class="c1">-- same table for &quot;Han&quot; (matches `numeric3`)</span>
<span class="nb">print</span><span class="p">(</span><span class="n">script</span><span class="p">[</span><span class="s2">&quot;Han (Hanzi, Kanji, Hanja)&quot;</span><span class="p">])</span> <span class="c1">-- same table for &quot;Han&quot; (matches `name`)</span>
<span class="nb">print</span><span class="p">(</span><span class="n">script</span><span class="p">.</span><span class="n">Han</span><span class="p">)</span>       <span class="c1">-- same table for &quot;Han&quot; (matches `pva`).</span>
</pre></div>
<p>This will return a table containing the following:</p>
<ul>
<li><code>alpha4</code>      - The 4-character script code (eg. "Hani", "Arab").</li>
<li><code>date</code>        - The <code>YYYY-MM-DD</code> date the script was added.</li>
<li><code>name</code>        - The name in English (eg. "Arabic", "Afaka").</li>
<li><code>numeric3</code>    - The 3-character language code (eg. "500", "050").</li>
<li><code>pva</code>         - The Property Value Alias. Not available on all scripts.</li>
</ul>
<p>Note: This data was adapted from <a href="https://github.com/wooorm/iso-15924">wooorm's code</a>
under an <a href="https://raw.githubusercontent.com/wooorm/iso-15924/master/LICENSE">MIT license</a>.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
      </ul>
      <h3>API Documentation</h3>
