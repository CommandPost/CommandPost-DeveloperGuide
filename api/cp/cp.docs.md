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
      <h1><a href="cp.docs.md">docs</a> &raquo; cp.docs</h1>
      <p>Documentation Tools.</p>
<p>These tools are for helping generate CommandPost documentation.</p>
<p>Example Usage:</p>
<div class="highlight"><pre><span></span><span class="nb">require</span><span class="p">(</span><span class="s2">&quot;cp.docs&quot;</span><span class="p">).</span><span class="n">generate</span><span class="p">()</span>
</pre></div>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#generate">generate</a></li>
            <li><a href="#generateExtensionLinks">generateExtensionLinks</a></li>
            <li><a href="#updateDeveloperGuideSummary">updateDeveloperGuideSummary</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Functions</h4>
          <section id="generate">
            <a name="//apple_ref/cpp/Function/generate" class="dashAnchor"></a>
            <h5><a href="#generate">generate</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.docs.generate() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Generates the CommandPost Developers Guide.</p>
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
          <section id="generateExtensionLinks">
            <a name="//apple_ref/cpp/Function/generateExtensionLinks" class="dashAnchor"></a>
            <h5><a href="#generateExtensionLinks">generateExtensionLinks</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.docs.generateExtensionLinks(folder) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns markup of all of the API links for a specific group of extensions.</p>
<p>Parameters:</p>
<ul>
<li>folder - The folder you want to process (i.e. "cp", "plugins" or "hs").</li>
</ul>
<p>Returns:</p>
<ul>
<li>The result as a string, otherwise <code>nil</code> if an error occurs.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="updateDeveloperGuideSummary">
            <a name="//apple_ref/cpp/Function/updateDeveloperGuideSummary" class="dashAnchor"></a>
            <h5><a href="#updateDeveloperGuideSummary">updateDeveloperGuideSummary</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.docs.updateDeveloperGuideSummary() -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Updates the Developer Guide Summary.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successful otherwise <code>nil</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
