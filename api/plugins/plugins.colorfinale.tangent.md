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
      <h1><a href="plugins.colorfinale.tangent.md">docs</a> &raquo; plugins.colorfinale.tangent</h1>
      <p>This plugin basically just disables CP's Tangent Manager when ColorFinale is running.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Variables - Configurable values</li>
          <ul>
            <li><a href="#colorFinaleActive">colorFinaleActive</a></li>
            <li><a href="#colorFinaleInstalled">colorFinaleInstalled</a></li>
            <li><a href="#colorFinaleVisible">colorFinaleVisible</a></li>
            <li><a href="#colorFinaleWindowUI">colorFinaleWindowUI</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#init">init</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Variables</h4>
          <section id="colorFinaleActive">
            <a name="//apple_ref/cpp/Variable/colorFinaleActive" class="dashAnchor"></a>
            <h5><a href="#colorFinaleActive">colorFinaleActive</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.colorfinale.tangent.colorFinaleActive &lt;cp.prop: boolean; read-only; live&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks to see if ColorFinale is active.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="colorFinaleInstalled">
            <a name="//apple_ref/cpp/Variable/colorFinaleInstalled" class="dashAnchor"></a>
            <h5><a href="#colorFinaleInstalled">colorFinaleInstalled</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.colorfinale.tangent.colorFinaleInstalled &lt;cp.prop: boolean; read-only; live&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks to see if ColorFinale is installed.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="colorFinaleVisible">
            <a name="//apple_ref/cpp/Variable/colorFinaleVisible" class="dashAnchor"></a>
            <h5><a href="#colorFinaleVisible">colorFinaleVisible</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.colorfinale.tangent.colorFinaleVisible &lt;cp.prop: boolean; read-only; live&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks to see if an object is a Color Finale window.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="colorFinaleWindowUI">
            <a name="//apple_ref/cpp/Variable/colorFinaleWindowUI" class="dashAnchor"></a>
            <h5><a href="#colorFinaleWindowUI">colorFinaleWindowUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.colorfinale.tangent.colorFinaleWindowUI &lt;cp.prop: hs._asm.axuielement; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the <code>axuielement</code> for the ColorFinale window, if present.</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Functions</h4>
          <section id="init">
            <a name="//apple_ref/cpp/Function/init" class="dashAnchor"></a>
            <h5><a href="#init">init</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.colorfinale.tangent.init(tangentManager) -&gt; module</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Initialise the module.</p>
<p>Parameters:</p>
<ul>
<li>tangentManager - The Tangent Manager</li>
</ul>
<p>Returns:</p>
<ul>
<li>The ColorFinale Tangent Module.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
