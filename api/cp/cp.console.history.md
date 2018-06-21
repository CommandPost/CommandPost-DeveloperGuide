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
      <h1><a href="cp.console.history.md">docs</a> &raquo; cp.console.history</h1>
      <p>Console History Manager.</p>
<p>Originally created by @asmagill
<a href="https://github.com/asmagill/hammerspoon-config-take2/blob/master/utils/_actions/consoleHistory.lua">https://github.com/asmagill/hammerspoon-config-take2/blob/master/utils/_actions/consoleHistory.lua</a></p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Variables - Configurable values</li>
          <ul>
            <li><a href="#autosaveHistory">autosaveHistory</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#clearHistory">clearHistory</a></li>
            <li><a href="#history">history</a></li>
            <li><a href="#pruneHistory">pruneHistory</a></li>
            <li><a href="#retrieveHistory">retrieveHistory</a></li>
            <li><a href="#saveHistory">saveHistory</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Variables</h4>
          <section id="autosaveHistory">
            <a name="//apple_ref/cpp/Variable/autosaveHistory" class="dashAnchor"></a>
            <h5><a href="#autosaveHistory">autosaveHistory</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.console.history.autosaveHistory -&gt; timer</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Auto Save History Timer.</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Functions</h4>
          <section id="clearHistory">
            <a name="//apple_ref/cpp/Function/clearHistory" class="dashAnchor"></a>
            <h5><a href="#clearHistory">clearHistory</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.console.history.clearHistory() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Clears the Console History.</p>
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
          <section id="history">
            <a name="//apple_ref/cpp/Function/history" class="dashAnchor"></a>
            <h5><a href="#history">history</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.console.history.history(toFind) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets a history item.</p>
<p>Parameters:</p>
<ul>
<li>toFind - Number of the item to find.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="pruneHistory">
            <a name="//apple_ref/cpp/Function/pruneHistory" class="dashAnchor"></a>
            <h5><a href="#pruneHistory">pruneHistory</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.console.history.pruneHistory() -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Prune History</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>Current History Count</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="retrieveHistory">
            <a name="//apple_ref/cpp/Function/retrieveHistory" class="dashAnchor"></a>
            <h5><a href="#retrieveHistory">retrieveHistory</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.console.history.retrieveHistory() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Retrieve's the Console History.</p>
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
          <section id="saveHistory">
            <a name="//apple_ref/cpp/Function/saveHistory" class="dashAnchor"></a>
            <h5><a href="#saveHistory">saveHistory</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.console.history.saveHistory() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Saves the Console History.</p>
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
