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
      <h1><a href="plugins.core.commands.actions.md">docs</a> &raquo; plugins.core.commands.actions</h1>
      <p>An <code>action</code> which will execute a command with matching group/id values.
Registers itself with the <code>core.action.manager</code>.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#execute">execute</a></li>
            <li><a href="#getId">getId</a></li>
            <li><a href="#init">init</a></li>
            <li><a href="#onChoices">onChoices</a></li>
            <li><a href="#reset">reset</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Functions</h4>
          <section id="execute">
            <a name="//apple_ref/cpp/Function/execute" class="dashAnchor"></a>
            <h5><a href="#execute">execute</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.commands.actions.execute(action) -&gt; boolean</code></td>
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
<li><code>action</code> - A table representing the action, matching the following:<ul>
<li><code>id</code> - The specific Command ID within the group.</li>
</ul>
</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the action was executed successfully.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="getId">
            <a name="//apple_ref/cpp/Function/getId" class="dashAnchor"></a>
            <h5><a href="#getId">getId</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.commands.actions.getId(action) -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets an ID from an action table</p>
<p>Parameters:</p>
<ul>
<li><code>action</code>      - The action table.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The ID as a string.</li>
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
                <td><code>plugins.core.commands.actions.init(actionmanager, cmds) -&gt; none</code></td>
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
<li><code>actionmanager</code> - The Action Manager Plugin</li>
<li><code>cmds</code> - The Commands Plugin.</li>
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
                <td><code>plugins.core.commands.actions.onChoices(choices) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Adds available choices to the  selection.</p>
<p>Parameters:</p>
<ul>
<li><code>choices</code>     - The <code>cp.choices</code> to add choices to.</li>
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
                <td><code>plugins.core.commands.actions.reset() -&gt; nothing</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Resets the set of choices.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>Nothing</li>
</ul>
</td>
              </tr>
            </table>
          </section>
