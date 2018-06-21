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
      <h1><a href="plugins.finalcutpro.timeline.audioeffects.md">docs</a> &raquo; plugins.finalcutpro.timeline.audioeffects</h1>
      <p>Controls Final Cut Pro's Audio Effects.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#audioeffects">audioeffects</a></li>
            <li><a href="#init">init</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Functions</h4>
          <section id="audioeffects">
            <a name="//apple_ref/cpp/Function/audioeffects" class="dashAnchor"></a>
            <h5><a href="#audioeffects">audioeffects</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.timeline.audioeffects(action) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Applies the specified action as a audio effect. Expects action to be a table with the following structure:</p>
<div class="highlight"><pre><span></span><span class="p">{</span> <span class="n">name</span> <span class="o">=</span> <span class="s2">&quot;XXX&quot;</span><span class="p">,</span> <span class="n">category</span> <span class="o">=</span> <span class="s2">&quot;YYY&quot;</span><span class="p">,</span> <span class="n">theme</span> <span class="o">=</span> <span class="s2">&quot;ZZZ&quot;</span> <span class="p">}</span>
</pre></div>
<p>...where <code>"XXX"</code>, <code>"YYY"</code> and <code>"ZZZ"</code> are in the current FCPX language. The <code>category</code> and <code>theme</code> are optional,
but if they are known it's recommended to use them, or it will simply execute the first matching audio effect with that name.</p>
<p>Alternatively, you can also supply a string with just the name.</p>
<p>Parameters:</p>
<ul>
<li><code>action</code>     - A table with the name/category/theme for the audio effect to apply, or a string with just the name.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if a matching audio effect was found and applied to the timeline.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="init">
            <a name="//apple_ref/cpp/Function/init" class="dashAnchor"></a>
            <h5><a href="#init">init</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.timeline.audioeffects.init() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Initialise the Module</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The Module</li>
</ul>
</td>
              </tr>
            </table>
          </section>
