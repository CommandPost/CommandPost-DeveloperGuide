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
      <h1><a href="plugins.core.touchbar.manager.virtual.md">docs</a> &raquo; plugins.core.touchbar.manager.virtual</h1>
      <p>Virtual Touch Bar Manager</p>

      </header>
        <h3>Submodules</h3>
        <ul>
        <li><a href="plugins.core.touchbar.manager.virtual.updateLocationCallback.html">plugins.core.touchbar.manager.virtual.updateLocationCallback</a></li>
        </ul>
      <h3>API Overview</h3>
      <ul>
        <li>Constants - Useful values which cannot be changed</li>
          <ul>
            <li><a href="#LOCATION_DEFAULT_VALUE">LOCATION_DEFAULT_VALUE</a></li>
            <li><a href="#LOCATION_DRAGGABLE">LOCATION_DRAGGABLE</a></li>
            <li><a href="#LOCATION_MOUSE">LOCATION_MOUSE</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#callback">callback</a></li>
            <li><a href="#hide">hide</a></li>
            <li><a href="#show">show</a></li>
            <li><a href="#start">start</a></li>
            <li><a href="#stop">stop</a></li>
            <li><a href="#update">update</a></li>
          </ul>
        <li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
          <ul>
            <li><a href="#enabled">enabled</a></li>
            <li><a href="#isActive">isActive</a></li>
            <li><a href="#lastLocation">lastLocation</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Constants</h4>
          <section id="LOCATION_DEFAULT_VALUE">
            <a name="//apple_ref/cpp/Constant/LOCATION_DEFAULT_VALUE" class="dashAnchor"></a>
            <h5><a href="#LOCATION_DEFAULT_VALUE">LOCATION_DEFAULT_VALUE</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.touchbar.manager.virtual.LOCATION_DEFAULT_VALUE -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Default location value.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="LOCATION_DRAGGABLE">
            <a name="//apple_ref/cpp/Constant/LOCATION_DRAGGABLE" class="dashAnchor"></a>
            <h5><a href="#LOCATION_DRAGGABLE">LOCATION_DRAGGABLE</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.touchbar.manager.virtual.LOCATION_DRAGGABLE -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Location is Draggable.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="LOCATION_MOUSE">
            <a name="//apple_ref/cpp/Constant/LOCATION_MOUSE" class="dashAnchor"></a>
            <h5><a href="#LOCATION_MOUSE">LOCATION_MOUSE</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.touchbar.manager.virtual.LOCATION_MOUSE -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Location is Mouse.</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Functions</h4>
          <section id="callback">
            <a name="//apple_ref/cpp/Function/callback" class="dashAnchor"></a>
            <h5><a href="#callback">callback</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.touchbar.manager.virtual.callback() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Callback Function for the Virtual Touch Bar</p>
<p>Parameters:</p>
<ul>
<li>obj - the touchbarObject the callback is for</li>
<li>message - the message to the callback, either "didEnter" or "didExit"</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="hide">
            <a name="//apple_ref/cpp/Function/hide" class="dashAnchor"></a>
            <h5><a href="#hide">hide</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.touchbar.manager.virtual.hide() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Hide the Virtual Touch Bar</p>
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
          <section id="show">
            <a name="//apple_ref/cpp/Function/show" class="dashAnchor"></a>
            <h5><a href="#show">show</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.touchbar.manager.virtual.show() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Show the Virtual Touch Bar</p>
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
                <td><code>plugins.core.touchbar.manager.virtual.start() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Initialises the Virtual Touch Bar</p>
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
                <td><code>plugins.core.touchbar.manager.virtual.stop() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Stops the Virtual Touch Bar</p>
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
                <td><code>plugins.core.touchbar.manager.virtual.update() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Updates the visibility and location of the Virtual Touch Bar</p>
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
                <td><code>plugins.core.touchbar.manager.virtual.enabled &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Is <code>true</code> if the plugin is enabled.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="isActive">
            <a name="//apple_ref/cpp/Field/isActive" class="dashAnchor"></a>
            <h5><a href="#isActive">isActive</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.touchbar.manager.virtual.isActive &lt;cp.prop: boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Is <code>true</code> if the plugin is enabled and the TouchBar is supported on this OS.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="lastLocation">
            <a name="//apple_ref/cpp/Field/lastLocation" class="dashAnchor"></a>
            <h5><a href="#lastLocation">lastLocation</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.touchbar.manager.virtual.lastLocation &lt;cp.prop: point table&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The last known Virtual Touch Bar Location</p>
</td>
              </tr>
            </table>
          </section>
