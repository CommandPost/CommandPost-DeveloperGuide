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
      <h1><a href="cp.web.xml.md">docs</a> &raquo; cp.web.xml</h1>
      <p>Functions for Generating XML markup.</p>
<p>This library allows the creation of 'safe' XML using via code.</p>
<p>Examples:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">xml</span> <span class="o">=</span> <span class="nb">require</span> <span class="s2">&quot;cp.web.xml&quot;</span>
<span class="nb">print</span> <span class="n">xml</span><span class="p">.</span><span class="n">Root</span> <span class="s2">&quot;Hello world!&quot;</span>                       <span class="c1">-- &quot;&lt;Root&gt;Hello world!&lt;/Root&gt;&quot;</span>
<span class="nb">print</span> <span class="n">xml</span><span class="p">.</span><span class="n">Root</span> <span class="p">{</span> <span class="n">class</span> <span class="o">=</span> <span class="s2">&quot;custom&quot;</span> <span class="p">}</span> <span class="s2">&quot;Hello world!&quot;</span>  <span class="c1">-- &quot;&lt;Root class=&#39;custom&#39;&gt;Hello world!&lt;/Root&gt;&quot;</span>
<span class="nb">print</span> <span class="n">xml</span><span class="p">.</span><span class="n">Root</span> <span class="p">{</span> <span class="n">class</span> <span class="o">=</span> <span class="s2">&quot;custom&quot;</span> <span class="p">}</span> <span class="p">(</span>
    <span class="n">xml</span><span class="p">.</span><span class="n">Child</span> <span class="s2">&quot;One&quot;</span> <span class="o">..</span> <span class="s2">&quot; and &quot;</span> <span class="o">..</span> <span class="n">xml</span><span class="p">.</span><span class="n">Child</span> <span class="s2">&quot;Two&quot;</span> <span class="o">..</span> <span class="s2">&quot;.&quot;</span>
<span class="p">)</span>
<span class="c1">-- &quot;&lt;Root class=&#39;custom&#39;&gt;&lt;Child&gt;One&lt;/Child&gt; and &lt;Child&gt;Two&lt;/Child&gt;.&lt;/Root&gt;&quot;</span>
<span class="nb">print</span> <span class="n">xml</span><span class="p">(</span><span class="s2">&quot;1 &lt; 2&quot;</span><span class="p">)</span>                                      <span class="c1">-- &quot;1 &amp;lt; 2&quot; (escaped)</span>
<span class="nb">print</span> <span class="n">xml</span><span class="p">(</span><span class="s2">&quot;1 &lt; 2&quot;</span><span class="p">,</span> <span class="kc">true</span><span class="p">)</span>                                <span class="c1">-- &quot;1 &lt; 2&quot; (unescaped)</span>
<span class="nb">print</span> <span class="n">xml</span><span class="p">.</span><span class="n">Root</span> <span class="p">(</span><span class="s2">&quot;&lt;Child&gt;One&lt;/Child&gt;&quot;</span><span class="p">,</span> <span class="kc">true</span><span class="p">)</span>             <span class="c1">-- &quot;&lt;Root&gt;&lt;Child&gt;One&lt;/Child&gt;&lt;/Root&gt;&quot;</span>
</pre></div>
<p>Be aware that concatonating with ".." can behave unexpectedly in some cases. For example:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">name</span> <span class="o">=</span> <span class="s2">&quot;world!&quot;</span>
<span class="nb">print</span> <span class="n">xml</span><span class="p">.</span><span class="n">Root</span> <span class="s2">&quot;Hello &quot;</span> <span class="o">..</span> <span class="n">name</span>                 <span class="c1">-- &quot;&lt;Root&gt;Hello &lt;/Root&gt;world!&quot;</span>
</pre></div>
<p>The <code>"Hello"</code> gets inserted into the <code>Root</code> tag, but the <code>name</code> gets concatonated after the closing tag.
To get the <code>name</code> inside the <code>Root</code> tag, we need to put brackets around the content:</p>
<div class="highlight"><pre><span></span><span class="nb">print</span> <span class="n">xml</span><span class="p">.</span><span class="n">Root</span> <span class="p">(</span><span class="s2">&quot;Hello &quot;</span> <span class="o">..</span> <span class="n">name</span><span class="p">)</span>                   <span class="c1">-- &quot;&lt;Root&gt;Hello world!&lt;/Root&gt;&quot;</span>
</pre></div>
<p>Any tag name can be generated, along with any attribute. The results are correctly escaped.
There are two 'special' tag names:</p>
<ul>
<li><code>CDATA</code>  - will generate a <code>&amp;lt;![CDATA[ ... ]]&amp;gt;</code> section with the content contained.</li>
<li><code>__</code>     - (double underscore) will generate a <code>&amp;lt!-- ... --&amp;gt</code> comment block.</li>
</ul>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#is">is</a></li>
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
                <td><code>cp.web.xml.is(value) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks if the <code>value</code> is an <code>cp.web.xml</code> block.</p>
<p>Parameters:</p>
<ul>
<li>value     - the value to check</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if it is an HTML block, or <code>false</code> otherwise.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
