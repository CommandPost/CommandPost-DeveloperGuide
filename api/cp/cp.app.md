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
      <h1><a href="cp.app.md">docs</a> &raquo; cp.app</h1>
      <p>This class assists with working with macOS apps. It provides functions for
finding, checking the running status, version number, path, and many other
values related to an application. It also provides support for launching,
quitting, and other activities related to applications.</p>
<p>This extension differs from the <code>hs.application</code> extension in several ways:</p>
<ul>
<li><code>cp.app</code> instances are long-lived. You request it once and it will stay up-to-date even if the app quits.</li>
<li>It makes extensive use of <code>cp.prop</code>, so you can <code>watch</code> many most properties of the app and get live notifications when they change.</li>
</ul>

      </header>
        <h3>Submodules</h3>
        <ul>
        <li><a href="cp.app.menu.html">cp.app.menu</a></li>
        <li><a href="cp.app.prefs.html">cp.app.prefs</a></li>
        </ul>
      <h3>API Overview</h3>
      <ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#apps">apps</a></li>
            <li><a href="#bundleIDs">bundleIDs</a></li>
          </ul>
        <li>Constructors - API calls which return an object, typically one that offers API methods</li>
          <ul>
            <li><a href="#forBundleID">forBundleID</a></li>
          </ul>
        <li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
          <ul>
            <li><a href="#frontmostApp">frontmostApp</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#bestSupportedLocale">bestSupportedLocale</a></li>
            <li><a href="#bundleID">bundleID</a></li>
            <li><a href="#hide">hide</a></li>
            <li><a href="#isSupportedLocale">isSupportedLocale</a></li>
            <li><a href="#launch">launch</a></li>
            <li><a href="#menu">menu</a></li>
            <li><a href="#notifier">notifier</a></li>
            <li><a href="#quit">quit</a></li>
            <li><a href="#restart">restart</a></li>
            <li><a href="#show">show</a></li>
            <li><a href="#update">update</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Functions</h4>
          <section id="apps">
            <a name="//apple_ref/cpp/Function/apps" class="dashAnchor"></a>
            <h5><a href="#apps">apps</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.app.apps() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a list of all apps that have been requested via <a href="#forBundleID">forBundleID</a>, in no particular order.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A list of <code>cp.app</code> instances.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="bundleIDs">
            <a name="//apple_ref/cpp/Function/bundleIDs" class="dashAnchor"></a>
            <h5><a href="#bundleIDs">bundleIDs</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.app.bundleIDs() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a list of Bundle IDs which have been requested via <a href="#forBundleID">forBundleID</a>.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A list of Bundle IDs.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Constructors</h4>
          <section id="forBundleID">
            <a name="//apple_ref/cpp/Constructor/forBundleID" class="dashAnchor"></a>
            <h5><a href="#forBundleID">forBundleID</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.app.forBundleID(bundleID)</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the <code>cp.app</code> for the specified Bundle ID. If the app has already been created,
the same instance of <code>cp.app</code> will be returned on subsequent calls.</p>
<p>The Bundle ID</p>
<p>Parameters:</p>
<ul>
<li>bundleID      - The application bundle ID to find the app for.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.app</code> for the bundle.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Fields</h4>
          <section id="frontmostApp">
            <a name="//apple_ref/cpp/Field/frontmostApp" class="dashAnchor"></a>
            <h5><a href="#frontmostApp">frontmostApp</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.app.frontmostApp &lt;cp.prop: cp.app; read-only; live&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the most recent 'registered' app that was active, other than CommandPost itself.</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Methods</h4>
          <section id="bestSupportedLocale">
            <a name="//apple_ref/cpp/Method/bestSupportedLocale" class="dashAnchor"></a>
            <h5><a href="#bestSupportedLocale">bestSupportedLocale</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.app:bestSupportedLocale(locale) -&gt; cp.i18n.localeID or nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Finds the closest match for the specified locale. The returned locale
will be in the same language as the provided locale, and as close a match as possible with the region and script.</p>
<p>Parameters:</p>
<ul>
<li>locale    - The local to match</li>
</ul>
<p>Returns:</p>
<ul>
<li>The closest supported locale or <code>nil</code> if none are available in the language.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="bundleID">
            <a name="//apple_ref/cpp/Method/bundleID" class="dashAnchor"></a>
            <h5><a href="#bundleID">bundleID</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.app:bundleID() -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the Bundle ID for the app.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The Bundle ID.</li>
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
                <td><code>cp.app:hide() -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Hides the application, if it's currently running.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.app</code> instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="isSupportedLocale">
            <a name="//apple_ref/cpp/Method/isSupportedLocale" class="dashAnchor"></a>
            <h5><a href="#isSupportedLocale">isSupportedLocale</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.app:isSupportedLocale(locale) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks if the specified locale is supported. The <code>locale</code> can
be either a string with the locale code (eg. "en_AU") or a
<code>cp.i18n.localeID</code>.</p>
<p>Parameters:</p>
<ul>
<li>locale    - The locale code string or <code>localeID</code> to check.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if it is supported, otherwise <code>false</code>.</li>
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
                <td><code>cp.app:launch(waitSeconds) -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Launches the application, or brings it to the front if it was already running.</p>
<p>Parameters:</p>
<ul>
<li><code>waitSeconds</code>    - If povided, the number of seconds to wait until the launch completes. If <code>nil</code>, it will return immediately.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.app</code> instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="menu">
            <a name="//apple_ref/cpp/Method/menu" class="dashAnchor"></a>
            <h5><a href="#menu">menu</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.app:menu() -&gt; cp.app.menu</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the main <code>menu</code> for the application.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.app.menu</code> for the <code>cp.app</code> instance.</li>
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
                <td><code>cp.app:notifier() -&gt; cp.ui.notifier</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a <code>notifier</code> that is tracking the application UI element. It has already been started.</p>
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
          <section id="quit">
            <a name="//apple_ref/cpp/Method/quit" class="dashAnchor"></a>
            <h5><a href="#quit">quit</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.app:quit(waitSeconds) -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Asks the application to quit, if it's running. The app may not have actually quit after this
function runs, even if <code>true</code> is returned. The application may take some time, or may be prompting
the user for input, etc.</p>
<p>Parameters:</p>
<ul>
<li><code>waitSeconds</code>    - If povided, the number of seconds to wait until the quit completes. If <code>nil</code>, it will return immediately.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.app</code> instance.</li>
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
                <td><code>cp.app:restart(waitSeconds) -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Restart the application, if currently running. If not, no action is taken.</p>
<p>Parameters:</p>
<ul>
<li><code>waitSeconds</code>    - If povided, the number of seconds to wait until the quit completes. If <code>nil</code>, it will return immediately.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.app</code> instance.</li>
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
                <td><code>cp.app:show() -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Ensure the app is onscreen if it is currently running.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.app</code> instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="update">
            <a name="//apple_ref/cpp/Method/update" class="dashAnchor"></a>
            <h5><a href="#update">update</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.app:update() -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Updates the app, triggering any watchers if values have changed.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.app</code> instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
