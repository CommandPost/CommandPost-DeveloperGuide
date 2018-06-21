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
      <h1><a href="plugins.finalcutpro.pasteboard.history.md">docs</a> &raquo; plugins.finalcutpro.pasteboard.history</h1>
      <p>Pasteboard History</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#addHistoryItem">addHistoryItem</a></li>
            <li><a href="#clearHistory">clearHistory</a></li>
            <li><a href="#getHistory">getHistory</a></li>
            <li><a href="#init">init</a></li>
            <li><a href="#pasteHistoryItem">pasteHistoryItem</a></li>
            <li><a href="#setHistory">setHistory</a></li>
            <li><a href="#update">update</a></li>
          </ul>
        <li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
          <ul>
            <li><a href="#enabled">enabled</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Functions</h4>
          <section id="addHistoryItem">
            <a name="//apple_ref/cpp/Function/addHistoryItem" class="dashAnchor"></a>
            <h5><a href="#addHistoryItem">addHistoryItem</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.pasteboard.history.addHistoryItem(data, label) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Adds an item to the Pasteboard history.</p>
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
          <section id="clearHistory">
            <a name="//apple_ref/cpp/Function/clearHistory" class="dashAnchor"></a>
            <h5><a href="#clearHistory">clearHistory</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.pasteboard.history.clearHistory() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Clears the Pasteboard History.</p>
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
          <section id="getHistory">
            <a name="//apple_ref/cpp/Function/getHistory" class="dashAnchor"></a>
            <h5><a href="#getHistory">getHistory</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.pasteboard.history.getHistory() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the Pasteboard History.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table of the Pasteboard history.</li>
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
                <td><code>plugins.finalcutpro.pasteboard.history.init(manager) -&gt; Pasteboard History Object</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Initialises the module.</p>
<p>Parameters:</p>
<ul>
<li>manager - The Pasteboard manager object.</li>
</ul>
<p>Returns:</p>
<ul>
<li>Pasteboard History Object</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="pasteHistoryItem">
            <a name="//apple_ref/cpp/Function/pasteHistoryItem" class="dashAnchor"></a>
            <h5><a href="#pasteHistoryItem">pasteHistoryItem</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.pasteboard.history.pasteHistoryItem(index) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Pastes a Pasteboard History Item.</p>
<p>Parameters:</p>
<ul>
<li>index - The index of the Pasteboard history item.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="setHistory">
            <a name="//apple_ref/cpp/Function/setHistory" class="dashAnchor"></a>
            <h5><a href="#setHistory">setHistory</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.pasteboard.history.setHistory(history) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Sets the Pasteboard History.</p>
<p>Parameters:</p>
<ul>
<li>history - The history in a table.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="update">
            <a name="//apple_ref/cpp/Function/update" class="dashAnchor"></a>
            <h5><a href="#update">update</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.pasteboard.history.update() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Enable or disable the Pasteboard History.</p>
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
        <h4 class="documentation-section">Fields</h4>
          <section id="enabled">
            <a name="//apple_ref/cpp/Field/enabled" class="dashAnchor"></a>
            <h5><a href="#enabled">enabled</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.pasteboard.history.enabled &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Enable or disable the Pasteboard History.</p>
</td>
              </tr>
            </table>
          </section>
