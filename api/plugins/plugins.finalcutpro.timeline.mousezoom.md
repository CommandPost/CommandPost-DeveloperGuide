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
      <h1><a href="plugins.finalcutpro.timeline.mousezoom.md">docs</a> &raquo; plugins.finalcutpro.timeline.mousezoom</h1>
      <p>Allows you to zoom in or out of a Final Cut Pro timeline using the mechanical scroll wheel on your mouse or the Touch Pad on the Magic Mouse when holding down the OPTION modifier key.</p>
<p>Special Thanks: Iain Anderson (@funwithstuff) for all his incredible testing!</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Variables - Configurable values</li>
          <ul>
            <li><a href="#customModifier">customModifier</a></li>
            <li><a href="#enabled">enabled</a></li>
            <li><a href="#numberOfTouchDevices">numberOfTouchDevices</a></li>
            <li><a href="#offset">offset</a></li>
            <li><a href="#threshold">threshold</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#findMagicMouses">findMagicMouses</a></li>
            <li><a href="#start">start</a></li>
            <li><a href="#stop">stop</a></li>
            <li><a href="#update">update</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Variables</h4>
          <section id="customModifier">
            <a name="//apple_ref/cpp/Variable/customModifier" class="dashAnchor"></a>
            <h5><a href="#customModifier">customModifier</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.timeline.mousezoom.customModifier &lt;cp.prop: string&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Custom Modifier as string.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="enabled">
            <a name="//apple_ref/cpp/Variable/enabled" class="dashAnchor"></a>
            <h5><a href="#enabled">enabled</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.timeline.mousezoom.enabled &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Toggles the Enable Proxy Menu Icon</p>
</td>
              </tr>
            </table>
          </section>
          <section id="numberOfTouchDevices">
            <a name="//apple_ref/cpp/Variable/numberOfTouchDevices" class="dashAnchor"></a>
            <h5><a href="#numberOfTouchDevices">numberOfTouchDevices</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.timeline.mousezoom.numberOfTouchDevices -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Number of Touch Devices Detected.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="offset">
            <a name="//apple_ref/cpp/Variable/offset" class="dashAnchor"></a>
            <h5><a href="#offset">offset</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.timeline.mousezoom.offset -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Offset Value used in difference calculations.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="threshold">
            <a name="//apple_ref/cpp/Variable/threshold" class="dashAnchor"></a>
            <h5><a href="#threshold">threshold</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.timeline.mousezoom.threshold -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Threshold Value used in difference calculations.</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Functions</h4>
          <section id="findMagicMouses">
            <a name="//apple_ref/cpp/Function/findMagicMouses" class="dashAnchor"></a>
            <h5><a href="#findMagicMouses">findMagicMouses</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.timeline.mousezoom.findMagicMouses() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Find Magic Mouse Devices and adds them to a table.</p>
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
          <section id="start">
            <a name="//apple_ref/cpp/Function/start" class="dashAnchor"></a>
            <h5><a href="#start">start</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.timeline.mousezoom.start() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Enables the ability to zoon a timeline using your mouse scroll wheel and the OPTION modifier key.</p>
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
          <section id="stop">
            <a name="//apple_ref/cpp/Function/stop" class="dashAnchor"></a>
            <h5><a href="#stop">stop</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.timeline.mousezoom.stop() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Disables the ability to zoom a timeline using your mouse scroll wheel and the OPTION modifier key.</p>
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
          <section id="update">
            <a name="//apple_ref/cpp/Function/update" class="dashAnchor"></a>
            <h5><a href="#update">update</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.timeline.mousezoom.update() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks to see whether or not we should enable the timeline zoom watchers.</p>
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
