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
      <h1><a href="plugins.core.disk.automount.md">docs</a> &raquo; plugins.core.disk.automount</h1>
      <p>Automatic Disk Mounting &amp; Unmounting.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Variables - Configurable values</li>
          <ul>
            <li><a href="#autoMountOnAC">autoMountOnAC</a></li>
            <li><a href="#autoUnmountOnBattery">autoUnmountOnBattery</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#mountPhysicalDrives">mountPhysicalDrives</a></li>
            <li><a href="#unmountPhysicalDrives">unmountPhysicalDrives</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Variables</h4>
          <section id="autoMountOnAC">
            <a name="//apple_ref/cpp/Variable/autoMountOnAC" class="dashAnchor"></a>
            <h5><a href="#autoMountOnAC">autoMountOnAC</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.disk.automount.autoMountOnAC &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Automatically mount on connection to mains power.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="autoUnmountOnBattery">
            <a name="//apple_ref/cpp/Variable/autoUnmountOnBattery" class="dashAnchor"></a>
            <h5><a href="#autoUnmountOnBattery">autoUnmountOnBattery</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.disk.automount.autoUnmountOnBattery &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Automatically Unmount on disconnection from battery.</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Functions</h4>
          <section id="mountPhysicalDrives">
            <a name="//apple_ref/cpp/Function/mountPhysicalDrives" class="dashAnchor"></a>
            <h5><a href="#mountPhysicalDrives">mountPhysicalDrives</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.disk.automount.mountPhysicalDrives() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Mount Physical Drives</p>
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
          <section id="unmountPhysicalDrives">
            <a name="//apple_ref/cpp/Function/unmountPhysicalDrives" class="dashAnchor"></a>
            <h5><a href="#unmountPhysicalDrives">unmountPhysicalDrives</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.disk.automount.unmountPhysicalDrives() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Unmount Physical Drives</p>
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
