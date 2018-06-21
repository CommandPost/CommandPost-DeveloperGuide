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
      <h1><a href="plugins.finder.window.md">docs</a> &raquo; plugins.finder.window</h1>
      <p>Handy tools for Windows Management in macOS.</p>
<p>Inspired by <a href="http://www.hammerspoon.org/Spoons/WinWin.html">WinWin</a> for <a href="http://www.hammerspoon.org/">Hammerspoon</a>.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Variables - Configurable values</li>
          <ul>
            <li><a href="#gridparts">gridparts</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#centerCursor">centerCursor</a></li>
            <li><a href="#grid">grid</a></li>
            <li><a href="#hints">hints</a></li>
            <li><a href="#moveAndResize">moveAndResize</a></li>
            <li><a href="#moveToScreen">moveToScreen</a></li>
            <li><a href="#stepMove">stepMove</a></li>
            <li><a href="#stepResize">stepResize</a></li>
            <li><a href="#undo">undo</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Variables</h4>
          <section id="gridparts">
            <a name="//apple_ref/cpp/Variable/gridparts" class="dashAnchor"></a>
            <h5><a href="#gridparts">gridparts</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finder.window.gridparts</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>An integer specifying how many gridparts the screen should be divided into. Defaults to 30.</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Functions</h4>
          <section id="centerCursor">
            <a name="//apple_ref/cpp/Function/centerCursor" class="dashAnchor"></a>
            <h5><a href="#centerCursor">centerCursor</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finder.window.centerCursor() -&gt; nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Center the cursor on the focused window.</p>
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
          <section id="grid">
            <a name="//apple_ref/cpp/Function/grid" class="dashAnchor"></a>
            <h5><a href="#grid">grid</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finder.window.grid() -&gt; nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Shows a modal keyboard driven interface for interactive window resizing.</p>
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
          <section id="hints">
            <a name="//apple_ref/cpp/Function/hints" class="dashAnchor"></a>
            <h5><a href="#hints">hints</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finder.window.hints() -&gt; nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Displays a keyboard hint for switching focus to each window.</p>
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
          <section id="moveAndResize">
            <a name="//apple_ref/cpp/Function/moveAndResize" class="dashAnchor"></a>
            <h5><a href="#moveAndResize">moveAndResize</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finder.window.moveAndResize(option)</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Move and resize the focused window.</p>
<p>Parameters:</p>
<ul>
<li>option - A string specifying the option, valid strings are: <code>halfleft</code>, <code>halfright</code>, <code>halfup</code>, <code>halfdown</code>, <code>cornerNW</code>, <code>cornerSW</code>, <code>cornerNE</code>, <code>cornerSE</code>, <code>center</code>, <code>fullscreen</code>, <code>expand</code>, <code>shrink</code>.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="moveToScreen">
            <a name="//apple_ref/cpp/Function/moveToScreen" class="dashAnchor"></a>
            <h5><a href="#moveToScreen">moveToScreen</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finder.window.moveToScreen(direction)</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Move the focused window between all of the screens in the <code>direction</code>.</p>
<p>Parameters:</p>
<ul>
<li>direction - A string specifying the direction, valid strings are: <code>left</code>, <code>right</code>, <code>up</code>, <code>down</code>, <code>next</code>.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="stepMove">
            <a name="//apple_ref/cpp/Function/stepMove" class="dashAnchor"></a>
            <h5><a href="#stepMove">stepMove</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finder.window.stepMove(direction)</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Move the focused window in the <code>direction</code> by one step. The step scale equals to the width/height of one gridpart.</p>
<p>Parameters:</p>
<ul>
<li>direction - A string specifying the direction, valid strings are: <code>left</code>, <code>right</code>, <code>up</code>, <code>down</code>.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="stepResize">
            <a name="//apple_ref/cpp/Function/stepResize" class="dashAnchor"></a>
            <h5><a href="#stepResize">stepResize</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finder.window.stepResize(direction)</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Resize the focused window in the <code>direction</code> by on step.</p>
<p>Parameters:</p>
<ul>
<li>direction - A string specifying the direction, valid strings are: <code>left</code>, <code>right</code>, <code>up</code>, <code>down</code>.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="undo">
            <a name="//apple_ref/cpp/Function/undo" class="dashAnchor"></a>
            <h5><a href="#undo">undo</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finder.window.undo()</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Undo the last window manipulation. Only those "moveAndResize" manipulations can be undone.</p>
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
