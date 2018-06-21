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
      <h1><a href="cp.web.text.md">docs</a> &raquo; cp.web.text</h1>
      <p>Functions for managing text on the web.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#escapeXML">escapeXML</a></li>
            <li><a href="#unescapeXML">unescapeXML</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Functions</h4>
          <section id="escapeXML">
            <a name="//apple_ref/cpp/Function/escapeXML" class="dashAnchor"></a>
            <h5><a href="#escapeXML">escapeXML</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.web.text.escapeXML(s) -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Escapes a string</p>
<p>Parameters:</p>
<ul>
<li>s - The string you want to escape</li>
</ul>
<p>Returns:</p>
<ul>
<li>The string, escaped for XML.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="unescapeXML">
            <a name="//apple_ref/cpp/Function/unescapeXML" class="dashAnchor"></a>
            <h5><a href="#unescapeXML">unescapeXML</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.web.text.unescapeXML(s) -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Unescapes a string from XML encoding.</p>
<p>Parameters:</p>
<ul>
<li>s - The string you want to unescape</li>
</ul>
<p>Returns:</p>
<ul>
<li>The string, unescaped.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
