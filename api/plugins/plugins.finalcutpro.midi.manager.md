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
      <h1><a href="plugins.finalcutpro.midi.manager.md">docs</a> &raquo; plugins.finalcutpro.midi.manager</h1>
      <p>MIDI Manager Plugin for Final Cut Pro.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Constants - Useful values which cannot be changed</li>
          <ul>
            <li><a href="#ID">ID</a></li>
          </ul>
        <li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
          <ul>
            <li><a href="#enabled">enabled</a></li>
            <li><a href="#transmitMMC">transmitMMC</a></li>
            <li><a href="#transmitMTC">transmitMTC</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Constants</h4>
          <section id="ID">
            <a name="//apple_ref/cpp/Constant/ID" class="dashAnchor"></a>
            <h5><a href="#ID">ID</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.midi.manager.ID -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Group ID</p>
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
                <td><code>plugins.finalcutpro.midi.manager.enabled &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Enable or disable MIDI Support.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="transmitMMC">
            <a name="//apple_ref/cpp/Field/transmitMMC" class="dashAnchor"></a>
            <h5><a href="#transmitMMC">transmitMMC</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.midi.manager.transmitMMC &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Enable or disable Transmit MMC Support.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="transmitMTC">
            <a name="//apple_ref/cpp/Field/transmitMTC" class="dashAnchor"></a>
            <h5><a href="#transmitMTC">transmitMTC</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.midi.manager.transmitMTC &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Enable or disable Transmit MTC Support.</p>
</td>
              </tr>
            </table>
          </section>
