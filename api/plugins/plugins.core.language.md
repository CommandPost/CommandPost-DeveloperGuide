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
      <h1><a href="plugins.core.language.md">docs</a> &raquo; plugins.core.language</h1>
      <p>Language Module.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Variables - Configurable values</li>
          <ul>
            <li><a href="#installedLanguages">installedLanguages</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#getCommandPostLanguages">getCommandPostLanguages</a></li>
            <li><a href="#getUserLocale">getUserLocale</a></li>
            <li><a href="#loadCommandPostLanguages">loadCommandPostLanguages</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Variables</h4>
          <section id="installedLanguages">
            <a name="//apple_ref/cpp/Variable/installedLanguages" class="dashAnchor"></a>
            <h5><a href="#installedLanguages">installedLanguages</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.language.installedLanguages() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>A table of installed languages.</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Functions</h4>
          <section id="getCommandPostLanguages">
            <a name="//apple_ref/cpp/Function/getCommandPostLanguages" class="dashAnchor"></a>
            <h5><a href="#getCommandPostLanguages">getCommandPostLanguages</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.language.getCommandPostLanguages() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets CommandPost Languages in Table</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>installedLanguages - table of Installed Languages</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="getUserLocale">
            <a name="//apple_ref/cpp/Function/getUserLocale" class="dashAnchor"></a>
            <h5><a href="#getUserLocale">getUserLocale</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.language.getUserLocale() -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets a users locale.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The user locale as a string.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="loadCommandPostLanguages">
            <a name="//apple_ref/cpp/Function/loadCommandPostLanguages" class="dashAnchor"></a>
            <h5><a href="#loadCommandPostLanguages">loadCommandPostLanguages</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.language.loadCommandPostLanguages() -&gt; nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Loads Command Post Languages</p>
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
