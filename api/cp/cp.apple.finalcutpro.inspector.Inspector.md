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
      <h1><a href="cp.apple.finalcutpro.inspector.Inspector.md">docs</a> &raquo; cp.apple.finalcutpro.inspector.Inspector</h1>
      <p>Inspector</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Constants - Useful values which cannot be changed</li>
          <ul>
            <li><a href="#INSPECTOR_TABS">INSPECTOR_TABS</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#matches">matches</a></li>
          </ul>
        <li>Constructors - API calls which return an object, typically one that offers API methods</li>
          <ul>
            <li><a href="#new">new</a></li>
          </ul>
        <li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
          <ul>
            <li><a href="#bottomBarUI">bottomBarUI</a></li>
            <li><a href="#isFullHeight">isFullHeight</a></li>
            <li><a href="#isShowing">isShowing</a></li>
            <li><a href="#labelUI">labelUI</a></li>
            <li><a href="#panelUI">panelUI</a></li>
            <li><a href="#propertiesUI">propertiesUI</a></li>
            <li><a href="#topBarUI">topBarUI</a></li>
            <li><a href="#UI">UI</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#app">app</a></li>
            <li><a href="#audio">audio</a></li>
            <li><a href="#color">color</a></li>
            <li><a href="#effect">effect</a></li>
            <li><a href="#generator">generator</a></li>
            <li><a href="#hide">hide</a></li>
            <li><a href="#info">info</a></li>
            <li><a href="#parent">parent</a></li>
            <li><a href="#selectedTab">selectedTab</a></li>
            <li><a href="#selectTab">selectTab</a></li>
            <li><a href="#share">share</a></li>
            <li><a href="#show">show</a></li>
            <li><a href="#tabAvailable">tabAvailable</a></li>
            <li><a href="#text">text</a></li>
            <li><a href="#title">title</a></li>
            <li><a href="#transition">transition</a></li>
            <li><a href="#video">video</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Constants</h4>
          <section id="INSPECTOR_TABS">
            <a name="//apple_ref/cpp/Constant/INSPECTOR_TABS" class="dashAnchor"></a>
            <h5><a href="#INSPECTOR_TABS">INSPECTOR_TABS</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.Inspector.INSPECTOR_TABS -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Table of supported Inspector Tabs</p>
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
                <td><code>cp.apple.finalcutpro.inspector.Inspector.matches(element) -&gt; boolean</code></td>
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
<li>element - axuielementObject</li>
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
                <td><code>cp.apple.finalcutpro.inspector.Inspector.new(parent) -&gt; Inspector</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new Inspector.</p>
<p>Parameters:</p>
<ul>
<li>parent - The parent object.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The Inspector object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Fields</h4>
          <section id="bottomBarUI">
            <a name="//apple_ref/cpp/Field/bottomBarUI" class="dashAnchor"></a>
            <h5><a href="#bottomBarUI">bottomBarUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.Inspector.bottomBarUI &lt;cp.prop: hs._asm.axuielement; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the bottom bar <code>axuielement</code> for the Inspector.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="isFullHeight">
            <a name="//apple_ref/cpp/Field/isFullHeight" class="dashAnchor"></a>
            <h5><a href="#isFullHeight">isFullHeight</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.Inspector.isFullHeight &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns <code>true</code> if the Inspector is full height.</p>
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
                <td><code>cp.apple.finalcutpro.inspector.Inspector.isShowing &lt;cp.prop: boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns <code>true</code> if the Inspector is showing otherwise <code>false</code></p>
</td>
              </tr>
            </table>
          </section>
          <section id="labelUI">
            <a name="//apple_ref/cpp/Field/labelUI" class="dashAnchor"></a>
            <h5><a href="#labelUI">labelUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.Inspector.labelUI &lt;cp.prop: hs._asm.axuielement; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the <code>axuielement</code> for text label at the top of the Inspector.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="panelUI">
            <a name="//apple_ref/cpp/Field/panelUI" class="dashAnchor"></a>
            <h5><a href="#panelUI">panelUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.Inspector.panelUI &lt;cp.prop: hs._asm.axuielement; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the central panel <code>axuielement</code> for the Inspector.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="propertiesUI">
            <a name="//apple_ref/cpp/Field/propertiesUI" class="dashAnchor"></a>
            <h5><a href="#propertiesUI">propertiesUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.Inspector.propertiesUI &lt;cp.prop: hs._asm.axuielement; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the properties <code>axuielement</code> for the Inspector. This contains the rows of property values.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="topBarUI">
            <a name="//apple_ref/cpp/Field/topBarUI" class="dashAnchor"></a>
            <h5><a href="#topBarUI">topBarUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.Inspector.topBarUI &lt;cp.prop: hs._asm.axuielement; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the "top bar" <code>axuielement</code> for the Inspector.</p>
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
                <td><code>cp.apple.finalcutpro.inspector.Inspector.UI &lt;cp.prop: hs._asm.axuielement; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the <code>axuielement</code> for the Inspector.</p>
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
                <td><code>cp.apple.finalcutpro.inspector.Inspector:app() -&gt; App</code></td>
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
          <section id="audio">
            <a name="//apple_ref/cpp/Method/audio" class="dashAnchor"></a>
            <h5><a href="#audio">audio</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.Inspector:audio() -&gt; AudioInspector</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the AudioInspector object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>AudioInspector</li>
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
                <td><code>cp.apple.finalcutpro.inspector.Inspector:color() -&gt; ColorInspector</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the ColorInspector object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>ColorInspector</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="effect">
            <a name="//apple_ref/cpp/Method/effect" class="dashAnchor"></a>
            <h5><a href="#effect">effect</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.Inspector:effect() -&gt; EffectInspector</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the EffectInspector object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>EffectInspector</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="generator">
            <a name="//apple_ref/cpp/Method/generator" class="dashAnchor"></a>
            <h5><a href="#generator">generator</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.Inspector:generator() -&gt; GeneratorInspector</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the GeneratorInspector object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>GeneratorInspector</li>
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
                <td><code>cp.apple.finalcutpro.inspector.Inspector:hide() -&gt; Inspector</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Hides the inspector.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>Inspector</code> instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="info">
            <a name="//apple_ref/cpp/Method/info" class="dashAnchor"></a>
            <h5><a href="#info">info</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.Inspector:info() -&gt; InfoInspector</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the InfoInspector object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>InfoInspector</li>
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
                <td><code>cp.apple.finalcutpro.inspector.Inspector:parent() -&gt; Parent</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the parent of the Inspector.</p>
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
          <section id="selectedTab">
            <a name="//apple_ref/cpp/Method/selectedTab" class="dashAnchor"></a>
            <h5><a href="#selectedTab">selectedTab</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.Inspector:selectedTab() -&gt; string or nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the name of the selected inspector tab otherwise <code>nil</code>.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A string of the selected tab, otherwise <code>nil</code> if the Inspector is closed or an error occurred.</li>
</ul>
<p>Notes:</p>
<ul>
<li>The tab strings can be:<ul>
<li>Audio</li>
<li>Color</li>
<li>Effect</li>
<li>Generator</li>
<li>Info</li>
<li>Share</li>
<li>Text</li>
<li>Title</li>
<li>Transition</li>
<li>Video</li>
</ul>
</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="selectTab">
            <a name="//apple_ref/cpp/Method/selectTab" class="dashAnchor"></a>
            <h5><a href="#selectTab">selectTab</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.Inspector:selectTab(tab) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Selects a tab in the inspector.</p>
<p>Parameters:</p>
<ul>
<li>tab - A string from the <code>cp.apple.finalcutpro.inspector.Inspector.INSPECTOR_TABS</code> table</li>
</ul>
<p>Returns:</p>
<ul>
<li>A string of the selected tab, otherwise <code>nil</code> if an error occurred.</li>
</ul>
<p>Notes:</p>
<ul>
<li>This method will open the Inspector if it's closed, and leave it open.</li>
<li>Valid strings for <code>value</code> are as follows:<ul>
<li>Audio</li>
<li>Color</li>
<li>Effect</li>
<li>Generator</li>
<li>Info</li>
<li>Share</li>
<li>Text</li>
<li>Title</li>
<li>Transition</li>
<li>Video</li>
</ul>
</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="share">
            <a name="//apple_ref/cpp/Method/share" class="dashAnchor"></a>
            <h5><a href="#share">share</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.Inspector:share() -&gt; ShareInspector</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the ShareInspector object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>ShareInspector</li>
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
                <td><code>cp.apple.finalcutpro.inspector.Inspector:show([tab]) -&gt; Inspector</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Shows the inspector.</p>
<p>Parameters:</p>
<ul>
<li>[tab] - A string from the <code>cp.apple.finalcutpro.inspector.Inspector.INSPECTOR_TABS</code> table</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>Inspector</code> instance.</li>
</ul>
<p>Notes:</p>
<ul>
<li>Valid strings for <code>value</code> are as follows:<ul>
<li>Audio</li>
<li>Color</li>
<li>Effect</li>
<li>Generator</li>
<li>Info</li>
<li>Share</li>
<li>Text</li>
<li>Title</li>
<li>Transition</li>
<li>Video</li>
</ul>
</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="tabAvailable">
            <a name="//apple_ref/cpp/Method/tabAvailable" class="dashAnchor"></a>
            <h5><a href="#tabAvailable">tabAvailable</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.Inspector:tabAvailable(tab) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks to see if a tab is currently available in the Inspector.</p>
<p>Parameters:</p>
<ul>
<li>tab - A string from the <code>cp.apple.finalcutpro.inspector.Inspector.INSPECTOR_TABS</code> table</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if available otherwise <code>false</code>.</li>
</ul>
<p>Notes:</p>
<ul>
<li>Valid strings for <code>value</code> are as follows:<ul>
<li>Audio</li>
<li>Color</li>
<li>Effect</li>
<li>Generator</li>
<li>Info</li>
<li>Share</li>
<li>Text</li>
<li>Title</li>
<li>Transition</li>
<li>Video</li>
</ul>
</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="text">
            <a name="//apple_ref/cpp/Method/text" class="dashAnchor"></a>
            <h5><a href="#text">text</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.Inspector:text() -&gt; TextInspector</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the TextInspector object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>TextInspector</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="title">
            <a name="//apple_ref/cpp/Method/title" class="dashAnchor"></a>
            <h5><a href="#title">title</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.Inspector:title() -&gt; TitleInspector</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the TitleInspector object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>TitleInspector</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="transition">
            <a name="//apple_ref/cpp/Method/transition" class="dashAnchor"></a>
            <h5><a href="#transition">transition</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.Inspector:transition() -&gt; TransitionInspector</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the TransitionInspector object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>TransitionInspector</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="video">
            <a name="//apple_ref/cpp/Method/video" class="dashAnchor"></a>
            <h5><a href="#video">video</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.Inspector:video() -&gt; VideoInspector</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the VideoInspector object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>ColorInspector</li>
</ul>
</td>
              </tr>
            </table>
          </section>
