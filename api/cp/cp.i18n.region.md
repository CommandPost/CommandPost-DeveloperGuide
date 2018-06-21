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
      <h1><a href="cp.i18n.region.md">docs</a> &raquo; cp.i18n.region</h1>
      <p>Provides the set of ISO 3166-1 region codes and names.
The return value can be iterated as a list, or you can find a
specific region by either its upper-case two-character code (<code>alpha2</code>), three-character numeric code (<code>numeric3</code>),
or English name (<code>name</code>).</p>
<p>For example:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">region</span> <span class="o">=</span> <span class="nb">require</span><span class="p">(</span><span class="s2">&quot;cp.i18n.region&quot;</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="n">region</span><span class="p">[</span><span class="mi">1</span><span class="p">])</span>    <span class="c1">-- table for &quot;Afghanistan&quot;</span>
<span class="nb">print</span><span class="p">(</span><span class="n">lang</span><span class="p">.</span><span class="n">FR</span><span class="p">)</span>      <span class="c1">-- table for &quot;France&quot;</span>
<span class="nb">print</span><span class="p">(</span><span class="n">lang</span><span class="p">.</span><span class="n">France</span><span class="p">)</span>  <span class="c1">-- same table for &quot;France&quot;</span>
</pre></div>
<p>This will return a table containing the following:</p>
<ul>
<li><code>alpha2</code>      - The 2-character region code, upper-case (eg. "AU", "FR").</li>
<li><code>name</code>        - The name in English (eg. "Australia", "France").</li>
</ul>
<p>Note: This data was adapted from the <a href="https://datahub.io/core/country-list">datahub.io list</a>
released under a Public Domain license.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
      </ul>
      <h3>API Documentation</h3>
