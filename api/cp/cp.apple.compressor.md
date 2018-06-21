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
      <h1><a href="cp.apple.compressor.md">docs</a> &raquo; cp.apple.compressor</h1>
      <p>Represents the Compressor application, providing functions that allow different tasks to be accomplished.</p>

      </header>
        <h3>Submodules</h3>
        <ul>
        <li><a href="cp.apple.compressor.app.html">cp.apple.compressor.app</a></li>
        </ul>
      <h3>API Overview</h3>
      <ul>
        <li>Constants - Useful values which cannot be changed</li>
          <ul>
            <li><a href="#ALLOWED_IMPORT_ALL_EXTENSIONS">ALLOWED_IMPORT_ALL_EXTENSIONS</a></li>
            <li><a href="#ALLOWED_IMPORT_AUDIO_EXTENSIONS">ALLOWED_IMPORT_AUDIO_EXTENSIONS</a></li>
            <li><a href="#ALLOWED_IMPORT_IMAGE_EXTENSIONS">ALLOWED_IMPORT_IMAGE_EXTENSIONS</a></li>
            <li><a href="#ALLOWED_IMPORT_VIDEO_EXTENSIONS">ALLOWED_IMPORT_VIDEO_EXTENSIONS</a></li>
            <li><a href="#BUNDLE_ID">BUNDLE_ID</a></li>
            <li><a href="#EARLIEST_SUPPORTED_VERSION">EARLIEST_SUPPORTED_VERSION</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#bundleID">bundleID</a></li>
            <li><a href="#getVersion">getVersion</a></li>
            <li><a href="#hide">hide</a></li>
            <li><a href="#launch">launch</a></li>
            <li><a href="#notifier">notifier</a></li>
            <li><a href="#path">path</a></li>
            <li><a href="#quit">quit</a></li>
            <li><a href="#restart">restart</a></li>
            <li><a href="#show">show</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Constants</h4>
          <section id="ALLOWED_IMPORT_ALL_EXTENSIONS">
            <a name="//apple_ref/cpp/Constant/ALLOWED_IMPORT_ALL_EXTENSIONS" class="dashAnchor"></a>
            <h5><a href="#ALLOWED_IMPORT_ALL_EXTENSIONS">ALLOWED_IMPORT_ALL_EXTENSIONS</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.compressor.ALLOWED_IMPORT_ALL_EXTENSIONS</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Table of all file extensions Final Cut Pro can import.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="ALLOWED_IMPORT_AUDIO_EXTENSIONS">
            <a name="//apple_ref/cpp/Constant/ALLOWED_IMPORT_AUDIO_EXTENSIONS" class="dashAnchor"></a>
            <h5><a href="#ALLOWED_IMPORT_AUDIO_EXTENSIONS">ALLOWED_IMPORT_AUDIO_EXTENSIONS</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.compressor.ALLOWED_IMPORT_AUDIO_EXTENSIONS</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Table of audio file extensions Final Cut Pro can import.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="ALLOWED_IMPORT_IMAGE_EXTENSIONS">
            <a name="//apple_ref/cpp/Constant/ALLOWED_IMPORT_IMAGE_EXTENSIONS" class="dashAnchor"></a>
            <h5><a href="#ALLOWED_IMPORT_IMAGE_EXTENSIONS">ALLOWED_IMPORT_IMAGE_EXTENSIONS</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.compressor.ALLOWED_IMPORT_IMAGE_EXTENSIONS</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Table of image file extensions Final Cut Pro can import.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="ALLOWED_IMPORT_VIDEO_EXTENSIONS">
            <a name="//apple_ref/cpp/Constant/ALLOWED_IMPORT_VIDEO_EXTENSIONS" class="dashAnchor"></a>
            <h5><a href="#ALLOWED_IMPORT_VIDEO_EXTENSIONS">ALLOWED_IMPORT_VIDEO_EXTENSIONS</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.compressor.ALLOWED_IMPORT_VIDEO_EXTENSIONS</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Table of video file extensions Final Cut Pro can import.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="BUNDLE_ID">
            <a name="//apple_ref/cpp/Constant/BUNDLE_ID" class="dashAnchor"></a>
            <h5><a href="#BUNDLE_ID">BUNDLE_ID</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.compressor.BUNDLE_ID</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Compressor's Bundle ID</p>
</td>
              </tr>
            </table>
          </section>
          <section id="EARLIEST_SUPPORTED_VERSION">
            <a name="//apple_ref/cpp/Constant/EARLIEST_SUPPORTED_VERSION" class="dashAnchor"></a>
            <h5><a href="#EARLIEST_SUPPORTED_VERSION">EARLIEST_SUPPORTED_VERSION</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.compressor.EARLIEST_SUPPORTED_VERSION <semver></code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The earliest version this API supports.</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Methods</h4>
          <section id="bundleID">
            <a name="//apple_ref/cpp/Method/bundleID" class="dashAnchor"></a>
            <h5><a href="#bundleID">bundleID</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.compressor:bundleID() -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the Compressor Bundle ID</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A string of the Compressor Bundle ID</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="getVersion">
            <a name="//apple_ref/cpp/Method/getVersion" class="dashAnchor"></a>
            <h5><a href="#getVersion">getVersion</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.compressor:getVersion() -&gt; string | nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Version of Compressor</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>Version as string or nil if an error occurred</li>
</ul>
<p>Notes:</p>
<ul>
<li>If Compressor is running it will get the version of the active Compressor application, otherwise, it will use hs.application.infoForBundleID() to find the version.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="hide">
            <a name="//apple_ref/cpp/Method/hide" class="dashAnchor"></a>
            <h5><a href="#hide">hide</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.compressor:hide() -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Hides Compressor</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The compressor instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="launch">
            <a name="//apple_ref/cpp/Method/launch" class="dashAnchor"></a>
            <h5><a href="#launch">launch</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.compressor:launch([waitSeconds]) -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Launches Compressor, or brings it to the front if it was already running.</p>
<p>Parameters:</p>
<ul>
<li>waitSeconds      - if provided, we will wait for up to the specified seconds for the launch to complete.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if Compressor was either launched or focused, otherwise false (e.g. if Compressor doesn't exist)</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="notifier">
            <a name="//apple_ref/cpp/Method/notifier" class="dashAnchor"></a>
            <h5><a href="#notifier">notifier</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.compressor:notifier() -&gt; cp.ui.notifier</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a notifier that is tracking the application UI element. It has already been started.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The notifier.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="path">
            <a name="//apple_ref/cpp/Method/path" class="dashAnchor"></a>
            <h5><a href="#path">path</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.compressor:path() -&gt; string or nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Path to Compressor Application</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A string containing Compressor's filesystem path, or <code>nil</code> if the bundle identifier could not be located</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="quit">
            <a name="//apple_ref/cpp/Method/quit" class="dashAnchor"></a>
            <h5><a href="#quit">quit</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.compressor:quit([waitSeconds]) -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Quits Compressor</p>
<p>Parameters:</p>
<ul>
<li>waitSeconds  - if provided, we will wait for the specified time for the quit to complete before returning.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>compressor</code> instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="restart">
            <a name="//apple_ref/cpp/Method/restart" class="dashAnchor"></a>
            <h5><a href="#restart">restart</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.compressor:restart([waitSeconds]) -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Restart the application.</p>
<p>Parameters:</p>
<ul>
<li>waitSeconds  - if provided, we will wait for up to the specified seconds for the restart to complete before returning.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the application was running and restarted successfully.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="show">
            <a name="//apple_ref/cpp/Method/show" class="dashAnchor"></a>
            <h5><a href="#show">show</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.compressor:show() -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Activate Compressor</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The compressor instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
