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
      <h1><a href="cp.apple.finalcutpro.md">docs</a> &raquo; cp.apple.finalcutpro</h1>
      <p>Represents the Final Cut Pro application, providing functions that allow different tasks to be accomplished.</p>
<p>Generally, you will <code>require</code> the <code>cp.apple.finalcutpro</code> module to import it, like so:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">fcp</span> <span class="o">=</span> <span class="nb">require</span><span class="p">(</span><span class="s2">&quot;cp.apple.finalcutpro&quot;</span><span class="p">)</span>
</pre></div>
<p>Then, there are the <code>UpperCase</code> files, which represent the application itself:</p>
<ul>
<li><code>MenuBar</code>                 - The main menu bar.</li>
<li><code>prefs/PreferencesWindow</code> - The preferences window.</li>
<li>etc...</li>
</ul>
<p>The <code>fcp</code> variable is the root application. It has functions which allow you to perform tasks or access parts of the UI. For example, to open the <code>Preferences</code> window, you can do this:</p>
<div class="highlight"><pre><span></span><span class="n">fcp</span><span class="p">:</span><span class="n">preferencesWindow</span><span class="p">():</span><span class="n">show</span><span class="p">()</span>
</pre></div>
<p>In general, as long as Final Cut Pro is running, actions can be performed directly, and the API will perform the required operations to achieve it. For example, to toggle the 'Create Optimized Media' checkbox in the 'Import' section of the 'Preferences' window, you can simply do this:</p>
<div class="highlight"><pre><span></span><span class="n">fcp</span><span class="p">:</span><span class="n">preferencesWindow</span><span class="p">():</span><span class="n">importPanel</span><span class="p">():</span><span class="n">toggleCreateOptimizedMedia</span><span class="p">()</span>
</pre></div>
<p>The API will automatically open the <code>Preferences</code> window, navigate to the 'Import' panel and toggle the checkbox.</p>
<p>The <code>UpperCase</code> classes also have a variety of <code>UI</code> methods. These will return the <code>axuielement</code> for the relevant GUI element, if it is accessible. If not, it will return <code>nil</code>. These allow direct interaction with the GUI if necessary. It's most useful when adding new functions to <code>UpperCase</code> files for a particular element.</p>
<p>This can also be used to 'wait' for an element to be visible before performing a task. For example, if you need to wait for the <code>Preferences</code> window to finish loading before doing something else, you can do this with the <code>cp.just</code> library:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">just</span> <span class="o">=</span> <span class="nb">require</span><span class="p">(</span><span class="s2">&quot;cp.just&quot;</span><span class="p">)</span>

<span class="kd">local</span> <span class="n">prefsWindow</span> <span class="o">=</span> <span class="n">fcp</span><span class="p">:</span><span class="n">preferencesWindow</span><span class="p">()</span>

<span class="kd">local</span> <span class="n">prefsUI</span> <span class="o">=</span> <span class="n">just</span><span class="p">.</span><span class="n">doUntil</span><span class="p">(</span><span class="kr">function</span><span class="p">()</span> <span class="kr">return</span> <span class="n">prefsWindow</span><span class="p">:</span><span class="n">UI</span><span class="p">()</span> <span class="kr">end</span><span class="p">)</span>

<span class="kr">if</span> <span class="n">prefsUI</span> <span class="kr">then</span>
    <span class="c1">-- it&#39;s open!</span>
<span class="kr">else</span>
    <span class="c1">-- it&#39;s closed!</span>
<span class="kr">end</span>
</pre></div>
<p>By using the <code>just</code> library, we can do a loop waiting until the function returns a result that will give up after a certain time period (10 seconds by default).</p>
<p>Of course, we have a specific support function for that already, so you could do this instead:</p>
<div class="highlight"><pre><span></span><span class="kr">if</span> <span class="n">fcp</span><span class="p">:</span><span class="n">preferencesWindow</span><span class="p">():</span><span class="n">isShowing</span><span class="p">()</span> <span class="kr">then</span>
    <span class="c1">-- it&#39;s open!</span>
<span class="kr">else</span>
    <span class="c1">-- it&#39;s closed!</span>
<span class="kr">end</span>
</pre></div>

      </header>
        <h3>Submodules</h3>
        <ul>
        <li><a href="cp.apple.finalcutpro.app.html">cp.apple.finalcutpro.app</a></li>
        <li><a href="cp.apple.finalcutpro.cmd.html">cp.apple.finalcutpro.cmd</a></li>
        <li><a href="cp.apple.finalcutpro.content.html">cp.apple.finalcutpro.content</a></li>
        <li><a href="cp.apple.finalcutpro.export.html">cp.apple.finalcutpro.export</a></li>
        <li><a href="cp.apple.finalcutpro.ids.html">cp.apple.finalcutpro.ids</a></li>
        <li><a href="cp.apple.finalcutpro.import.html">cp.apple.finalcutpro.import</a></li>
        <li><a href="cp.apple.finalcutpro.inspector.html">cp.apple.finalcutpro.inspector</a></li>
        <li><a href="cp.apple.finalcutpro.main.html">cp.apple.finalcutpro.main</a></li>
        <li><a href="cp.apple.finalcutpro.menu.html">cp.apple.finalcutpro.menu</a></li>
        <li><a href="cp.apple.finalcutpro.plugins.html">cp.apple.finalcutpro.plugins</a></li>
        <li><a href="cp.apple.finalcutpro.prefs.html">cp.apple.finalcutpro.prefs</a></li>
        <li><a href="cp.apple.finalcutpro.strings.html">cp.apple.finalcutpro.strings</a></li>
        </ul>
      <h3>API Overview</h3>
      <ul>
        <li>Constants - Useful values which cannot be changed</li>
          <ul>
            <li><a href="#ALLOWED_IMPORT_AUDIO_EXTENSIONS">ALLOWED_IMPORT_AUDIO_EXTENSIONS</a></li>
            <li><a href="#ALLOWED_IMPORT_EXTENSIONS">ALLOWED_IMPORT_EXTENSIONS</a></li>
            <li><a href="#ALLOWED_IMPORT_IMAGE_EXTENSIONS">ALLOWED_IMPORT_IMAGE_EXTENSIONS</a></li>
            <li><a href="#ALLOWED_IMPORT_VIDEO_EXTENSIONS">ALLOWED_IMPORT_VIDEO_EXTENSIONS</a></li>
            <li><a href="#BUNDLE_ID">BUNDLE_ID</a></li>
            <li><a href="#EARLIEST_SUPPORTED_VERSION">EARLIEST_SUPPORTED_VERSION</a></li>
            <li><a href="#EVENT_DESCRIPTION_PATH">EVENT_DESCRIPTION_PATH</a></li>
            <li><a href="#FLEXO_LANGUAGES">FLEXO_LANGUAGES</a></li>
            <li><a href="#PASTEBOARD_UTI">PASTEBOARD_UTI</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#commandSet">commandSet</a></li>
            <li><a href="#init">init</a></li>
            <li><a href="#matches">matches</a></li>
            <li><a href="#reset">reset</a></li>
          </ul>
        <li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
          <ul>
            <li><a href="#contentUI">contentUI</a></li>
            <li><a href="#contentUI">contentUI</a></li>
            <li><a href="#contentUI">contentUI</a></li>
            <li><a href="#contentUI">contentUI</a></li>
            <li><a href="#isShowing">isShowing</a></li>
            <li><a href="#isShowing">isShowing</a></li>
            <li><a href="#isShowing">isShowing</a></li>
            <li><a href="#isShowing">isShowing</a></li>
            <li><a href="#isShowing">isShowing</a></li>
            <li><a href="#UI">UI</a></li>
            <li><a href="#UI">UI</a></li>
            <li><a href="#UI">UI</a></li>
            <li><a href="#UI">UI</a></li>
            <li><a href="#UI">UI</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#activeCommandSet">activeCommandSet</a></li>
            <li><a href="#activeCommandSetPath">activeCommandSetPath</a></li>
            <li><a href="#alert">alert</a></li>
            <li><a href="#browser">browser</a></li>
            <li><a href="#bundleID">bundleID</a></li>
            <li><a href="#closeLibrary">closeLibrary</a></li>
            <li><a href="#color">color</a></li>
            <li><a href="#colorBoard">colorBoard</a></li>
            <li><a href="#commandEditor">commandEditor</a></li>
            <li><a href="#defaultCommandSetPath">defaultCommandSetPath</a></li>
            <li><a href="#effects">effects</a></li>
            <li><a href="#eventViewer">eventViewer</a></li>
            <li><a href="#exportDialog">exportDialog</a></li>
            <li><a href="#fullScreenWindow">fullScreenWindow</a></li>
            <li><a href="#generators">generators</a></li>
            <li><a href="#getCommandShortcuts">getCommandShortcuts</a></li>
            <li><a href="#getPath">getPath</a></li>
            <li><a href="#hide">hide</a></li>
            <li><a href="#importXML">importXML</a></li>
            <li><a href="#inspector">inspector</a></li>
            <li><a href="#isSupportedLocale">isSupportedLocale</a></li>
            <li><a href="#keysWithString">keysWithString</a></li>
            <li><a href="#keywordEditor">keywordEditor</a></li>
            <li><a href="#launch">launch</a></li>
            <li><a href="#libraries">libraries</a></li>
            <li><a href="#media">media</a></li>
            <li><a href="#mediaImport">mediaImport</a></li>
            <li><a href="#menu">menu</a></li>
            <li><a href="#notifier">notifier</a></li>
            <li><a href="#openLibrary">openLibrary</a></li>
            <li><a href="#performShortcut">performShortcut</a></li>
            <li><a href="#plugins">plugins</a></li>
            <li><a href="#preferencesWindow">preferencesWindow</a></li>
            <li><a href="#primaryWindow">primaryWindow</a></li>
            <li><a href="#quit">quit</a></li>
            <li><a href="#restart">restart</a></li>
            <li><a href="#scanPlugins">scanPlugins</a></li>
            <li><a href="#secondaryWindow">secondaryWindow</a></li>
            <li><a href="#selectLibrary">selectLibrary</a></li>
            <li><a href="#selectMenu">selectMenu</a></li>
            <li><a href="#selectMenuItem">selectMenuItem</a></li>
            <li><a href="#show">show</a></li>
            <li><a href="#string">string</a></li>
            <li><a href="#timeline">timeline</a></li>
            <li><a href="#toolbar">toolbar</a></li>
            <li><a href="#transitions">transitions</a></li>
            <li><a href="#userCommandSetPath">userCommandSetPath</a></li>
            <li><a href="#viewer">viewer</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Constants</h4>
          <section id="ALLOWED_IMPORT_AUDIO_EXTENSIONS">
            <a name="//apple_ref/cpp/Constant/ALLOWED_IMPORT_AUDIO_EXTENSIONS" class="dashAnchor"></a>
            <h5><a href="#ALLOWED_IMPORT_AUDIO_EXTENSIONS">ALLOWED_IMPORT_AUDIO_EXTENSIONS</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.ALLOWED_IMPORT_AUDIO_EXTENSIONS</code></td>
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
          <section id="ALLOWED_IMPORT_EXTENSIONS">
            <a name="//apple_ref/cpp/Constant/ALLOWED_IMPORT_EXTENSIONS" class="dashAnchor"></a>
            <h5><a href="#ALLOWED_IMPORT_EXTENSIONS">ALLOWED_IMPORT_EXTENSIONS</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.ALLOWED_IMPORT_EXTENSIONS</code></td>
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
          <section id="ALLOWED_IMPORT_IMAGE_EXTENSIONS">
            <a name="//apple_ref/cpp/Constant/ALLOWED_IMPORT_IMAGE_EXTENSIONS" class="dashAnchor"></a>
            <h5><a href="#ALLOWED_IMPORT_IMAGE_EXTENSIONS">ALLOWED_IMPORT_IMAGE_EXTENSIONS</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.ALLOWED_IMPORT_IMAGE_EXTENSIONS</code></td>
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
                <td><code>cp.apple.finalcutpro.ALLOWED_IMPORT_VIDEO_EXTENSIONS</code></td>
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
                <td><code>cp.apple.finalcutpro.BUNDLE_ID</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Final Cut Pro's Bundle ID as a <code>semver</code>.</p>
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
                <td><code>cp.apple.finalcutpro.EARLIEST_SUPPORTED_VERSION</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The earliest version of Final Cut Pro supported by this module.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="EVENT_DESCRIPTION_PATH">
            <a name="//apple_ref/cpp/Constant/EVENT_DESCRIPTION_PATH" class="dashAnchor"></a>
            <h5><a href="#EVENT_DESCRIPTION_PATH">EVENT_DESCRIPTION_PATH</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.EVENT_DESCRIPTION_PATH</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The Event Description Path.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="FLEXO_LANGUAGES">
            <a name="//apple_ref/cpp/Constant/FLEXO_LANGUAGES" class="dashAnchor"></a>
            <h5><a href="#FLEXO_LANGUAGES">FLEXO_LANGUAGES</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.FLEXO_LANGUAGES</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Table of Final Cut Pro's supported Languages for the Flexo Framework</p>
</td>
              </tr>
            </table>
          </section>
          <section id="PASTEBOARD_UTI">
            <a name="//apple_ref/cpp/Constant/PASTEBOARD_UTI" class="dashAnchor"></a>
            <h5><a href="#PASTEBOARD_UTI">PASTEBOARD_UTI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.PASTEBOARD_UTI</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Final Cut Pro's Pasteboard UTI</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Functions</h4>
          <section id="commandSet">
            <a name="//apple_ref/cpp/Function/commandSet" class="dashAnchor"></a>
            <h5><a href="#commandSet">commandSet</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.commandSet(path) -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the Command Set at the specified path as a table.</p>
<p>Parameters:</p>
<ul>
<li><code>path</code>   - The path to the Command Set.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The Command Set as a table, or <code>nil</code> if there was a problem.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="init">
            <a name="//apple_ref/cpp/Function/init" class="dashAnchor"></a>
            <h5><a href="#init">init</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro:init() -&gt; App</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Initialises the app instance representing Final Cut Pro.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The app.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="matches">
            <a name="//apple_ref/cpp/Function/matches" class="dashAnchor"></a>
            <h5><a href="#matches">matches</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.CommandEditor.matches(element) -&gt; boolean</code></td>
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
          <section id="reset">
            <a name="//apple_ref/cpp/Function/reset" class="dashAnchor"></a>
            <h5><a href="#reset">reset</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro:reset() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Resets the language cache</p>
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
          <section id="contentUI">
            <a name="//apple_ref/cpp/Field/contentUI" class="dashAnchor"></a>
            <h5><a href="#contentUI">contentUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.ShareInspector.contentUI &lt;cp.prop: hs._asm.axuielement; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The <code>axuielement</code> containing the properties rows, if available.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="contentUI">
            <a name="//apple_ref/cpp/Field/contentUI" class="dashAnchor"></a>
            <h5><a href="#contentUI">contentUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.TextInspector.contentUI &lt;cp.prop: hs._asm.axuielement; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The <code>axuielement</code> containing the properties rows, if available.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="contentUI">
            <a name="//apple_ref/cpp/Field/contentUI" class="dashAnchor"></a>
            <h5><a href="#contentUI">contentUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.TitleInspector.contentUI &lt;cp.prop: hs._asm.axuielement; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The <code>axuielement</code> containing the properties rows, if available.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="contentUI">
            <a name="//apple_ref/cpp/Field/contentUI" class="dashAnchor"></a>
            <h5><a href="#contentUI">contentUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.inspector.color.VideoInspector.contentUI &lt;cp.prop: hs._asm.axuielement; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The <code>axuielement</code> containing the properties rows, if available.</p>
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
                <td><code>cp.apple.finalcutpro.inspector.color.TitleInspector.isShowing &lt;cp.prop: boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks if the TitleInspector is currently showing.</p>
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
                <td><code>cp.apple.finalcutpro.inspector.color.AudioInspector.isShowing &lt;cp.prop: boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks if the AudioInspector is currently showing.</p>
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
                <td><code>cp.apple.finalcutpro.inspector.color.ShareInspector.isShowing &lt;cp.prop: boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks if the ShareInspector is currently showing.</p>
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
                <td><code>cp.apple.finalcutpro.inspector.color.VideoInspector.isShowing &lt;cp.prop: boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks if the VideoInspector is currently showing.</p>
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
                <td><code>cp.apple.finalcutpro.inspector.color.TextInspector.isShowing &lt;cp.prop: boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks if the TextInspector is currently showing.</p>
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
                <td><code>cp.apple.finalcutpro.inspector.color.AudioInspector.UI &lt;cp.prop: hs._asm.axuielement; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the <code>hs._asm.axuielement</code> object for the Audio Inspector.</p>
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
                <td><code>cp.apple.finalcutpro.inspector.color.VideoInspector.UI &lt;cp.prop: hs._asm.axuielement; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the <code>hs._asm.axuielement</code> object for the Video Inspector.</p>
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
                <td><code>cp.apple.finalcutpro.inspector.color.TitleInspector.UI &lt;cp.prop: hs._asm.axuielement; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the <code>hs._asm.axuielement</code> object for the Title Inspector.</p>
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
                <td><code>cp.apple.finalcutpro.inspector.color.ShareInspector.UI &lt;cp.prop: hs._asm.axuielement; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the <code>hs._asm.axuielement</code> object for the Share Inspector.</p>
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
                <td><code>cp.apple.finalcutpro.inspector.color.TextInspector.UI &lt;cp.prop: hs._asm.axuielement; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the <code>hs._asm.axuielement</code> object for the Text Inspector.</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Methods</h4>
          <section id="activeCommandSet">
            <a name="//apple_ref/cpp/Method/activeCommandSet" class="dashAnchor"></a>
            <h5><a href="#activeCommandSet">activeCommandSet</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro:activeCommandSet([forceReload]) -&gt; table or nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the 'Active Command Set' as a Table. The result is cached, so pass in
<code>true</code> for <code>forceReload</code> if you want to reload it.</p>
<p>Parameters:</p>
<ul>
<li>[forceReload]    - If <code>true</code>, require the Command Set to be reloaded.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table of the Active Command Set's contents, or <code>nil</code> if an error occurred</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="activeCommandSetPath">
            <a name="//apple_ref/cpp/Method/activeCommandSetPath" class="dashAnchor"></a>
            <h5><a href="#activeCommandSetPath">activeCommandSetPath</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro:activeCommandSetPath() -&gt; string or nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the 'Active Command Set' value from the Final Cut Pro preferences</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The 'Active Command Set' value, or the 'Default' Command Set if this is the first time Final Cut Pro has been run.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="alert">
            <a name="//apple_ref/cpp/Method/alert" class="dashAnchor"></a>
            <h5><a href="#alert">alert</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro:alert() -&gt; cp.ui.Alert</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Provides basic access to any 'alert' dialog windows in the app.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>the <code>Alert</code> instance</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="browser">
            <a name="//apple_ref/cpp/Method/browser" class="dashAnchor"></a>
            <h5><a href="#browser">browser</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro:browser() -&gt; Browser</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the Browser instance, whether it is in the primary or secondary window.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>the Browser</li>
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
                <td><code>cp.apple.finalcutpro:bundleID() -&gt; string</code></td>
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
<li>The Bundle ID</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="closeLibrary">
            <a name="//apple_ref/cpp/Method/closeLibrary" class="dashAnchor"></a>
            <h5><a href="#closeLibrary">closeLibrary</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro:closeLibrary(title) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Attempts to close a library with the specified <code>title</code>.</p>
<p>Parameters:</p>
<ul>
<li>title - The title of the FCP Library to close.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successful, or <code>false</code> if not.</li>
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
                <td><code>cp.apple.finalcutpro:color() -&gt; ColorInspector</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the ColorInspector instance from the primary window</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>the ColorInspector</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="colorBoard">
            <a name="//apple_ref/cpp/Method/colorBoard" class="dashAnchor"></a>
            <h5><a href="#colorBoard">colorBoard</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro:colorBoard() -&gt; ColorBoard</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the ColorBoard instance from the primary window</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>the ColorBoard</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="commandEditor">
            <a name="//apple_ref/cpp/Method/commandEditor" class="dashAnchor"></a>
            <h5><a href="#commandEditor">commandEditor</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro:commandEditor() -&gt; commandEditor object</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the Final Cut Pro Command Editor</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The Final Cut Pro Command Editor</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="defaultCommandSetPath">
            <a name="//apple_ref/cpp/Method/defaultCommandSetPath" class="dashAnchor"></a>
            <h5><a href="#defaultCommandSetPath">defaultCommandSetPath</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro:defaultCommandSetPath([locale]) -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the path to the 'Default' Command Set.</p>
<p>Parameters:</p>
<ul>
<li><code>locale</code> - The optional locale to use. Defaults to the <a href="#currentLocale">current locale</a>.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The 'Default' Command Set path, or <code>nil</code> if an error occurred</li>
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
                <td><code>cp.apple.finalcutpro:effects() -&gt; EffectsBrowser</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the EffectsBrowser instance, whether it is in the primary or secondary window.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>the EffectsBrowser</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="eventViewer">
            <a name="//apple_ref/cpp/Method/eventViewer" class="dashAnchor"></a>
            <h5><a href="#eventViewer">eventViewer</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro:eventViewer() -&gt; Event Viewer</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the Event Viewer instance, whether it is in the primary or secondary window.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>the Event Viewer</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="exportDialog">
            <a name="//apple_ref/cpp/Method/exportDialog" class="dashAnchor"></a>
            <h5><a href="#exportDialog">exportDialog</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro:exportDialog() -&gt; exportDialog object</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the Final Cut Pro Export Dialog Box</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The Final Cut Pro Export Dialog Box</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="fullScreenWindow">
            <a name="//apple_ref/cpp/Method/fullScreenWindow" class="dashAnchor"></a>
            <h5><a href="#fullScreenWindow">fullScreenWindow</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro:fullScreenWindow() -&gt; fullScreenWindow object</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the Final Cut Pro Full Screen Window</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The Full Screen Playback Window</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="generators">
            <a name="//apple_ref/cpp/Method/generators" class="dashAnchor"></a>
            <h5><a href="#generators">generators</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro:generators() -&gt; GeneratorsBrowser</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the GeneratorsBrowser instance, whether it is in the primary or secondary window.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>the GeneratorsBrowser</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="getCommandShortcuts">
            <a name="//apple_ref/cpp/Method/getCommandShortcuts" class="dashAnchor"></a>
            <h5><a href="#getCommandShortcuts">getCommandShortcuts</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.getCommandShortcuts(id) -&gt; table of hs.commands.shortcut</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Finds a shortcut from the Active Command Set with the specified ID and returns a table
of <code>hs.commands.shortcut</code>s for the specified command, or <code>nil</code> if it doesn't exist.</p>
<p>Parameters:</p>
<ul>
<li>id - The unique ID for the command.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The array of shortcuts, or <code>nil</code> if no command exists with the specified <code>id</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="getPath">
            <a name="//apple_ref/cpp/Method/getPath" class="dashAnchor"></a>
            <h5><a href="#getPath">getPath</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro:getPath() -&gt; string or nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Path to Final Cut Pro Application</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A string containing Final Cut Pro's filesystem path, or nil if Final Cut Pro's path could not be determined.</li>
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
                <td><code>cp.apple.finalcutpro:hide() -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Hides Final Cut Pro</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The FCP instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="importXML">
            <a name="//apple_ref/cpp/Method/importXML" class="dashAnchor"></a>
            <h5><a href="#importXML">importXML</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro:importXML(path) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Imports an XML file into Final Cut Pro</p>
<p>Parameters:</p>
<ul>
<li>path = Path to XML File</li>
</ul>
<p>Returns:</p>
<ul>
<li>A boolean value indicating whether the AppleScript succeeded or not</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="inspector">
            <a name="//apple_ref/cpp/Method/inspector" class="dashAnchor"></a>
            <h5><a href="#inspector">inspector</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro:inspector() -&gt; Inspector</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the Inspector instance from the primary window</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>the Inspector</li>
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
                <td><code>cp.apple.finalcutpro:isSupportedLocale(locale) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks if the provided <code>locale</code> is supported by the app.</p>
<p>Parameters:</p>
<ul>
<li><code>language</code>   - The <code>cp.i18n.localeID</code> or string code. E.g. "en" or "zh_CN"</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the locale is supported.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="keysWithString">
            <a name="//apple_ref/cpp/Method/keysWithString" class="dashAnchor"></a>
            <h5><a href="#keysWithString">keysWithString</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro:keysWithString(string[, lang]) -&gt; {string}</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Looks up an application string and returns an array of keys that match. It will take into account current language the app is running in, or use <code>lang</code> if provided.</p>
<p>Parameters:</p>
<ul>
<li><code>string</code> - The string to look up.</li>
<li><code>lang</code>   - The language (defaults to current FCPX language).</li>
</ul>
<p>Returns:</p>
<ul>
<li>The array of keys with a matching string.</li>
</ul>
<p>Notes:</p>
<ul>
<li>This method may be very inefficient, since it has to search through every possible key/value pair to find matches. It is not recommended that this is used in production.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="keywordEditor">
            <a name="//apple_ref/cpp/Method/keywordEditor" class="dashAnchor"></a>
            <h5><a href="#keywordEditor">keywordEditor</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro:keywordEditor() -&gt; keywordEditor object</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the Final Cut Pro Keyword Editor</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The Final Cut Pro Keyword Editor</li>
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
                <td><code>cp.apple.finalcutpro:launch([waitSeconds]) -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Launches Final Cut Pro, or brings it to the front if it was already running.</p>
<p>Parameters:</p>
<ul>
<li>waitSeconds  - if provided, we will wait for up to the specified seconds for the launch to complete.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The FCP instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="libraries">
            <a name="//apple_ref/cpp/Method/libraries" class="dashAnchor"></a>
            <h5><a href="#libraries">libraries</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro:libraries() -&gt; LibrariesBrowser</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the LibrariesBrowser instance, whether it is in the primary or secondary window.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>the LibrariesBrowser</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="media">
            <a name="//apple_ref/cpp/Method/media" class="dashAnchor"></a>
            <h5><a href="#media">media</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro:media() -&gt; MediaBrowser</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the MediaBrowser instance, whether it is in the primary or secondary window.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>the MediaBrowser</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="mediaImport">
            <a name="//apple_ref/cpp/Method/mediaImport" class="dashAnchor"></a>
            <h5><a href="#mediaImport">mediaImport</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro:mediaImport() -&gt; mediaImport object</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the Final Cut Pro Media Import Window</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The Final Cut Pro Media Import Window</li>
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
                <td><code>cp.apple.finalcutpro:menu() -&gt; cp.app.menu</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the <code>cp.app.menu</code> for FCP.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.app.menu</code> for the app.</li>
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
                <td><code>cp.apple.finalcutpro:notifier() -&gt; cp.ui.notifier</code></td>
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
          <section id="openLibrary">
            <a name="//apple_ref/cpp/Method/openLibrary" class="dashAnchor"></a>
            <h5><a href="#openLibrary">openLibrary</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro:openLibrary(path) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Attempts to open a file at the specified absolute <code>path</code>.</p>
<p>Parameters:</p>
<ul>
<li>path  - The path to the FCP Library to open.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successful, or <code>false</code> if not.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="performShortcut">
            <a name="//apple_ref/cpp/Method/performShortcut" class="dashAnchor"></a>
            <h5><a href="#performShortcut">performShortcut</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro:performShortcut(whichShortcut) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Performs a Final Cut Pro Shortcut</p>
<p>Parameters:</p>
<ul>
<li>whichShortcut - As per the Command Set name</li>
</ul>
<p>Returns:</p>
<ul>
<li>true if successful otherwise false</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="plugins">
            <a name="//apple_ref/cpp/Method/plugins" class="dashAnchor"></a>
            <h5><a href="#plugins">plugins</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro:plugins() -&gt; cp.apple.finalcutpro.plugins</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the plugins manager for the app.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The plugins manager.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="preferencesWindow">
            <a name="//apple_ref/cpp/Method/preferencesWindow" class="dashAnchor"></a>
            <h5><a href="#preferencesWindow">preferencesWindow</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro:preferencesWindow() -&gt; preferenceWindow object</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the Final Cut Pro Preferences Window</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The Preferences Window</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="primaryWindow">
            <a name="//apple_ref/cpp/Method/primaryWindow" class="dashAnchor"></a>
            <h5><a href="#primaryWindow">primaryWindow</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro:primaryWindow() -&gt; primaryWindow object</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the Final Cut Pro Preferences Window</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The Primary Window</li>
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
                <td><code>cp.apple.finalcutpro:quit([waitSeconds]) -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Quits Final Cut Pro, if it's running.</p>
<p>Parameters:</p>
<ul>
<li>waitSeconds      - The number of seconds to wait for the quit to complete.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The FCP instance.</li>
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
                <td><code>cp.apple.finalcutpro:restart([waitSeconds]) -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Restart Final Cut Pro, if it is running. If not, nothing happens.</p>
<p>Parameters:</p>
<ul>
<li><code>waitSeconds</code>    - If provided, the number of seconds to wait for the restart to complete.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The FCP instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="scanPlugins">
            <a name="//apple_ref/cpp/Method/scanPlugins" class="dashAnchor"></a>
            <h5><a href="#scanPlugins">scanPlugins</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro:scanPlugins() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Scan Final Cut Pro Plugins</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A MenuBar object</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="secondaryWindow">
            <a name="//apple_ref/cpp/Method/secondaryWindow" class="dashAnchor"></a>
            <h5><a href="#secondaryWindow">secondaryWindow</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro:secondaryWindow() -&gt; secondaryWindow object</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the Final Cut Pro Preferences Window</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The Secondary Window</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="selectLibrary">
            <a name="//apple_ref/cpp/Method/selectLibrary" class="dashAnchor"></a>
            <h5><a href="#selectLibrary">selectLibrary</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro:selectLibrary(title) -&gt; axuielement</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Attempts to select an open library with the specified title.</p>
<p>Parameters:</p>
<ul>
<li>title - The title of the library to select.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The library row <code>axuielement</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="selectMenu">
            <a name="//apple_ref/cpp/Method/selectMenu" class="dashAnchor"></a>
            <h5><a href="#selectMenu">selectMenu</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro:selectMenu(path[, options]) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Selects a Final Cut Pro Menu Item based on the list of menu titles in English.</p>
<p>Parameters:</p>
<ul>
<li><code>path</code>       - The list of menu items you'd like to activate, for example:
<pre><code>    select("View", "Browser", "as List")</code></pre>
</li>
<li><code>options</code>    - (optional) The table of options. See <code>cp.app.menu:selectMenu(...)</code> for details.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the press was successful.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="selectMenuItem">
            <a name="//apple_ref/cpp/Method/selectMenuItem" class="dashAnchor"></a>
            <h5><a href="#selectMenuItem">selectMenuItem</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro:selectMenuItem(path, options) -&gt; cp.rx.Observable &lt;hs._asm.axuielement&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Selects a Menu Item based on the provided menu path.</p>
<p>Each step on the path can be either one of:</p>
<ul>
<li>a string     - The exact name of the menu item.</li>
<li>a number     - The menu item number, starting from 1.</li>
<li>a function   - Passed one argument - the Menu UI to check - returning <code>true</code> if it matches.</li>
</ul>
<p>Options supported include:</p>
<ul>
<li>locale - The <code>localeID</code> or <code>string</code> for the locale that the path values are in.</li>
<li>pressAll - If <code>true</code>, all menu items will be pressed on the way to the final destination.</li>
<li>timeout - The maximum time to wait for the menu to be available before producing an error. Defaults to 10 seconds.</li>
</ul>
<p>Examples:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">preview</span> <span class="o">=</span> <span class="nb">require</span><span class="p">(</span><span class="s2">&quot;cp.app&quot;</span><span class="p">).</span><span class="n">forBundleID</span><span class="p">(</span><span class="s2">&quot;com.apple.Preview&quot;</span><span class="p">)</span>
<span class="n">preview</span><span class="p">:</span><span class="n">launch</span><span class="p">():</span><span class="n">menu</span><span class="p">():</span><span class="n">selectMenuItem</span><span class="p">({</span><span class="s2">&quot;File&quot;</span><span class="p">,</span> <span class="s2">&quot;Take Screenshot&quot;</span><span class="p">,</span> <span class="s2">&quot;From Entire Screen&quot;</span><span class="p">})</span>
</pre></div>
<p>Parameters:</p>
<ul>
<li>path - The list of menu items you'd like to activate.</li>
<li>options - (optional) The table of options to apply.</li>
</ul>
<p>Returns:</p>
<ul>
<li>An <code>Observable</code> which emits the final menu item, or an error if the selection failed.</li>
</ul>
<p>Notes:</p>
<ul>
<li>The returned <code>Observable</code> will be 'hot', in that it will execute even if no subscription is made to the result. However, it will potentially be run asynchronously, so the actual execution may occur later.</li>
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
                <td><code>cp.apple.finalcutpro:show() -&gt; cp.apple.finalcutpro</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Activate Final Cut Pro, if it is running.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The FCP instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="string">
            <a name="//apple_ref/cpp/Method/string" class="dashAnchor"></a>
            <h5><a href="#string">string</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro:string(key[, locale][, quiet]]) -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Looks up an application string with the specified <code>key</code>.
If no <code>context</code> value is provided, the <a href="#context">current context</a> is used.</p>
<p>Parameters:</p>
<ul>
<li><code>key</code>    - The key to look up.</li>
<li><code>locale</code> - Optional locale to retrieve the key for, if available. May be a <code>string</code> or <code>cp.i18n.localeID</code>.</li>
<li><code>quiet</code>  - Optional boolean, defaults to <code>false</code>. If <code>true</code>, no warnings are logged for missing keys.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The requested string or <code>nil</code> if the application is not running.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="timeline">
            <a name="//apple_ref/cpp/Method/timeline" class="dashAnchor"></a>
            <h5><a href="#timeline">timeline</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro:timeline() -&gt; Timeline</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the Timeline instance, whether it is in the primary or secondary window.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>the Timeline</li>
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
                <td><code>cp.apple.finalcutpro:toolbar() -&gt; PrimaryToolbar</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the Primary Toolbar - the toolbar at the top of the Primary Window.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>the PrimaryToolbar</li>
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
                <td><code>cp.apple.finalcutpro:transitions() -&gt; TransitionsBrowser</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the TransitionsBrowser instance, whether it is in the primary or secondary window.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>the TransitionsBrowser</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="userCommandSetPath">
            <a name="//apple_ref/cpp/Method/userCommandSetPath" class="dashAnchor"></a>
            <h5><a href="#userCommandSetPath">userCommandSetPath</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.userCommandSetPath() -&gt; string or nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the path where User Command Set files are stored.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A path as a string or <code>nil</code> if the folder doesn't exist.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="viewer">
            <a name="//apple_ref/cpp/Method/viewer" class="dashAnchor"></a>
            <h5><a href="#viewer">viewer</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro:viewer() -&gt; Viewer</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the Viewer instance, whether it is in the primary or secondary window.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>the Viewer</li>
</ul>
</td>
              </tr>
            </table>
          </section>
