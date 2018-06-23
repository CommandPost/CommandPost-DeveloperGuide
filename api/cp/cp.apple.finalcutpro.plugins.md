# [docs](index.md) » cp.apple.finalcutpro.plugins
---

Scans an entire system for Final Cut Pro Effects, Generators, Titles & Transitions.

Usage:
```lua
    require("cp.apple.finalcutpro"):plugins():scan()
```

<style type="text/css">
	a { text-decoration: none; }
	a:hover { text-decoration: underline; }
	th { background-color: #DDDDDD; vertical-align: top; padding: 3px; }
	td { width: 100%; background-color: #EEEEEE; vertical-align: top; padding: 3px; }
	table { width: 100% ; border: 1px solid #0; text-align: left; }
	section > table table td { width: 0; }
</style>
<link rel="stylesheet" href="../../css/docs.css" type="text/css" media="screen" />
<h3>Submodules</h3>
<ul>
<li><a href="cp.apple.finalcutpro.plugins.guiscan.md">cp.apple.finalcutpro.plugins.guiscan</a></li>
</ul>
<h3>API Overview</h3>
<ul>
<li>Constants - Useful values which cannot be changed</li>
  <ul>
	<li><a href="#appBuiltinPlugins">appBuiltinPlugins</a></li>
	<li><a href="#appEdelEffects">appEdelEffects</a></li>
	<li><a href="#audioUnitsCache">audioUnitsCache</a></li>
	<li><a href="#coreAudioPreferences">coreAudioPreferences</a></li>
	<li><a href="#types">types</a></li>
  </ul>
<li>Variables - Configurable values</li>
  <ul>
	<li><a href="#outputReport">outputReport</a></li>
  </ul>
<li>Functions - API calls offered directly by the extension</li>
  <ul>
	<li><a href="#clearCaches">clearCaches</a></li>
	<li><a href="#new">new</a></li>
	<li><a href="#scan">scan</a></li>
	<li><a href="#scanned">scanned</a></li>
	<li><a href="#scanSystemAudioUnits">scanSystemAudioUnits</a></li>
	<li><a href="#scanUserEffectsPresets">scanUserEffectsPresets</a></li>
  </ul>
<li>Methods - API calls which can only be made on an object returned by a constructor</li>
  <ul>
	<li><a href="#app">app</a></li>
	<li><a href="#audioEffects">audioEffects</a></li>
	<li><a href="#effectBundleStrings">effectBundleStrings</a></li>
	<li><a href="#effectStrings">effectStrings</a></li>
	<li><a href="#generators">generators</a></li>
	<li><a href="#init">init</a></li>
	<li><a href="#ofType">ofType</a></li>
	<li><a href="#registerPlugin">registerPlugin</a></li>
	<li><a href="#reset">reset</a></li>
	<li><a href="#scanAll">scanAll</a></li>
	<li><a href="#scanAppAudioEffectBundles">scanAppAudioEffectBundles</a></li>
	<li><a href="#scanAppBuiltInPlugins">scanAppBuiltInPlugins</a></li>
	<li><a href="#scanAppEdelEffects">scanAppEdelEffects</a></li>
	<li><a href="#scanAppMotionTemplates">scanAppMotionTemplates</a></li>
	<li><a href="#scanPluginCategoryDirectory">scanPluginCategoryDirectory</a></li>
	<li><a href="#scanPluginsDirectory">scanPluginsDirectory</a></li>
	<li><a href="#scanPluginThemeDirectory">scanPluginThemeDirectory</a></li>
	<li><a href="#scanSystemMotionTemplates">scanSystemMotionTemplates</a></li>
	<li><a href="#scanUserMotionTemplates">scanUserMotionTemplates</a></li>
	<li><a href="#titles">titles</a></li>
	<li><a href="#transitions">transitions</a></li>
	<li><a href="#translateEffectBundle">translateEffectBundle</a></li>
	<li><a href="#unwatch">unwatch</a></li>
	<li><a href="#videoEffects">videoEffects</a></li>
	<li><a href="#watch">watch</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Constants</h4>
  <section id="appBuiltinPlugins">
	<h5><a href="#appBuiltinPlugins">appBuiltinPlugins</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.plugins.appBuiltinPlugins -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Table of built-in plugins</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="appEdelEffects">
	<h5><a href="#appEdelEffects">appEdelEffects</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.plugins.appEdelEffects -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Table of Built-in Soundtrack Pro EDEL Effects.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="audioUnitsCache">
	<h5><a href="#audioUnitsCache">audioUnitsCache</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.plugins.audioUnitsCache -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Path to the Audio Units Cache</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="coreAudioPreferences">
	<h5><a href="#coreAudioPreferences">coreAudioPreferences</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.plugins.coreAudioPreferences -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Core Audio Preferences File Path</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="types">
	<h5><a href="#types">types</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.plugins.types -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Table of the different Motion Template Extensions</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Variables</h4>
  <section id="outputReport">
	<h5><a href="#outputReport">outputReport</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.plugins.outputReport &lt;cp.prop: boolean&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Set this to <code>false</code> via <code>_fcp:plugins():outputReport(false)</code> to disable reporting.</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Functions</h4>
  <section id="clearCaches">
	<h5><a href="#clearCaches">clearCaches</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.plugins.clearCaches() -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Clears any local caches created for tracking the plugins.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the caches have been cleared successfully.</li>
</ul>
<p>Notes:</p>
<ul>
<li>Does not uninstall any of the actual plugins.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="new">
	<h5><a href="#new">new</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.plugins.new(fcp) -&gt; plugins object</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new Plugins Object.</p>
<p>Parameters:</p>
<ul>
<li>fcp - The <code>cp.apple.finalcutpro</code> object</li>
</ul>
<p>Returns:</p>
<ul>
<li>The plugins object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="scan">
	<h5><a href="#scan">scan</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.plugins:scan() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Scans Final Cut Pro for Effects, Transitions, Generators &amp; Titles</p>
<p>Parameters:</p>
<ul>
<li>fcp - the <code>cp.apple.finalcutpro</code> instance</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="scanned">
	<h5><a href="#scanned">scanned</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.plugins.scanned() -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets if the system has been scanned.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> is scanned otherwise <code>false</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="scanSystemAudioUnits">
	<h5><a href="#scanSystemAudioUnits">scanSystemAudioUnits</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.plugins:scanSystemAudioUnits(locale) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Scans for Validated Audio Units, and saves the results to a cache for faster subsequent startup times.</p>
<p>Parameters:</p>
<ul>
<li>locale   - the locale to scan in.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="scanUserEffectsPresets">
	<h5><a href="#scanUserEffectsPresets">scanUserEffectsPresets</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.plugins:scanUserEffectsPresets(locale) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Scans Final Cut Pro Effects Presets</p>
<p>Parameters:</p>
<ul>
<li><code>locale</code>    - The locale to scan for.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Methods</h4>
  <section id="app">
	<h5><a href="#app">app</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.plugins:app() -&gt; plugins</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the <code>cp.apple.finalcutpro</code> object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.apple.finalcutpro</code> object.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="audioEffects">
	<h5><a href="#audioEffects">audioEffects</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.plugins:audioEffects([locale]) -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Finds the 'audio effect' plugins.</p>
<p>Parameters:</p>
<ul>
<li><code>locale</code>    - The locale code to search for (e.g. "en"). Defaults to the current FCPX langauge.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table of the available plugins.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="effectBundleStrings">
	<h5><a href="#effectBundleStrings">effectBundleStrings</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.plugins:effectBundleStrings() -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns all the Effect Bundle Strings.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The effect bundle strings in a table.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="effectStrings">
	<h5><a href="#effectStrings">effectStrings</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.plugins:effectStrings() -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a table of Effects Strings.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table of effect strings.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="generators">
	<h5><a href="#generators">generators</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.plugins:generators([locale]) -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Finds the 'generator' plugins.</p>
<p>Parameters:</p>
<ul>
<li><code>locale</code>    - The locale code to search for (e.g. "en"). Defaults to the current FCPX langauge.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table of the available plugins.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="init">
	<h5><a href="#init">init</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.plugins:init() -&gt; plugins</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Initialises the module.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The plugins object.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="ofType">
	<h5><a href="#ofType">ofType</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.plugins:ofType(type[, locale]) -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Finds the plugins of the specified type (<code>types.videoEffect</code>, etc.) and if provided, locale.</p>
<p>Parameters:</p>
<ul>
<li><code>type</code>        - The plugin type. See <code>types</code> for the complete list.</li>
<li><code>locale</code>    - The locale code to search for (e.g. "en"). Defaults to the current FCPX langauge.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table of the available plugins of the specified type.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="registerPlugin">
	<h5><a href="#registerPlugin">registerPlugin</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.plugins:registerPlugin(path, type, categoryName, themeName, pluginName, locale) -&gt; plugin</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Registers a plugin with the specified details.</p>
<p>Parameters:</p>
<ul>
<li><code>path</code>           - The path to the plugin directory.</li>
<li><code>type</code>           - The type of plugin</li>
<li><code>categoryName</code>   - The category name, in the specified locale.</li>
<li><code>themeName</code>      - The theme name, in the specified locale. May be <code>nil</code> if not in a theme.</li>
<li><code>pluginName</code>     - The plugin name, in the specified locale.</li>
<li><code>locale</code>         - The <code>cp.i18n.localeID</code> or string code for same (e.g. "en", "fr", "de")</li>
</ul>
<p>Returns:</p>
<ul>
<li>The plugin object.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="reset">
	<h5><a href="#reset">reset</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.plugins:reset() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Resets all the cached plugins.</p>
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
  <section id="scanAll">
	<h5><a href="#scanAll">scanAll</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.plugins:scanAll() -&gt; nil</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Scans all supported locales, loading them into memory.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>Nothing</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="scanAppAudioEffectBundles">
	<h5><a href="#scanAppAudioEffectBundles">scanAppAudioEffectBundles</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.plugins:scanAppAudioEffectBundles() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Scans the Audio Effect Bundles directories.</p>
<p>Parameters:</p>
<ul>
<li>directoryPath - Directory to scan</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="scanAppBuiltInPlugins">
	<h5><a href="#scanAppBuiltInPlugins">scanAppBuiltInPlugins</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.plugins:scanAppBuiltInPlugins([locale]) -&gt; None</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Scan Built In Plugins.</p>
<p>Parameters:</p>
<ul>
<li><code>locale</code>    - The <code>cp.i18n.localeID</code> code to search for. Defaults to the current FCPX langauge.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="scanAppEdelEffects">
	<h5><a href="#scanAppEdelEffects">scanAppEdelEffects</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.plugins:scanAppEdelEffects() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Scans for Soundtrack Pro EDEL Effects.</p>
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
  <section id="scanAppMotionTemplates">
	<h5><a href="#scanAppMotionTemplates">scanAppMotionTemplates</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.plugins:scanAppMotionTemplates(locale) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Scans for app-provided Final Cut Pro Plugins.</p>
<p>Parameters:</p>
<ul>
<li><code>locale</code>    - The locale to scan for.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="scanPluginCategoryDirectory">
	<h5><a href="#scanPluginCategoryDirectory">scanPluginCategoryDirectory</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.plugins:scanPluginCategoryDirectory(locale, path, plugin) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Scans a folder as a plugin category folder. The contents will be folders that are either theme folders or actual plugins.</p>
<p>Parameters:</p>
<ul>
<li><code>locale</code>        - The locale to scan with.</li>
<li><code>path</code>            - The path to the plugin type directory</li>
<li><code>plugin</code>      - A table containing the plugin details collected so far.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the folder was scanned successfully.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="scanPluginsDirectory">
	<h5><a href="#scanPluginsDirectory">scanPluginsDirectory</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.plugins:scanPluginsDirectory(locale, path, filter) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Scans a root plugins directory. Plugins directories have a standard structure which comes in two flavours:</p>
<ol>
<li><type>/<plugin name>/<plugin name>.<ext></li>
<li><type>/<group>/<plugin name>/<plugin name>.<ext></li>
<li><type>/<group>/<theme>/<plugin name>/<plugin name>.<ext></li>
</ol>
<p>This is somewhat complicated by 'localization', wherein each of the folder levels may have a <code>.localized</code> extension. If this is the case, it will contain a subfolder called <code>.localized</code>, which in turn contains files which describe the local name for the folder in any number of locales.</p>
<p>This function will drill down through the contents of the specified <code>path</code>, assuming the above structure, and then register any contained plugins in the <code>locale</code> provided. Other locales are ignored, other than some use of English when checking for specific effect types (Effect, Generator, etc.).</p>
<p>Parameters:</p>
<ul>
<li><code>locale</code>   - The locale code to scan for (e.g. "en" or "fr").</li>
<li><code>path</code>       - The path of the root plugin directory to scan.</li>
<li><code>checkFn</code>    - A function which will receive the path being scanned and return <code>true</code> if it should be scanned.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the plugin directory was successfully scanned.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="scanPluginThemeDirectory">
	<h5><a href="#scanPluginThemeDirectory">scanPluginThemeDirectory</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.plugins:scanPluginThemeDirectory(locale, path, plugin) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Scans a folder as a plugin theme folder. The contents will be plugin folders.</p>
<p>Parameters:</p>
<ul>
<li><code>locale</code>        - The locale to scan with.</li>
<li><code>path</code>            - The path to the plugin type directory</li>
<li><code>plugin</code>          - A table containing the plugin details collected so far.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the folder was scanned successfully.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="scanSystemMotionTemplates">
	<h5><a href="#scanSystemMotionTemplates">scanSystemMotionTemplates</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.plugins:scanSystemMotionTemplates(locale) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Scans for system-provided Final Cut Pro Plugins.</p>
<p>Parameters:</p>
<ul>
<li><code>locale</code>    - The locale to scan for.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="scanUserMotionTemplates">
	<h5><a href="#scanUserMotionTemplates">scanUserMotionTemplates</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.plugins:scanUserMotionTemplates(locale) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Scans for user-provided Final Cut Pro Plugins.</p>
<p>Parameters:</p>
<ul>
<li><code>locale</code>    - The locale to scan for.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="titles">
	<h5><a href="#titles">titles</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.plugins:titles([locale]) -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Finds the 'title' plugins.</p>
<p>Parameters:</p>
<ul>
<li><code>locale</code>    - The locale code to search for (e.g. "en"). Defaults to the current FCPX langauge.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table of the available plugins.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="transitions">
	<h5><a href="#transitions">transitions</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.plugins:transitions([locale]) -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Finds the 'transitions' plugins.</p>
<p>Parameters:</p>
<ul>
<li><code>locale</code>    - The locale code to search for (e.g. "en"). Defaults to the current FCPX langauge.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table of the available plugins.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="translateEffectBundle">
	<h5><a href="#translateEffectBundle">translateEffectBundle</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.plugins:translateEffectBundle(input, locale) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Translates an Effect Bundle Item.</p>
<p>Parameters:</p>
<ul>
<li>input - The original name</li>
<li>locale - The locale code you want to attempt to translate to</li>
</ul>
<p>Returns:</p>
<ul>
<li>The translated value for <code>input</code> in the specified locale, if present.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="unwatch">
	<h5><a href="#unwatch">unwatch</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.plugins:unwatch(id) -&gt; watcher</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Unwatches a watcher with a specific ID.</p>
<p>Parameters:</p>
<ul>
<li>id - The ID of the watcher to stop watching.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The watcher object.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="videoEffects">
	<h5><a href="#videoEffects">videoEffects</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.plugins:videoEffects([locale]) -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Finds the 'video effect' plugins.</p>
<p>Parameters:</p>
<ul>
<li><code>locale</code>    - The locale code to search for (e.g. "en"). Defaults to the current FCPX langauge.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table of the available plugins.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="watch">
	<h5><a href="#watch">watch</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.plugins:watch(events) -&gt; watcher</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Adds a watcher for the provided events table.</p>
<p>Parameters:</p>
<ul>
<li>events - A table of events to watch.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The watcher object</li>
</ul>
<p>Notes:</p>
<ul>
<li>The events can be:
<strong> videoEffects</strong> audioEffects
<strong> transitions</strong> titles
** generators</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
