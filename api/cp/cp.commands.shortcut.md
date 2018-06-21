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
      <h1><a href="cp.commands.shortcut.md">docs</a> &raquo; cp.commands.shortcut</h1>
      <p>Shortcut Commands</p>

      </header>
        <h3>Submodules</h3>
        <ul>
        <li><a href="cp.commands.shortcut.builder.html">cp.commands.shortcut.builder</a></li>
        </ul>
      <h3>API Overview</h3>
      <ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#build">build</a></li>
            <li><a href="#new">new</a></li>
          </ul>
        <li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
          <ul>
            <li><a href="#isEnabled">isEnabled</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#bind">bind</a></li>
            <li><a href="#delete">delete</a></li>
            <li><a href="#disable">disable</a></li>
            <li><a href="#enable">enable</a></li>
            <li><a href="#getKeyCode">getKeyCode</a></li>
            <li><a href="#getModifiers">getModifiers</a></li>
            <li><a href="#trigger">trigger</a></li>
            <li><a href="#unbind">unbind</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Functions</h4>
          <section id="build">
            <a name="//apple_ref/cpp/Function/build" class="dashAnchor"></a>
            <h5><a href="#build">build</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.commands.shortcut.build(receiverFn) -&gt; cp.commands.shortcut.builder</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new shortcut builder.</p>
<p>Parameters:</p>
<ul>
<li><code>receiverFn</code>     - (optional) a function which will get passed the shortcut when the build is complete.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>shortcut.builder</code> which can be used to create the shortcut.</li>
</ul>
<p>Notes:</p>
<ul>
<li><p>If provided, the receiver function will be called when the shortcut has been configured, and passed the new
shortcut. The result of that function will be returned to the next stage.
If no <code>receiverFn</code> is provided, the shortcut will be returned directly.</p>
<p>The builder is additive. You can create a complex keystroke combo by
chaining the shortcut names together.</p>
<p>For example:</p>
<p><code>local myShortcut = shortcut.build():cmd():alt("x")</code></p>
<p>Alternately, provide a <code>receiver</code> function and it will get passed the shortcut instead:</p>
<p><code>shortcut.build(function(shortcut) self._myShortcut = shortcut end):cmd():alt("x")</code></p>
</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="new">
            <a name="//apple_ref/cpp/Function/new" class="dashAnchor"></a>
            <h5><a href="#new">new</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.commands.shortcut.new(modifiers, keyCode) -&gt; shortcut</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new keyboard shortcut, attached to the specified <code>hs.commands.command</code></p>
<p>Parameters:</p>
<ul>
<li><code>modifiers</code>  - The modifiers.</li>
<li><code>keyCode</code>    - The key code.</li>
</ul>
<p>Returns:</p>
<ul>
<li>shortcut - The shortcut that was created.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Fields</h4>
          <section id="isEnabled">
            <a name="//apple_ref/cpp/Field/isEnabled" class="dashAnchor"></a>
            <h5><a href="#isEnabled">isEnabled</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.commands.shortcut:isEnabled &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>If <code>true</code>, the shortcut is enabled.</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Methods</h4>
          <section id="bind">
            <a name="//apple_ref/cpp/Method/bind" class="dashAnchor"></a>
            <h5><a href="#bind">bind</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.commands.shortcut:bind(pressedFn, releasedFn, repeatedFn) -&gt; shortcut</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>This function binds the shortcut to a hotkey, with the specified callback functions for <code>pressedFn</code>, <code>releasedFn</code> and <code>repeatedFn</code>.</p>
<p>Parameters:</p>
<ul>
<li><code>pressedFn</code>  - (optional) If present, this is called when the shortcut combo is pressed.</li>
<li><code>releasedFn</code> - (optional) If present, this is called when the shortcut combo is released.</li>
<li><code>repeatedFn</code> - (optional) If present, this is called when the shortcut combo is repeated.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>self</code></li>
</ul>
<p>Notes:</p>
<ul>
<li>If the shortcut is enabled, the hotkey will also be enabled at this point.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="delete">
            <a name="//apple_ref/cpp/Method/delete" class="dashAnchor"></a>
            <h5><a href="#delete">delete</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.commands.shortcut:delete() -&gt; shortcut</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Deletes a shortcut.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>self</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="disable">
            <a name="//apple_ref/cpp/Method/disable" class="dashAnchor"></a>
            <h5><a href="#disable">disable</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.commands.shortcut:disable() -&gt; shortcut</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>This disables the shortcut. If a hotkey has been bound, it will be disabled also.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>self</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="enable">
            <a name="//apple_ref/cpp/Method/enable" class="dashAnchor"></a>
            <h5><a href="#enable">enable</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.commands.shortcut:enable() -&gt; shortcut</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>This enables the shortcut. If a hotkey has been bound, it will be enabled also.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>self</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="getKeyCode">
            <a name="//apple_ref/cpp/Method/getKeyCode" class="dashAnchor"></a>
            <h5><a href="#getKeyCode">getKeyCode</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.commands.shortcut:getKeyCode() -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a string containing the keycode of the shortcut.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>string</code> containing the keycode of the shortcut.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="getModifiers">
            <a name="//apple_ref/cpp/Method/getModifiers" class="dashAnchor"></a>
            <h5><a href="#getModifiers">getModifiers</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.commands.shortcut:getModifiers() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a table containing the modifiers for a shortcut.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>table</code> containing the modifiers of the shortcut.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="trigger">
            <a name="//apple_ref/cpp/Method/trigger" class="dashAnchor"></a>
            <h5><a href="#trigger">trigger</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.commands.shortcut:trigger() -&gt; shortcut</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>This will trigger the keystroke specified in the shortcut.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>self</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="unbind">
            <a name="//apple_ref/cpp/Method/unbind" class="dashAnchor"></a>
            <h5><a href="#unbind">unbind</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.commands.shortcut:unbind() -&gt; shortcut</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Unbinds a shortcut.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>self</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
