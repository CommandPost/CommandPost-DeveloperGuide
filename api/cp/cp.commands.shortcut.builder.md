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
      <h1><a href="cp.commands.shortcut.builder.md">docs</a> &raquo; cp.commands.shortcut.builder</h1>
      <p>Shortcut Commands Builder Module.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#add">add</a></li>
            <li><a href="#new">new</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Methods</h4>
          <section id="add">
            <a name="//apple_ref/cpp/Method/add" class="dashAnchor"></a>
            <h5><a href="#add">add</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.commands.shortcut.builder:add(modifier, [keyCode]) -&gt; shortcut/command</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Adds the specified modifier to the set. If a <code>keyCode</code> is provided,
no more modifiers can be added and the original <code>command</code> is returned instead.
Otherwise, <code>self</code> is returned and further modifiers can be added.</p>
<p>Parameters:</p>
<ul>
<li>modifier - (optional) The modifier that was added.</li>
<li>keyCode  - (optional) The key code being modified.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>self</code> if no <code>keyCode</code> is provided, or the original <code>command</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="new">
            <a name="//apple_ref/cpp/Method/new" class="dashAnchor"></a>
            <h5><a href="#new">new</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.commands.shortcut.builder.new([receiverFn]) -&gt; builder</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new shortcut builder. If provided, the receiver function
will be called when the shortcut has been configured, and passed the new
shortcut. The result of that function will be returned to the next stage.
If no <code>receiverFn</code> is provided, the shortcut will be returned directly.</p>
<p>Parameters:</p>
<ul>
<li><code>receiverFn</code> - The function which will be called with the new shortcut, when built.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The builder instance</li>
</ul>
</td>
              </tr>
            </table>
          </section>
