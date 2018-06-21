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
      <h1><a href="plugins.finalcutpro.notifications.manager.md">docs</a> &raquo; plugins.finalcutpro.notifications.manager</h1>
      <p>Notifications Manager Plugin.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Constants - Useful values which cannot be changed</li>
          <ul>
            <li><a href="#manager">manager</a></li>
          </ul>
        <li>Variables - Configurable values</li>
          <ul>
            <li><a href="#watchers">watchers</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#unwatch">unwatch</a></li>
            <li><a href="#watch">watch</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Constants</h4>
          <section id="manager">
            <a name="//apple_ref/cpp/Constant/manager" class="dashAnchor"></a>
            <h5><a href="#manager">manager</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.notifications.manager</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Event Types</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Variables</h4>
          <section id="watchers">
            <a name="//apple_ref/cpp/Variable/watchers" class="dashAnchor"></a>
            <h5><a href="#watchers">watchers</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.notifications.manager.watchers -&gt; watcher</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Watchers</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Functions</h4>
          <section id="unwatch">
            <a name="//apple_ref/cpp/Function/unwatch" class="dashAnchor"></a>
            <h5><a href="#unwatch">unwatch</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.notifications.manager.unwatch(id) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Start Watchers</p>
<p>Parameters:</p>
<ul>
<li>id - The ID of the watcher to unwatch as string</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="watch">
            <a name="//apple_ref/cpp/Function/watch" class="dashAnchor"></a>
            <h5><a href="#watch">watch</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.notifications.manager.watch(event) -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Start Watchers</p>
<p>Parameters:</p>
<ul>
<li>events - Events to watch</li>
</ul>
<p>Returns:</p>
<ul>
<li>The ID of the watcher as string</li>
</ul>
</td>
              </tr>
            </table>
          </section>
