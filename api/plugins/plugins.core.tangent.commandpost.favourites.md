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
      <h1><a href="plugins.core.tangent.commandpost.favourites.md">docs</a> &raquo; plugins.core.tangent.commandpost.favourites</h1>
      <p>Tangent Favourites.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#clearAction">clearAction</a></li>
            <li><a href="#favourites">favourites</a></li>
            <li><a href="#init">init</a></li>
            <li><a href="#saveAction">saveAction</a></li>
            <li><a href="#updateControls">updateControls</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Functions</h4>
          <section id="clearAction">
            <a name="//apple_ref/cpp/Function/clearAction" class="dashAnchor"></a>
            <h5><a href="#clearAction">clearAction</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.commandpost.favourites.clearAction(buttonID) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Clears an Action from Favourites.</p>
<p>Parameters:</p>
<ul>
<li>buttonID - The button ID you want to clear.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="favourites">
            <a name="//apple_ref/cpp/Function/favourites" class="dashAnchor"></a>
            <h5><a href="#favourites">favourites</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.commandpost.favourites.favourites() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets a table of favourites from file.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table of favourites.</li>
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
                <td><code>plugins.core.tangent.commandpost.favourites.init() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Initialise Module.</p>
<p>Parameters:</p>
<ul>
<li>tangentManager - Tangent Manager Plugin</li>
<li>actionManager - Action Manager Plugin</li>
<li>cpGroup - CommandPost Group</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="saveAction">
            <a name="//apple_ref/cpp/Function/saveAction" class="dashAnchor"></a>
            <h5><a href="#saveAction">saveAction</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.commandpost.favourites.saveAction(buttonID, actionTitle, handlerID, action) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Saves an action to Favourites.</p>
<p>Parameters:</p>
<ul>
<li>buttonID - The button ID as number.</li>
<li>actionTitle - The action title as string.</li>
<li>handlerID - The handler ID as string.</li>
<li>action - The action table.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="updateControls">
            <a name="//apple_ref/cpp/Function/updateControls" class="dashAnchor"></a>
            <h5><a href="#updateControls">updateControls</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.commandpost.favourites.updateControls() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Update Controls</p>
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
