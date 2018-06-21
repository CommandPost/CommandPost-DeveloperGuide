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
      <h1><a href="plugins.finalcutpro.touchbar.virtual.md">docs</a> &raquo; plugins.finalcutpro.touchbar.virtual</h1>
      <p>Virtual Touch Bar Plugin.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Constants - Useful values which cannot be changed</li>
          <ul>
            <li><a href="#LOCATION_TIMELINE">LOCATION_TIMELINE</a></li>
            <li><a href="#VISIBILITY_ALWAYS">VISIBILITY_ALWAYS</a></li>
            <li><a href="#VISIBILITY_DEFAULT">VISIBILITY_DEFAULT</a></li>
            <li><a href="#VISIBILITY_FCP">VISIBILITY_FCP</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#updateLocation">updateLocation</a></li>
          </ul>
        <li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
          <ul>
            <li><a href="#enabled">enabled</a></li>
            <li><a href="#location">location</a></li>
            <li><a href="#visibility">visibility</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Constants</h4>
          <section id="LOCATION_TIMELINE">
            <a name="//apple_ref/cpp/Constant/LOCATION_TIMELINE" class="dashAnchor"></a>
            <h5><a href="#LOCATION_TIMELINE">LOCATION_TIMELINE</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.touchbar.virtual.LOCATION_TIMELINE -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Virtual Touch Bar is displayed in the top centre of the Final Cut Pro timeline</p>
</td>
              </tr>
            </table>
          </section>
          <section id="VISIBILITY_ALWAYS">
            <a name="//apple_ref/cpp/Constant/VISIBILITY_ALWAYS" class="dashAnchor"></a>
            <h5><a href="#VISIBILITY_ALWAYS">VISIBILITY_ALWAYS</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.touchbar.virtual.VISIBILITY_ALWAYS -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Virtual Touch Bar is Always Visible</p>
</td>
              </tr>
            </table>
          </section>
          <section id="VISIBILITY_DEFAULT">
            <a name="//apple_ref/cpp/Constant/VISIBILITY_DEFAULT" class="dashAnchor"></a>
            <h5><a href="#VISIBILITY_DEFAULT">VISIBILITY_DEFAULT</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.touchbar.virtual.VISIBILITY_DEFAULT -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The default visibility.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="VISIBILITY_FCP">
            <a name="//apple_ref/cpp/Constant/VISIBILITY_FCP" class="dashAnchor"></a>
            <h5><a href="#VISIBILITY_FCP">VISIBILITY_FCP</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.touchbar.virtual.VISIBILITY_FCP -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Virtual Touch Bar is only visible when Final Cut Pro is active.</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Functions</h4>
          <section id="updateLocation">
            <a name="//apple_ref/cpp/Function/updateLocation" class="dashAnchor"></a>
            <h5><a href="#updateLocation">updateLocation</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.touchbar.virtual.updateLocation() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Updates the Location of the Virtual Touch Bar</p>
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
                <td><code>plugins.finalcutpro.touchbar.virtual.enabled &lt;cp.prop: boolean&gt;</code></td>
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
          <section id="location">
            <a name="//apple_ref/cpp/Field/location" class="dashAnchor"></a>
            <h5><a href="#location">location</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.touchbar.virtual.location &lt;cp.prop: string&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The Virtual Touch Bar Location Setting</p>
</td>
              </tr>
            </table>
          </section>
          <section id="visibility">
            <a name="//apple_ref/cpp/Field/visibility" class="dashAnchor"></a>
            <h5><a href="#visibility">visibility</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.touchbar.virtual.visibility &lt;cp.prop: string&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>When should the Virtual Touch Bar be visible?</p>
</td>
              </tr>
            </table>
          </section>
