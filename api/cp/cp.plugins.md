# [docs](index.md) » cp.plugins
---

This is a simple plugin manager.

## Functions

It has a few core functions:

### `plugins.init(...)`

This function will load all enabled plugins in the specified 'parent' folders. For example:

```lua
local plugins = require("cp.plugins")
plugins.init("~/Library/Application Support/CommandPost/Plugins")
```

This will load all plugins in the current user's `Library/Application Support/CommandPost/Plugins` folder.

### `cp.plugins.getPluginModule(id)`

Once the plugins have been loaded, the module can be accessed by their ID via the `getPluginModule(id)` function. It will return the module returned by the plugin's `init` function. This can also be done via the default function for the library. Eg:

```lua
plugins("my.plugin.id").doSomething()
```

## Plugin Modules

Plugins typically have two parts:
1. The plugin table, which defines details about the plugin, and
2. The module, or result, which could be anything, which is returned from the `init` function.


A plugin file should return a `plugin` table that allows the plugin to be initialised. The table will look something like this:

```lua
local module = {}

local module.init(otherPlugin)
    -- do stuff with otherPlugin here
end

local plugin = {
    id = "my.plugin.id",
    group = "foo",
    dependencies = {
        ["some.other.plugin"] = "otherPlugin",
    },
}

function plugin.init(dependencies)
   -- do stuff to initialise the module here
   module.init(dependencies.otherPlugin)
   return module
}

function plugin.postInit(dependencies)
   -- do stuff that will happen after all plugins have been initialised.
end
```

As you can see above, plugin module can have a few simple functions and properties. The key ones are:

### `plugin.id`
This is a unique ID for the plugin. It is used to load the plugin externally, as well as to define dependencies between plugins.

### `plugin.group`
This is the group ID for the plugin. This is used to group plugins visually in the Properties panel for Plugins.

### `plugin.required`
This optional property can be specified for plugins which should never be disabled. This should only be set for plugins which will break the application if disabled.

### `plugin.dependencies`

This is a table with the list of other plugins that this plugin requires to be loaded prior to this plugin. Be careful of creating infinite loops of dependencies - we don't check for them currently!

It is defined like so:

```lua
plugin.dependencies = {
    "cp.plugins.myplugin",
    ["cp.plugins.otherplugin"] = "otherPlugin"
}

As you can see, there are two ways of declaring a dependency. The first is with just the plugin ID, the second has an alias.

These can be accessed in the `init` and `postInit` functions like so:

```lua
function plugin.init(dependencies)
   local myPlugin = dependencies["cp.plugins.myplugin"]
   local otherPlugin = dependencies.otherPlugin -- or dependencies["cp.plugins.otherplugin"]
end
```

A plugin will only have its `init` function called after its dependencies have successfully had their `init` functions called. Additionally, if a plugin has a `postInit`, all declared `postInits` for dependencies will have been called prior to the plugin's `postInit` function.

### `function plugin.init(dependencies[, environment]) -> module`

This function is basically required. It will be executed when the plugin is initialised. The `dependencies` parameter is a table containing the list of dependencies that the plugin defined via the `dependencies` property. The `environment` provides access to resources such as images, HTML files, or other lua modules that are bundled with the plugin. See `Simple vs Complex Plugins` below.

As you may have noted, there are two ways to specify a plugin is required. Either by simply specifying it as an 'array' item (the first example) or as a key/value (the second example). Doing the later allows you to specify an alias for the dependency, which can be used in the `init(...)` function, like so:

```lua
local plugin = {}

plugin.dependencies = {
    "cp.plugins.myplugin",
    ["cp.plugins.otherplugin"] = "otherplugin"
}

function plugin.init(dependencies)
    local myplugin = dependencies["cp.plugins.myplugin"]
    local otherplugin = dependencies.otherplugin

    -- do other stuff with the dependencies

    return myinstance
end

return plugin
```

## Simple vs Complex Plugins

There are two types of plugin structures supported. The Simple version is a single `.lua` file that matches the above format for `plugin`. The Complex version is a folder containing an `init.lua` file that matches the above format.

The key advantage of Complex Plugins is that the folder can contain other resources, such as images, HTML templates, or other `.lua` files - including 3rd-party libraries if desired. These can be accessed via two main mechanisms:

1. The second `environment` parameter in the `init` function. This is a [cp.plugins.env](cp.plugins.env.md) table, which provides access to files and templates inside the plugin folder. See the [documentation](cp.plugins.env.md) for details.
2. The standard `require` method will allow loading of `*.lua` files inside the plugin from the `init.lua`.

For example, if you have a file called `foo.lua` in your folder, it can be `required` like so:

```lua
local foo = require("foo")
```

You do not have to know anything about where the plugin folder is stored, or use the plugin ID. Just use the local file path within the plugin. If you have another file in a `foo` folder called `bar.lua`, it can be loaded via:

```lua
local fooBar = require("foo.bar")
```

These modules will not be accessible to other plugins or to the main application. They are only available to code inside the plugin.

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
<li><a href="cp.plugins.env.md">cp.plugins.env</a></li>
<li><a href="cp.plugins.plugin.md">cp.plugins.plugin</a></li>
</ul>
<h3>API Overview</h3>
<ul>
<li>Constants - Useful values which cannot be changed</li>
  <ul>
	<li><a href="#CACHE">CACHE</a></li>
	<li><a href="#SETTINGS_DISABLED">SETTINGS_DISABLED</a></li>
	<li><a href="#SLOW_PLUGIN_WARNING_THRESHOLD">SLOW_PLUGIN_WARNING_THRESHOLD</a></li>
  </ul>
<li>Variables - Configurable values</li>
  <ul>
	<li><a href="#IDS">IDS</a></li>
  </ul>
<li>Functions - API calls offered directly by the extension</li>
  <ul>
	<li><a href="#addDependent">addDependent</a></li>
	<li><a href="#disable">disable</a></li>
	<li><a href="#enable">enable</a></li>
	<li><a href="#getDependents">getDependents</a></li>
	<li><a href="#getPlugin">getPlugin</a></li>
	<li><a href="#getPluginIds">getPluginIds</a></li>
	<li><a href="#getPluginModule">getPluginModule</a></li>
	<li><a href="#getPlugins">getPlugins</a></li>
	<li><a href="#init">init</a></li>
	<li><a href="#initPlugin">initPlugin</a></li>
	<li><a href="#initPlugins">initPlugins</a></li>
	<li><a href="#isDisabled">isDisabled</a></li>
	<li><a href="#loadComplexPlugin">loadComplexPlugin</a></li>
	<li><a href="#loadDependencies">loadDependencies</a></li>
	<li><a href="#loadSimplePlugin">loadSimplePlugin</a></li>
	<li><a href="#postInitPlugin">postInitPlugin</a></li>
	<li><a href="#postInitPlugins">postInitPlugins</a></li>
	<li><a href="#scanDirectory">scanDirectory</a></li>
	<li><a href="#watchPluginPaths">watchPluginPaths</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Constants</h4>
  <section id="CACHE">
	<h5><a href="#CACHE">CACHE</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.plugins.CACHE -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Plugin Cache</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="SETTINGS_DISABLED">
	<h5><a href="#SETTINGS_DISABLED">SETTINGS_DISABLED</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.plugins.SETTINGS_DISABLED -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Plugin Disabled Code</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="SLOW_PLUGIN_WARNING_THRESHOLD">
	<h5><a href="#SLOW_PLUGIN_WARNING_THRESHOLD">SLOW_PLUGIN_WARNING_THRESHOLD</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.plugins.SLOW_PLUGIN_WARNING_THRESHOLD -&gt; number</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Slow Plugin Warning Threshold</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Variables</h4>
  <section id="IDS">
	<h5><a href="#IDS">IDS</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.plugins.IDS -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Plugin Status Codes</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Functions</h4>
  <section id="addDependent">
	<h5><a href="#addDependent">addDependent</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.plugins.addDependent(id) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Adds the <code>dependentPlugin</code> as a dependent of the plugin with the specified id.</p>
<p>Parameters:</p>
<ul>
<li><code>id</code>                 - The plugin package ID.</li>
<li><code>dependentPlugin</code>    - The plugin which is a dependent</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="disable">
	<h5><a href="#disable">disable</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.plugins.disable(id) -&gt; nothing</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Disabled the plugin with the specified ID and reloads the application.</p>
<p>Parameters:</p>
<ul>
<li><code>id</code> - The plugin package ID.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the plugin was disabled, or <code>false</code> if it could not be disabled.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="enable">
	<h5><a href="#enable">enable</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.plugins.enable(id) -&gt; nothing</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Enables the plugin with the specified ID, and reloads the application.</p>
<p>Parameters:</p>
<ul>
<li><code>id</code> - The plugin package ID.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the plugin had been disabled and is now enabled.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getDependents">
	<h5><a href="#getDependents">getDependents</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.plugins.getDependents(pluginId)</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Retrieves the list of dependent plugins for the specified plugin id.</p>
<p>Parameters:</p>
<ul>
<li><code>id</code>      - The plugin ID.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The table of dependents.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getPlugin">
	<h5><a href="#getPlugin">getPlugin</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.plugins.getPlugin(id) -&gt; plugin</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Retrieves a plugin from the cache by ID.</p>
<p>Parameters:</p>
<ul>
<li>id - The ID of the plugin you want to get</li>
</ul>
<p>Returns:</p>
<ul>
<li>The plugin</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getPluginIds">
	<h5><a href="#getPluginIds">getPluginIds</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.plugins.getPluginIds() -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Retrieves an array of the loaded plugin IDs.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>the list of plugin IDs.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getPluginModule">
	<h5><a href="#getPluginModule">getPluginModule</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.plugins.getPluginModule(id) -&gt; value</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns an initialised plugin result with the specified <code>id</code>.</p>
<p>Parameters:</p>
<ul>
<li><code>id</code> - The plugin package ID.</li>
</ul>
<p>Returns:</p>
<ul>
<li>the result of the plugin's <code>init(...)</code> function call.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getPlugins">
	<h5><a href="#getPlugins">getPlugins</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.plugins.getPlugins() -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Retrieves an array of details about the set of loaded plugins.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>the list of plugins.</li>
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
		<td><code>cp.plugins.init(paths) -&gt; cp.plugins</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Initialises the plugin loader to look in the specified file paths for plugins.
Plugins in earlier packages will take precedence over those in later paths, if
there are duplicates.</p>
<p>Eg:</p>
<div class="highlight"><pre><span></span><span class="n">plugins</span><span class="p">.</span><span class="n">init</span><span class="p">({</span><span class="s2">&quot;~/Library/Application Support/CommandPost/Plugins&quot;</span><span class="p">})</span>
</pre></div>
<p>Parameters:</p>
<ul>
<li><code>paths</code> - An array of paths to search for plugins in.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>cp.plugins</code> - The module.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="initPlugin">
	<h5><a href="#initPlugin">initPlugin</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.plugins.initPlugin(id) -&gt; module</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Initialises a specific plugin with the specified path.
The plugin will only be loaded once, and the result of its <code>init(...)</code> function
will be cached for future calls.</p>
<p>Eg:</p>

<pre><code>plugins.initPlugin("cp.plugins.test.helloworld")</code></pre>
<p>Parameters:</p>
<ul>
<li><code>id</code> - The LUA package to look in</li>
</ul>
<p>Returns:</p>
<ul>
<li>the result of the plugin's <code>init(...)</code> function call.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="initPlugins">
	<h5><a href="#initPlugins">initPlugins</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.plugins.initPlugins() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Initialises all registered plugins.</p>
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
  <section id="isDisabled">
	<h5><a href="#isDisabled">isDisabled</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.plugins.isDisabled(id) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Checks if the specified plugin ID is disabled.
Plugins are enabled by default.</p>
<p>Parameters:</p>
<ul>
<li><code>id</code> - The plugin package ID.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the plugin is disabled.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="loadComplexPlugin">
	<h5><a href="#loadComplexPlugin">loadComplexPlugin</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.plugins.loadComplexPlugin(path) -&gt; plugin</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Loads a 'complex' plugin, which is a folder containing an <code>init.lua</code> file.
Complex plugins can also have other resources, accessible via an <code>cp.plugins.env</code> parameter
passed to the <code>init()</code> function. For example, an image stored in the <code>images</code> folder
inside the plugin can be accessed via:</p>
<div class="highlight"><pre><span></span><span class="kr">function</span> <span class="nc">plugin</span><span class="p">.</span><span class="nf">init</span><span class="p">(</span><span class="n">dependencies</span><span class="p">,</span> <span class="n">env</span><span class="p">)</span>
    <span class="kd">local</span> <span class="n">imagePath</span> <span class="o">=</span> <span class="n">env</span><span class="p">:</span><span class="n">pathToAbsolute</span><span class="p">(</span><span class="s2">&quot;image/example.jpg&quot;</span><span class="p">)</span>
<span class="kr">end</span>
</pre></div>
<p>Parameters:</p>
<ul>
<li><code>path</code> - The plugin package ID.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the plugin is successfully post-initialised.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="loadDependencies">
	<h5><a href="#loadDependencies">loadDependencies</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.plugins.loadDependencies(plugin) -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Loads the list of dependencies for the provided plugin.</p>
<p>Parameters:</p>
<ul>
<li><code>plugin</code> - The plugin object</li>
</ul>
<p>Returns:</p>
<ul>
<li>an array of the dependencies required by the plugin, or <code>nil</code> if any could not be loaded.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="loadSimplePlugin">
	<h5><a href="#loadSimplePlugin">loadSimplePlugin</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.plugins.loadSimplePlugin(id) -&gt; plugin</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Loads a 'simple' plugin, where it is defined by a single LUA script.</p>
<p>Parameters:</p>
<ul>
<li><code>path</code> - The plugin package ID.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the plugin is successfully post-initialised.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="postInitPlugin">
	<h5><a href="#postInitPlugin">postInitPlugin</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.plugins.postInitPlugin(id) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Runs any post-initialisation functions declared for the specified plugin ID.
Any dependencies will be post-initialised prior to the plugin being post-initialised.</p>
<p>Parameters:</p>
<ul>
<li><code>id</code> - The plugin package ID.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the plugin is successfully post-initialised.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="postInitPlugins">
	<h5><a href="#postInitPlugins">postInitPlugins</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.plugins.postInitPlugins() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Performs any post-initialisation required for plugins.</p>
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
  <section id="scanDirectory">
	<h5><a href="#scanDirectory">scanDirectory</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.plugins.scanDirectory(directoryPath) -&gt; cp.plugins</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Scans the specified directory and loads any plugins in the directory,
along with any in sub-directories.</p>
<p>Plugins can be simple or complex. Simple plugins are a single <code>*.lua</code> file,
not named <code>init.lua</code>. Complex plugins are folders containing an <code>init.lua</code> file.</p>
<p>Parameters:</p>
<ul>
<li><code>directoryPath</code> - The path to the directory to scan.</li>
</ul>
<p>Returns:</p>
<ul>
<li>boolean - <code>true</code> if the path was loaded successfully, false if there were any issues.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="watchPluginPaths">
	<h5><a href="#watchPluginPaths">watchPluginPaths</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.plugins.watchPluginPaths() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Watches the plugin paths for changes and reloads the  application if any change.</p>
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
