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
      <h1><a href="plugins.finalcutpro.console.font.md">docs</a> &raquo; plugins.finalcutpro.console.font</h1>
      <p>Final Cut Pro Font Console</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Constants - Useful values which cannot be changed</li>
          <ul>
            <li><a href="#FILE_NAME">FILE_NAME</a></li>
            <li><a href="#FOLDER_NAME">FOLDER_NAME</a></li>
            <li><a href="#FONT_EXTENSIONS">FONT_EXTENSIONS</a></li>
            <li><a href="#IGNORE_FONTS">IGNORE_FONTS</a></li>
            <li><a href="#RENAME_FONTS">RENAME_FONTS</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#deleteCache">deleteCache</a></li>
            <li><a href="#getRunningFonts">getRunningFonts</a></li>
            <li><a href="#onActivate">onActivate</a></li>
            <li><a href="#show">show</a></li>
          </ul>
        <li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
          <ul>
            <li><a href="#cachedFonts">cachedFonts</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Constants</h4>
          <section id="FILE_NAME">
            <a name="//apple_ref/cpp/Constant/FILE_NAME" class="dashAnchor"></a>
            <h5><a href="#FILE_NAME">FILE_NAME</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.console.font.FILE_NAME -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>File name of settings file.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="FOLDER_NAME">
            <a name="//apple_ref/cpp/Constant/FOLDER_NAME" class="dashAnchor"></a>
            <h5><a href="#FOLDER_NAME">FOLDER_NAME</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.console.font.FOLDER_NAME -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Folder Name where settings file is contained.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="FONT_EXTENSIONS">
            <a name="//apple_ref/cpp/Constant/FONT_EXTENSIONS" class="dashAnchor"></a>
            <h5><a href="#FONT_EXTENSIONS">FONT_EXTENSIONS</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.console.font.FONT_EXTENSIONS -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Table of support font file extensions.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="IGNORE_FONTS">
            <a name="//apple_ref/cpp/Constant/IGNORE_FONTS" class="dashAnchor"></a>
            <h5><a href="#IGNORE_FONTS">IGNORE_FONTS</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.console.font.IGNORE_FONTS -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Fonts to ignore as they're used internally by Final Cut Pro or macOS.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="RENAME_FONTS">
            <a name="//apple_ref/cpp/Constant/RENAME_FONTS" class="dashAnchor"></a>
            <h5><a href="#RENAME_FONTS">RENAME_FONTS</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.console.font.RENAME_FONTS -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Special Fonts that appear to have a different name in Final Cut Pro than they do in Font Book.</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Functions</h4>
          <section id="deleteCache">
            <a name="//apple_ref/cpp/Function/deleteCache" class="dashAnchor"></a>
            <h5><a href="#deleteCache">deleteCache</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.console.font.deleteCache() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Deletes the cache file.</p>
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
          <section id="getRunningFonts">
            <a name="//apple_ref/cpp/Function/getRunningFonts" class="dashAnchor"></a>
            <h5><a href="#getRunningFonts">getRunningFonts</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.console.font.getRunningFonts() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Shows the Final Cut Pro Console.</p>
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
          <section id="onActivate">
            <a name="//apple_ref/cpp/Function/onActivate" class="dashAnchor"></a>
            <h5><a href="#onActivate">onActivate</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.console.font.onActivate() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Handles Console Activations.</p>
<p>Parameters:</p>
<ul>
<li>handler - Handler instance.</li>
<li>action - Action table.</li>
<li>text - Selected text from the Console.</li>
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
                <td><code>plugins.finalcutpro.console.font.show() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Shows the Font Console.</p>
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
          <section id="cachedFonts">
            <a name="//apple_ref/cpp/Field/cachedFonts" class="dashAnchor"></a>
            <h5><a href="#cachedFonts">cachedFonts</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.console.font.cachedFonts &lt;cp.prop: table | nil&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Table of cached fonts.</p>
</td>
              </tr>
            </table>
          </section>
