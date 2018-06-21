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
      <h1><a href="cp.ui.notifier.md">docs</a> &raquo; cp.ui.notifier</h1>
      <p>Supports long-lived 'AX' notifiers. Configure the application to watch, the
function that provides the <code>axuielement</code> and then register for the type of
notification to watch, along with a function that will get triggered.</p>
<p>For example:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">notifier</span> <span class="o">=</span> <span class="nb">require</span><span class="p">(</span><span class="s2">&quot;cp.ui.notifier&quot;</span><span class="p">)</span>
<span class="kd">local</span> <span class="kr">function</span> <span class="nf">finder</span><span class="p">()</span> <span class="p">...</span> <span class="kr">end</span> <span class="c1">-- returns the axuielement</span>
<span class="kd">local</span> <span class="n">o</span> <span class="o">=</span> <span class="n">notifier</span><span class="p">.</span><span class="n">new</span><span class="p">(</span><span class="s2">&quot;com.apple.FinalCut&quot;</span><span class="p">,</span> <span class="n">finder</span><span class="p">)</span>
<span class="n">o</span><span class="p">:</span><span class="n">addWatcher</span><span class="p">(</span><span class="s2">&quot;AXValueChanged&quot;</span><span class="p">,</span> <span class="kr">function</span><span class="p">(</span><span class="n">notifier</span><span class="p">,</span> <span class="n">element</span><span class="p">,</span> <span class="n">notification</span><span class="p">,</span> <span class="n">details</span><span class="p">)</span> <span class="p">...</span> <span class="kr">end</span><span class="p">)</span>
<span class="n">o</span><span class="p">:</span><span class="n">start</span><span class="p">()</span>
</pre></div>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#notifiersForBundleID">notifiersForBundleID</a></li>
          </ul>
        <li>Constructors - API calls which return an object, typically one that offers API methods</li>
          <ul>
            <li><a href="#new">new</a></li>
          </ul>
        <li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
          <ul>
            <li><a href="#isRunning">isRunning</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#addWatcher">addWatcher</a></li>
            <li><a href="#app">app</a></li>
            <li><a href="#bundleID">bundleID</a></li>
            <li><a href="#currentElement">currentElement</a></li>
            <li><a href="#pid">pid</a></li>
            <li><a href="#reset">reset</a></li>
            <li><a href="#start">start</a></li>
            <li><a href="#update">update</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Functions</h4>
          <section id="notifiersForBundleID">
            <a name="//apple_ref/cpp/Function/notifiersForBundleID" class="dashAnchor"></a>
            <h5><a href="#notifiersForBundleID">notifiersForBundleID</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.notifier.notifiersForBundleID(bundleID) -&gt; table of cp.ui.notifier</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the list of <code>cp.ui.notifier</code> instances that have been created for the specified <code>Bundle ID</code>.</p>
<p>Parameters:</p>
<ul>
<li>bundleID          - The application Bundle ID being observed. E.g. "com.apple.FinalCut".</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table of <code>cp.ui.notifier</code> instances.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Constructors</h4>
          <section id="new">
            <a name="//apple_ref/cpp/Constructor/new" class="dashAnchor"></a>
            <h5><a href="#new">new</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.notifier.new(bundleID, elementFinderFn) -&gt; cp.ui.notifier</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new <code>cp.ui.notifier</code> instance with the specified bundle ID and
a function that returns the element being observed.</p>
<p>The function has a signature of <code>function() -&gt; hs._asm.axuielement</code>.
It simply returns the current element being observed, or <code>nil</code> if none is available.
The function will be called multiple times over the life of the notifier.</p>
<p>Parameters:</p>
<ul>
<li>bundleID          - The application Bundle ID being observed. E.g. "com.apple.FinalCut".</li>
<li>elementFinderFn   - The function that will return the <code>axuielement</code> to observe.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A new <code>cp.ui.notifier</code> instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Fields</h4>
          <section id="isRunning">
            <a name="//apple_ref/cpp/Field/isRunning" class="dashAnchor"></a>
            <h5><a href="#isRunning">isRunning</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.notifier.isRunning &lt;cp.prop: boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Indicates if the notifier is currently running.</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Methods</h4>
          <section id="addWatcher">
            <a name="//apple_ref/cpp/Method/addWatcher" class="dashAnchor"></a>
            <h5><a href="#addWatcher">addWatcher</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.notifier:addWatcher(notification, callbackFn) -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Registers a function to get called whenever the specified notification type is triggered
for the current <code>axuielement</code>.</p>
<p>Parameters:</p>
<ul>
<li>notification      - The notification type to watch for (e.g. "AXValueChanged").</li>
<li>callbackFn        - The function to call when the matching notification is happens.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.ui.notifier</code> instance.</li>
</ul>
<p>Notes:</p>
<ul>
<li>The callback function should expect 3 arguments and return none. The arguments passed to the callback will be as follows:
<strong> the <code>hs._asm.axuielement</code> object for the accessibility element which generated the notification.</strong> a string with the notification type.
** A table containing key-value pairs with more information about the notification, if provided. Commonly this will be an empty table.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="app">
            <a name="//apple_ref/cpp/Method/app" class="dashAnchor"></a>
            <h5><a href="#app">app</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.notifier:app() -&gt; hs.application</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the current <code>hs.application</code> instance for the app this notifier tracks.
May be <code>nil</code> if the application is not running.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The running <code>hs.application</code> for the notifier's <code>bundleID</code>, or <code>nil</code>.</li>
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
                <td><code>cp.ui.notifier:bundleID()</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the application 'bundle ID' that this notifier is tracking.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The application 'bundle ID' string (e.g. "com.apple.FinalCut")</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="currentElement">
            <a name="//apple_ref/cpp/Method/currentElement" class="dashAnchor"></a>
            <h5><a href="#currentElement">currentElement</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.notifier:currentElement() -&gt; hs._asm.axuielement</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the current <code>axuielement</code> being observed.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>axuielement</code>, or <code>nil</code> if not available.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="pid">
            <a name="//apple_ref/cpp/Method/pid" class="dashAnchor"></a>
            <h5><a href="#pid">pid</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.notifier:pid() -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the PID for the application being observed, or <code>nil</code> if it's not running.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The PID, or <code>nil</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="reset">
            <a name="//apple_ref/cpp/Method/reset" class="dashAnchor"></a>
            <h5><a href="#reset">reset</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.notifier:reset() -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Resets the notifier</p>
</td>
              </tr>
            </table>
          </section>
          <section id="start">
            <a name="//apple_ref/cpp/Method/start" class="dashAnchor"></a>
            <h5><a href="#start">start</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.notifier:start() -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Stops notifying watchers when events happen.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.ui.notifier</code> instance.</li>
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
                <td><code>cp.ui.notifier:update([force]) -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Updates any watchers to use the current <code>axuielement</code>.</p>
<p>Parameters:</p>
<ul>
<li>force     - If <code>true</code>, the notifier will be updated even if the element has not changed since the last update. Defaults to <code>false</code>.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.ui.notifier</code> instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
