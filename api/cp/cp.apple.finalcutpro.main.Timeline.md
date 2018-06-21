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
      <h1><a href="cp.apple.finalcutpro.main.Timeline.md">docs</a> &raquo; cp.apple.finalcutpro.main.Timeline</h1>
      <p>Timeline Module.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#matches">matches</a></li>
            <li><a href="#matchesMain">matchesMain</a></li>
          </ul>
        <li>Constructors - API calls which return an object, typically one that offers API methods</li>
          <ul>
            <li><a href="#new">new</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#app">app</a></li>
            <li><a href="#contents">contents</a></li>
            <li><a href="#effects">effects</a></li>
            <li><a href="#hide">hide</a></li>
            <li><a href="#playhead">playhead</a></li>
            <li><a href="#show">show</a></li>
            <li><a href="#showOnPrimary">showOnPrimary</a></li>
            <li><a href="#showOnSecondary">showOnSecondary</a></li>
            <li><a href="#skimmingPlayhead">skimmingPlayhead</a></li>
            <li><a href="#toolbar">toolbar</a></li>
            <li><a href="#transitions">transitions</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Functions</h4>
          <section id="matches">
            <a name="//apple_ref/cpp/Function/matches" class="dashAnchor"></a>
            <h5><a href="#matches">matches</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.Timeline.matches(element) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks to see if an element matches what we think it should be.</p>
<p>Parameters:</p>
<ul>
<li>element - An <code>axuielementObject</code> to check.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if matches otherwise <code>false</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="matchesMain">
            <a name="//apple_ref/cpp/Function/matchesMain" class="dashAnchor"></a>
            <h5><a href="#matchesMain">matchesMain</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.Timeline.matchesMain(element) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks to see if an element matches what we think it should be.</p>
<p>Parameters:</p>
<ul>
<li>element - An <code>axuielementObject</code> to check.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if matches otherwise <code>false</code></li>
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
                <td><code>cp.apple.finalcutpro.main.Timeline.new(app) -&gt; Timeline</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new <code>Timeline</code> instance.</p>
<p>Parameters:</p>
<ul>
<li>app - The <code>cp.apple.finalcutpro</code> object.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A new <code>Timeline</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Methods</h4>
          <section id="app">
            <a name="//apple_ref/cpp/Method/app" class="dashAnchor"></a>
            <h5><a href="#app">app</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.Timeline:app() -&gt; App</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the app instance representing Final Cut Pro.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>App</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="contents">
            <a name="//apple_ref/cpp/Method/contents" class="dashAnchor"></a>
            <h5><a href="#contents">contents</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.Timeline:contents() -&gt; TimelineContent</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the Timeline Contents. The Content is the main body of the timeline,
containing the Timeline Index, the Content, and the Effects/Transitions panels.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>TimelineContent</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="effects">
            <a name="//apple_ref/cpp/Method/effects" class="dashAnchor"></a>
            <h5><a href="#effects">effects</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.Timeline:effects() -&gt; EffectsBrowser</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the (sometimes hidden) Effect Browser.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>EffectsBrowser</code> object.</li>
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
                <td><code>cp.apple.finalcutpro.main.Timeline:hide() -&gt; Timeline</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Hide's the Timeline (regardless of whether it was on the Primary or Secondary display).</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>Timeline</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="playhead">
            <a name="//apple_ref/cpp/Method/playhead" class="dashAnchor"></a>
            <h5><a href="#playhead">playhead</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.Timeline:playhead() -&gt; Playhead</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the Timeline Playhead.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>Playhead</code> object.</li>
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
                <td><code>cp.apple.finalcutpro.main.Timeline:show() -&gt; Timeline</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Show's the Timeline on the Primary Display.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>Timeline</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="showOnPrimary">
            <a name="//apple_ref/cpp/Method/showOnPrimary" class="dashAnchor"></a>
            <h5><a href="#showOnPrimary">showOnPrimary</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.Timeline:showOnPrimary() -&gt; Timeline</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Show's the Timeline on the Primary Display.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>Timeline</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="showOnSecondary">
            <a name="//apple_ref/cpp/Method/showOnSecondary" class="dashAnchor"></a>
            <h5><a href="#showOnSecondary">showOnSecondary</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.Timeline:showOnSecondary() -&gt; Timeline</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Show's the Timeline on the Secondary Display.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>Timeline</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="skimmingPlayhead">
            <a name="//apple_ref/cpp/Method/skimmingPlayhead" class="dashAnchor"></a>
            <h5><a href="#skimmingPlayhead">skimmingPlayhead</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.Timeline:skimmingPlayhead() -&gt; Playhead</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the Playhead that tracks under the mouse while skimming.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>Playhead</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="toolbar">
            <a name="//apple_ref/cpp/Method/toolbar" class="dashAnchor"></a>
            <h5><a href="#toolbar">toolbar</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.Timeline:toolbar() -&gt; TimelineToolbar</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the bar at the top of the timeline.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>TimelineToolbar</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="transitions">
            <a name="//apple_ref/cpp/Method/transitions" class="dashAnchor"></a>
            <h5><a href="#transitions">transitions</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.Timeline:transitions() -&gt; EffectsBrowser</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the (sometimes hidden) Transitions Browser.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>EffectsBrowser</code> object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
