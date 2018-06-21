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
      <h1><a href="plugins.finalcutpro.menu.menuaction.md">docs</a> &raquo; plugins.finalcutpro.menu.menuaction</h1>
      <p>A <code>action</code> which will trigger an Final Cut Pro menu with a matching path, if available/enabled.
Registers itself with the <code>plugins.core.actions.actionmanager</code>.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#actionId">actionId</a></li>
            <li><a href="#execute">execute</a></li>
            <li><a href="#id">id</a></li>
            <li><a href="#init">init</a></li>
            <li><a href="#onChoices">onChoices</a></li>
            <li><a href="#reload">reload</a></li>
            <li><a href="#reset">reset</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Functions</h4>
          <section id="actionId">
            <a name="//apple_ref/cpp/Function/actionId" class="dashAnchor"></a>
            <h5><a href="#actionId">actionId</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.menu.menuaction.actionId(params) -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the action ID from the parameters table.</p>
<p>Parameters:</p>
<ul>
<li>params - Parameters table.</li>
</ul>
<p>Returns:</p>
<ul>
<li>Action ID as string.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="execute">
            <a name="//apple_ref/cpp/Function/execute" class="dashAnchor"></a>
            <h5><a href="#execute">execute</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.menu.menuaction.execute(action) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Executes the action with the provided parameters.</p>
<p>Parameters:</p>
<ul>
<li><p><code>action</code>  - A table of parameters, matching the following:</p>
<ul>
<li><code>group</code>   - The Command Group ID</li>
<li><code>id</code>      - The specific Command ID within the group.</li>
</ul>
</li>
<li><p><code>true</code> if the action was executed successfully.</p>
</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="id">
            <a name="//apple_ref/cpp/Function/id" class="dashAnchor"></a>
            <h5><a href="#id">id</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.menu.menuaction.id() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the menu ID</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>a string contains the menu ID</li>
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
                <td><code>plugins.finalcutpro.menu.menuaction.init(actionmanager) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Initialises the Menu Action plugin</p>
<p>Parameters:</p>
<ul>
<li><code>actionmanager</code> - the Action Manager plugin</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="onChoices">
            <a name="//apple_ref/cpp/Function/onChoices" class="dashAnchor"></a>
            <h5><a href="#onChoices">onChoices</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.menu.menuaction.onChoices(choices) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Add choices to the chooser.</p>
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
          <section id="reload">
            <a name="//apple_ref/cpp/Function/reload" class="dashAnchor"></a>
            <h5><a href="#reload">reload</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.menu.menuaction.reload() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Reloads the choices.</p>
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
          <section id="reset">
            <a name="//apple_ref/cpp/Function/reset" class="dashAnchor"></a>
            <h5><a href="#reset">reset</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.menu.menuaction.reset() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Resets the handler.</p>
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
