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
      <h1><a href="cp.apple.finalcutpro.inspector.color.ColorBoard.md">docs</a> &raquo; cp.apple.finalcutpro.inspector.color.ColorBoard</h1>
      <p>Color Board Module.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Constants - Useful values which cannot be changed</li>
          <ul>
            <li><a href="#aspect">aspect</a></li>
            <li><a href="#color">color</a></li>
            <li><a href="#exposure">exposure</a></li>
            <li><a href="#saturation">saturation</a></li>
          </ul>
        <li>Variables - Configurable values</li>
          <ul>
            <li><a href="#currentAspect">currentAspect</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#matches">matches</a></li>
            <li><a href="#matchesCurrent">matchesCurrent</a></li>
            <li><a href="#matchesOriginal">matchesOriginal</a></li>
          </ul>
        <li>Constructors - API calls which return an object, typically one that offers API methods</li>
          <ul>
            <li><a href="#new">new</a></li>
          </ul>
        <li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
          <ul>
            <li><a href="#contentUI">contentUI</a></li>
            <li><a href="#isActive">isActive</a></li>
            <li><a href="#isAdvanced">isAdvanced</a></li>
            <li><a href="#isShowing">isShowing</a></li>
            <li><a href="#topToolbarUI">topToolbarUI</a></li>
            <li><a href="#UI">UI</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#app">app</a></li>
            <li><a href="#aspectGroup">aspectGroup</a></li>
            <li><a href="#backButton">backButton</a></li>
            <li><a href="#childUI">childUI</a></li>
            <li><a href="#color">color</a></li>
            <li><a href="#current">current</a></li>
            <li><a href="#exposure">exposure</a></li>
            <li><a href="#hide">hide</a></li>
            <li><a href="#nextAspect">nextAspect</a></li>
            <li><a href="#parent">parent</a></li>
            <li><a href="#reset">reset</a></li>
            <li><a href="#saturation">saturation</a></li>
            <li><a href="#show">show</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Constants</h4>
          <section id="aspect">
            <a name="//apple_ref/cpp/Constant/aspect" class="dashAnchor"></a>
            <h5><a href="#aspect">aspect</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoard.aspect -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>A table containing tables of all the aspect panel settings</p>
</td>
              </tr>
            </table>
          </section>
          <section id="color">
            <a name="//apple_ref/cpp/Constant/color" class="dashAnchor"></a>
            <h5><a href="#color">color</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoard.aspect.color -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>A table containing the Color Board Color panel settings</p>
</td>
              </tr>
            </table>
          </section>
          <section id="exposure">
            <a name="//apple_ref/cpp/Constant/exposure" class="dashAnchor"></a>
            <h5><a href="#exposure">exposure</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoard.aspect.exposure -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>A table containing the Color Board Exposure panel settings</p>
</td>
              </tr>
            </table>
          </section>
          <section id="saturation">
            <a name="//apple_ref/cpp/Constant/saturation" class="dashAnchor"></a>
            <h5><a href="#saturation">saturation</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoard.aspect.saturation -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>A table containing the Color Board Saturation panel settings</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Variables</h4>
          <section id="currentAspect">
            <a name="//apple_ref/cpp/Variable/currentAspect" class="dashAnchor"></a>
            <h5><a href="#currentAspect">currentAspect</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoard.currentAspect -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The current aspect as a string.</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Functions</h4>
          <section id="matches">
            <a name="//apple_ref/cpp/Function/matches" class="dashAnchor"></a>
            <h5><a href="#matches">matches</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoard.matches(element) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks to see if a GUI element is the Color Board or not</p>
<p>Parameters:</p>
<ul>
<li><code>element</code>    - The element you want to check</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the <code>element</code> is a Color Board otherwise <code>false</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="matchesCurrent">
            <a name="//apple_ref/cpp/Function/matchesCurrent" class="dashAnchor"></a>
            <h5><a href="#matchesCurrent">matchesCurrent</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoard.matchesCurrent(element) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks to see if a GUI element is the 'current' (10.4+) Color Board.</p>
<p>Parameters:</p>
<ul>
<li><code>element</code>    - The element you want to check</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the <code>element</code> is a 10.4+ Color Board otherwise <code>false</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="matchesOriginal">
            <a name="//apple_ref/cpp/Function/matchesOriginal" class="dashAnchor"></a>
            <h5><a href="#matchesOriginal">matchesOriginal</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoard.matchesOriginal(element) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks to see if a GUI element is the 'original' (pre-10.4) Color Board.</p>
<p>Parameters:</p>
<ul>
<li><code>element</code>    - The element you want to check</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the <code>element</code> is a pre-10.4 Color Board otherwise <code>false</code></li>
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
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoard.new(parent) -&gt; ColorBoard object</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new ColorBoard object</p>
<p>Parameters:</p>
<ul>
<li><code>parent</code>     - The parent</li>
</ul>
<p>Returns:</p>
<ul>
<li>A ColorBoard object</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Fields</h4>
          <section id="contentUI">
            <a name="//apple_ref/cpp/Field/contentUI" class="dashAnchor"></a>
            <h5><a href="#contentUI">contentUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoard.contentUI &lt;cp.prop: hs._asm.axuielement; read-only; live&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the <code>hs._asm.axuielement</code> object for the Color Board's content.</p>
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
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoard:isActive &lt;cp.prop: boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns whether or not the Color Board is active</p>
</td>
              </tr>
            </table>
          </section>
          <section id="isAdvanced">
            <a name="//apple_ref/cpp/Field/isAdvanced" class="dashAnchor"></a>
            <h5><a href="#isAdvanced">isAdvanced</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoard.isAdvanced &lt;cp.prop: boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks if the advanced Color Inspector (from 10.4) is supported.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="isShowing">
            <a name="//apple_ref/cpp/Field/isShowing" class="dashAnchor"></a>
            <h5><a href="#isShowing">isShowing</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoard.isShowing &lt;cp.prop: boolean; read-only; live&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns whether or not the Color Board is visible.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="topToolbarUI">
            <a name="//apple_ref/cpp/Field/topToolbarUI" class="dashAnchor"></a>
            <h5><a href="#topToolbarUI">topToolbarUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoard.topToolbarUI &lt;cp.prop: hs._asm.axuielement; read-only; live&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the <code>hs._asm.axuielement</code> object for the top toolbar (i.e. where the Back Button is located in Final Cut Pro 10.3)</p>
<p>Notes:</p>
<ul>
<li>This object doesn't exist in Final Cut Pro 10.4 as the Color Board is now contained within the Color Inspector</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="UI">
            <a name="//apple_ref/cpp/Field/UI" class="dashAnchor"></a>
            <h5><a href="#UI">UI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoard.UI &lt;cp.prop: hs._asm.axuielement; read-only; live&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the <code>hs._asm.axuielement</code> object for the Color Board.</p>
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
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoard:app() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the <code>cp.apple.finalcutpro</code> app table</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The application object as a table</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="aspectGroup">
            <a name="//apple_ref/cpp/Method/aspectGroup" class="dashAnchor"></a>
            <h5><a href="#aspectGroup">aspectGroup</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoard:aspectGroup() -&gt; cp.ui.RadioGroup</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the <code>RadioGroup</code> for the 'aspect' currently being controlled 
either "Color", "Saturation", or "Exposure".</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>RadioGroup</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="backButton">
            <a name="//apple_ref/cpp/Method/backButton" class="dashAnchor"></a>
            <h5><a href="#backButton">backButton</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoard:backButton() -&gt; Button</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a <code>Button</code> to access the 'Back' button, if present.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>Button</code> for 'back'.</li>
</ul>
<p>Notes:</p>
<ul>
<li>This no longer exists in FCP 10.4+, so will always be non-functional.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="childUI">
            <a name="//apple_ref/cpp/Method/childUI" class="dashAnchor"></a>
            <h5><a href="#childUI">childUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoard:childUI(id) -&gt; hs._asm.axuielement object</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the <code>hs._asm.axuielement</code> object for a child with the specified ID.</p>
<p>Parameters:</p>
<ul>
<li>axID - <code>AXIdentifier</code> of the child</li>
</ul>
<p>Returns:</p>
<ul>
<li>An <code>hs._asm.axuielement</code> object</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="color">
            <a name="//apple_ref/cpp/Method/color" class="dashAnchor"></a>
            <h5><a href="#color">color</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoard:color() -&gt; ColorBoardAspect</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the <code>color</code> aspect of the color board.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>ColorBoardAspect</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="current">
            <a name="//apple_ref/cpp/Method/current" class="dashAnchor"></a>
            <h5><a href="#current">current</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoard:current() -&gt; ColorBoardAspect</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the currently-selected 'aspect' of the Color Board - either the <code>color</code>, <code>saturation</code> or <code>exposure</code>.
If the color board is not currently visible, it returns the <code>color</code> aspect by default.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The currently active <code>ColorBoardAspect</code>, or the <code>color</code> aspect if none is showing.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="exposure">
            <a name="//apple_ref/cpp/Method/exposure" class="dashAnchor"></a>
            <h5><a href="#exposure">exposure</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoard:exposure() -&gt; ColorBoardAspect</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the <code>exposure</code> aspect of the color board.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>ColorBoardAspect</code>.</li>
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
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoard:hide() -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Hides the Color Board</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>ColorBoard object</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="nextAspect">
            <a name="//apple_ref/cpp/Method/nextAspect" class="dashAnchor"></a>
            <h5><a href="#nextAspect">nextAspect</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoard:nextAspect() -&gt; ColorBoard object</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Toggles the Color Board Panels between "Color", "Saturation" and "Exposure"</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>ColorBoard object</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="parent">
            <a name="//apple_ref/cpp/Method/parent" class="dashAnchor"></a>
            <h5><a href="#parent">parent</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoard:parent() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the ColorBoard's parent table</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The parent object as a table</li>
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
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoard:reset() -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Resets the current aspect.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>ColorBoard object</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="saturation">
            <a name="//apple_ref/cpp/Method/saturation" class="dashAnchor"></a>
            <h5><a href="#saturation">saturation</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoard:saturation() -&gt; ColorBoardAspect</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the <code>saturation</code> aspect of the color board.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>ColorBoardAspect</code>.</li>
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
                <td><code>cp.apple.finalcutpro.inspector.color.ColorBoard:show() -&gt; ColorBoard object</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Shows the Color Board</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>ColorBoard object</li>
</ul>
</td>
              </tr>
            </table>
          </section>
