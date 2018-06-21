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
      <h1><a href="plugins.finalcutpro.notifications.prowl.md">docs</a> &raquo; plugins.finalcutpro.notifications.prowl</h1>
      <p>Prowl Notifications Plugin.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#init">init</a></li>
            <li><a href="#sendNotification">sendNotification</a></li>
            <li><a href="#update">update</a></li>
            <li><a href="#validateAPIKey">validateAPIKey</a></li>
          </ul>
        <li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
          <ul>
            <li><a href="#apiKey">apiKey</a></li>
            <li><a href="#apiValidated">apiValidated</a></li>
            <li><a href="#enabled">enabled</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Functions</h4>
          <section id="init">
            <a name="//apple_ref/cpp/Function/init" class="dashAnchor"></a>
            <h5><a href="#init">init</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.notifications.prowl.init() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Initialises the plugin.</p>
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
          <section id="sendNotification">
            <a name="//apple_ref/cpp/Function/sendNotification" class="dashAnchor"></a>
            <h5><a href="#sendNotification">sendNotification</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.notifications.prowl.sendNotification(message, [title]) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Sends a notification.</p>
<p>Parameters:</p>
<ul>
<li>message - The message you want to send as a string.</li>
<li>[title] - An optional Title for the message as a string.</li>
</ul>
<p>Returns:</p>
<ul>
<li>success - <code>true</code> if successful otherwise <code>false</code></li>
<li>errorMessage - a string containing any error messages</li>
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
                <td><code>plugins.finalcutpro.notifications.prowl.update() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Enables or disables Prowl Notifications depending on the user's preferences.</p>
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
          <section id="validateAPIKey">
            <a name="//apple_ref/cpp/Function/validateAPIKey" class="dashAnchor"></a>
            <h5><a href="#validateAPIKey">validateAPIKey</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.notifications.prowl.validateAPIKey(key) -&gt; success, errorMessage</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Validates a Growl API Key</p>
<p>Parameters:</p>
<ul>
<li>key - The API key as string</li>
</ul>
<p>Returns:</p>
<ul>
<li>success - <code>true</code> if successful otherwise <code>false</code></li>
<li>errorMessage - a string containing any error messages</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Fields</h4>
          <section id="apiKey">
            <a name="//apple_ref/cpp/Field/apiKey" class="dashAnchor"></a>
            <h5><a href="#apiKey">apiKey</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.notifications.prowl.apiKey &lt;cp.prop: string&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Prowl API Key</p>
</td>
              </tr>
            </table>
          </section>
          <section id="apiValidated">
            <a name="//apple_ref/cpp/Field/apiValidated" class="dashAnchor"></a>
            <h5><a href="#apiValidated">apiValidated</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.notifications.prowl.apiValidated &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Whether or not the API key has been validated.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="enabled">
            <a name="//apple_ref/cpp/Field/enabled" class="dashAnchor"></a>
            <h5><a href="#enabled">enabled</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.notifications.prowl.enabled &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Whether or not the plugin has been enabled.</p>
</td>
              </tr>
            </table>
          </section>
