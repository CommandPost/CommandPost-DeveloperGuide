# [docs](index.md) » cp.config
---

Manage CommandPost's constants and settings.

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
<li><a href="cp.config.dockIconClickCallback.md">cp.config.dockIconClickCallback</a></li>
<li><a href="cp.config.fileDroppedToDockIconCallback.md">cp.config.fileDroppedToDockIconCallback</a></li>
<li><a href="cp.config.shutdownCallback.md">cp.config.shutdownCallback</a></li>
<li><a href="cp.config.textDroppedToDockIconCallback.md">cp.config.textDroppedToDockIconCallback</a></li>
</ul>
<h3>API Overview</h3>
<ul>
<li>Constants - Useful values which cannot be changed</li>
  <ul>
	<li><a href="#appName">appName</a></li>
	<li><a href="#appVersion">appVersion</a></li>
	<li><a href="#assetsPath">assetsPath</a></li>
	<li><a href="#basePath">basePath</a></li>
	<li><a href="#bundledPluginsPath">bundledPluginsPath</a></li>
	<li><a href="#bundleID">bundleID</a></li>
	<li><a href="#cachePath">cachePath</a></li>
	<li><a href="#configPrefix">configPrefix</a></li>
	<li><a href="#developerMode">developerMode</a></li>
	<li><a href="#iconPath">iconPath</a></li>
	<li><a href="#languagePath">languagePath</a></li>
	<li><a href="#menubarIconPath">menubarIconPath</a></li>
	<li><a href="#pluginPaths">pluginPaths</a></li>
	<li><a href="#privacyPolicyURL">privacyPolicyURL</a></li>
	<li><a href="#processID">processID</a></li>
	<li><a href="#scriptPath">scriptPath</a></li>
	<li><a href="#sourceExtensions">sourceExtensions</a></li>
	<li><a href="#sourceWatcher">sourceWatcher</a></li>
	<li><a href="#translationURL">translationURL</a></li>
	<li><a href="#userConfigRootPath">userConfigRootPath</a></li>
	<li><a href="#userPluginsPath">userPluginsPath</a></li>
  </ul>
<li>Variables - Configurable values</li>
  <ul>
	<li><a href="#automaticScriptReloading">automaticScriptReloading</a></li>
  </ul>
<li>Functions - API calls offered directly by the extension</li>
  <ul>
	<li><a href="#application">application</a></li>
	<li><a href="#get">get</a></li>
	<li><a href="#prop">prop</a></li>
	<li><a href="#reset">reset</a></li>
	<li><a href="#set">set</a></li>
	<li><a href="#unwatch">unwatch</a></li>
	<li><a href="#watch">watch</a></li>
  </ul>
<li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
  <ul>
	<li><a href="#frontmost">frontmost</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Constants</h4>
  <section id="appName">
	<h5><a href="#appName">appName</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.config.appName -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The name of the Application</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="appVersion">
	<h5><a href="#appVersion">appVersion</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.config.appVersion -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Prefix used for Configuration Settings</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="assetsPath">
	<h5><a href="#assetsPath">assetsPath</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.config.assetsPath -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Path to where Application Assets are stored</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="basePath">
	<h5><a href="#basePath">basePath</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.config.basePath -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Path to where the Extensions &amp; Plugins folders are stored.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="bundledPluginsPath">
	<h5><a href="#bundledPluginsPath">bundledPluginsPath</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.config.bundledPluginsPath -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The path to bundled plugins</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="bundleID">
	<h5><a href="#bundleID">bundleID</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.config.bundleID -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Application's Bundle ID</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="cachePath">
	<h5><a href="#cachePath">cachePath</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.config.cachePath -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The path to the CommandPost Cache folder.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="configPrefix">
	<h5><a href="#configPrefix">configPrefix</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.config.configPrefix -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Prefix used for Configuration Settings</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="developerMode">
	<h5><a href="#developerMode">developerMode</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.config.developerMode &lt;cp.prop: boolean&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>When <code>true</code>, the app is in developer mode.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="iconPath">
	<h5><a href="#iconPath">iconPath</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.config.iconPath -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Path to the Application Icon</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="languagePath">
	<h5><a href="#languagePath">languagePath</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.config.languagePath -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Path to the Languages Folder</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="menubarIconPath">
	<h5><a href="#menubarIconPath">menubarIconPath</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.config.menubarIconPath -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Path to the Menubar Application Icon</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="pluginPaths">
	<h5><a href="#pluginPaths">pluginPaths</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.config.pluginPaths -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Table of Plugins Paths. Earlier entries take precedence.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="privacyPolicyURL">
	<h5><a href="#privacyPolicyURL">privacyPolicyURL</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.config.privacyPolicyURL -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>URL for Privacy Policy</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="processID">
	<h5><a href="#processID">processID</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.config.processID -&gt; number</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Application's Process ID</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="scriptPath">
	<h5><a href="#scriptPath">scriptPath</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.config.scriptPath -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Path to where Application Scripts are stored</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="sourceExtensions">
	<h5><a href="#sourceExtensions">sourceExtensions</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.config.sourceExtensions -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Extensions for files which will trigger a reload when modified.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="sourceWatcher">
	<h5><a href="#sourceWatcher">sourceWatcher</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.config.sourceWatcher -&gt; SourceWatcher</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>A <code>cp.sourcewatcher</code> that will watch for source files and reload CommandPost if any change.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="translationURL">
	<h5><a href="#translationURL">translationURL</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.config.translationURL -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>URL for Translations</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="userConfigRootPath">
	<h5><a href="#userConfigRootPath">userConfigRootPath</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.config.userConfigRootPath -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The path to user configuration folders</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="userPluginsPath">
	<h5><a href="#userPluginsPath">userPluginsPath</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.config.userPluginsPath -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The path to user plugins</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Variables</h4>
  <section id="automaticScriptReloading">
	<h5><a href="#automaticScriptReloading">automaticScriptReloading</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.config.automaticScriptReloading &lt;cp.prop: boolean&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Automatic Script Reloading.</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Functions</h4>
  <section id="application">
	<h5><a href="#application">application</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.config.application() -&gt; hs.application object</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the Application as a hs.application object</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>hs.application object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="get">
	<h5><a href="#get">get</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.config.get(key[, defaultValue]) -&gt; string or boolean or number or nil or table or binary data</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Loads a setting</p>
<p>Parameters:</p>
<ul>
<li>key - A string containing the name of the setting</li>
<li>defaultValue - A default value if the setting doesn't already exist</li>
</ul>
<p>Returns:</p>
<ul>
<li>The value of the setting</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="prop">
	<h5><a href="#prop">prop</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.config.prop(key[, defaultValue]) -&gt; cp.prop</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a <code>cp.prop</code> instance connected to the value of the specified key. When the value is modified, it will be notified.</p>
<p>Parameters:</p>
<ul>
<li><code>key</code>             - The configuration setting key.</li>
<li><code>defaultValue</code>    - The default value if the key has not been set.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A <code>cp.prop</code> instance for the key.</li>
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
		<td><code>cp.config.reset()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Resets all the settings for the Application</p>
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
  <section id="set">
	<h5><a href="#set">set</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.config.set(key, value)</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Saves a setting with common datatypes</p>
<p>Parameters:</p>
<ul>
<li><code>key</code>        - A string containing the name of the setting</li>
<li><code>value</code>      - An optional value for the setting. Valid datatypes are:<ul>
<li>string</li>
<li>number</li>
<li>boolean</li>
<li>nil</li>
<li>table (which may contain any of the same valid datatypes)</li>
</ul>
</li>
<li>if no value is provided, it is assumed to be nil</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
<p>Notes:</p>
<ul>
<li>This function cannot set dates or raw data types</li>
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
		<td><code>cp.config.unwatch(id)</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Unregisters the watcher with the specified ID.</p>
<p>Parameters:</p>
<ul>
<li><code>id</code>     - The ID, originally returned from the <code>watch</code> function.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if a watcher with the ID existed and was successfully removed.</li>
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
		<td><code>cp.config.watch(events) -&gt; id</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Watches for config events.</p>
<p>Parameters:</p>
<ul>
<li><code>events</code> - a table containing functions for each event to watch for.</li>
</ul>
<p>Returns:</p>
<ul>
<li>a unique ID that can be used to <code>unwatch</code>.</li>
</ul>
<p>Notes:</p>
<ul>
<li>Supported events:
** <code>reset()</code>   - occurs after CommandPost's settings are reset.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Fields</h4>
  <section id="frontmost">
	<h5><a href="#frontmost">frontmost</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.config.frontmost &lt;cp.prop: boolean; read-only&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns whether or not the Application is frontmost.</p>
</td>
	  </tr>
	</table>
  </section>
