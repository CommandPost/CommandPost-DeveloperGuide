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
      <h1><a href="cp.plugins.md">docs</a> &raquo; cp.plugins</h1>
      <p>This is a simple plugin manager.</p>
<h2>Functions</h2>
<p>It has a few core functions:</p>
<h3><code>plugins.init(...)</code></h3>
<p>This function will load all enabled plugins in the specified 'parent' folders. For example:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">plugins</span> <span class="o">=</span> <span class="nb">require</span><span class="p">(</span><span class="s2">&quot;cp.plugins&quot;</span><span class="p">)</span>
<span class="n">plugins</span><span class="p">.</span><span class="n">init</span><span class="p">(</span><span class="s2">&quot;~/Library/Application Support/CommandPost/Plugins&quot;</span><span class="p">)</span>
</pre></div>
<p>This will load all plugins in the current user's <code>Library/Application Support/CommandPost/Plugins</code> folder.</p>
<h3><code>cp.plugins.getPluginModule(id)</code></h3>
<p>Once the plugins have been loaded, the module can be accessed by their ID via the <code>getPluginModule(id)</code> function. It will return the module returned by the plugin's <code>init</code> function. This can also be done via the default function for the library. Eg:</p>
<div class="highlight"><pre><span></span><span class="n">plugins</span><span class="p">(</span><span class="s2">&quot;my.plugin.id&quot;</span><span class="p">).</span><span class="n">doSomething</span><span class="p">()</span>
</pre></div>
<h2>Plugin Modules</h2>
<p>Plugins typically have two parts:</p>
<ol>
<li>The plugin table, which defines details about the plugin, and</li>
<li>The module, or result, which could be anything, which is returned from the <code>init</code> function.</li>
</ol>
<p>A plugin file should return a <code>plugin</code> table that allows the plugin to be initialised. The table will look something like this:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">module</span> <span class="o">=</span> <span class="p">{}</span>

<span class="kd">local</span> <span class="n">module</span><span class="p">.</span><span class="n">init</span><span class="p">(</span><span class="n">otherPlugin</span><span class="p">)</span>
    <span class="c1">-- do stuff with otherPlugin here</span>
<span class="kr">end</span>

<span class="kd">local</span> <span class="n">plugin</span> <span class="o">=</span> <span class="p">{</span>
    <span class="n">id</span> <span class="o">=</span> <span class="s2">&quot;my.plugin.id&quot;</span><span class="p">,</span>
    <span class="n">group</span> <span class="o">=</span> <span class="s2">&quot;foo&quot;</span><span class="p">,</span>
    <span class="n">dependencies</span> <span class="o">=</span> <span class="p">{</span>
        <span class="p">[</span><span class="s2">&quot;some.other.plugin&quot;</span><span class="p">]</span> <span class="o">=</span> <span class="s2">&quot;otherPlugin&quot;</span><span class="p">,</span>
    <span class="p">},</span>
<span class="p">}</span>

<span class="kr">function</span> <span class="nc">plugin</span><span class="p">.</span><span class="nf">init</span><span class="p">(</span><span class="n">dependencies</span><span class="p">)</span>
   <span class="c1">-- do stuff to initialise the module here</span>
   <span class="n">module</span><span class="p">.</span><span class="n">init</span><span class="p">(</span><span class="n">dependencies</span><span class="p">.</span><span class="n">otherPlugin</span><span class="p">)</span>
   <span class="kr">return</span> <span class="n">module</span>
<span class="p">}</span>

<span class="kr">function</span> <span class="nc">plugin</span><span class="p">.</span><span class="nf">postInit</span><span class="p">(</span><span class="n">dependencies</span><span class="p">)</span>
   <span class="c1">-- do stuff that will happen after all plugins have been initialised.</span>
<span class="kr">end</span>
</pre></div>
<p>As you can see above, plugin module can have a few simple functions and properties. The key ones are:</p>
<h3><code>plugin.id</code></h3>
<p>This is a unique ID for the plugin. It is used to load the plugin externally, as well as to define dependencies between plugins.</p>
<h3><code>plugin.group</code></h3>
<p>This is the group ID for the plugin. This is used to group plugins visually in the Properties panel for Plugins.</p>
<h3><code>plugin.required</code></h3>
<p>This optional property can be specified for plugins which should never be disabled. This should only be set for plugins which will break the application if disabled.</p>
<h3><code>plugin.dependencies</code></h3>
<p>This is a table with the list of other plugins that this plugin requires to be loaded prior to this plugin. Be careful of creating infinite loops of dependencies - we don't check for them currently!</p>
<p>It is defined like so:</p>
<div class="highlight"><pre><span></span><span class="n">plugin</span><span class="p">.</span><span class="n">dependencies</span> <span class="o">=</span> <span class="p">{</span>
    <span class="s2">&quot;cp.plugins.myplugin&quot;</span><span class="p">,</span>
    <span class="p">[</span><span class="s2">&quot;cp.plugins.otherplugin&quot;</span><span class="p">]</span> <span class="o">=</span> <span class="s2">&quot;otherPlugin&quot;</span>
<span class="p">}</span>

<span class="n">As</span> <span class="n">you</span> <span class="n">can</span> <span class="n">see</span><span class="p">,</span> <span class="n">there</span> <span class="n">are</span> <span class="n">two</span> <span class="n">ways</span> <span class="n">of</span> <span class="n">declaring</span> <span class="n">a</span> <span class="n">dependency</span><span class="p">.</span> <span class="n">The</span> <span class="n">first</span> <span class="n">is</span> <span class="n">with</span> <span class="n">just</span> <span class="n">the</span> <span class="n">plugin</span> <span class="n">ID</span><span class="p">,</span> <span class="n">the</span> <span class="n">second</span> <span class="n">has</span> <span class="n">an</span> <span class="n">alias</span><span class="p">.</span>

<span class="n">These</span> <span class="n">can</span> <span class="n">be</span> <span class="n">accessed</span> <span class="kr">in</span> <span class="n">the</span> <span class="err">`</span><span class="n">init</span><span class="err">`</span> <span class="ow">and</span> <span class="err">`</span><span class="n">postInit</span><span class="err">`</span> <span class="n">functions</span> <span class="n">like</span> <span class="n">so</span><span class="p">:</span>

<span class="err">```</span><span class="n">lua</span>
<span class="kr">function</span> <span class="nc">plugin</span><span class="p">.</span><span class="nf">init</span><span class="p">(</span><span class="n">dependencies</span><span class="p">)</span>
   <span class="kd">local</span> <span class="n">myPlugin</span> <span class="o">=</span> <span class="n">dependencies</span><span class="p">[</span><span class="s2">&quot;cp.plugins.myplugin&quot;</span><span class="p">]</span>
   <span class="kd">local</span> <span class="n">otherPlugin</span> <span class="o">=</span> <span class="n">dependencies</span><span class="p">.</span><span class="n">otherPlugin</span> <span class="c1">-- or dependencies[&quot;cp.plugins.otherplugin&quot;]</span>
<span class="kr">end</span>
</pre></div>
<p>A plugin will only have its <code>init</code> function called after its dependencies have successfully had their <code>init</code> functions called. Additionally, if a plugin has a <code>postInit</code>, all declared <code>postInits</code> for dependencies will have been called prior to the plugin's <code>postInit</code> function.</p>
<h3><code>function plugin.init(dependencies[, environment]) -&gt; module</code></h3>
<p>This function is basically required. It will be executed when the plugin is initialised. The <code>dependencies</code> parameter is a table containing the list of dependencies that the plugin defined via the <code>dependencies</code> property. The <code>environment</code> provides access to resources such as images, HTML files, or other lua modules that are bundled with the plugin. See <code>Simple vs Complex Plugins</code> below.</p>

<pre><code>
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

return plugin</code></pre>
<h2>Simple vs Complex Plugins</h2>
<p>There are two types of plugin structures supported. The Simple version is a single <code>.lua</code> file that matches the above format for <code>plugin</code>. The Complex version is a folder containing an <code>init.lua</code> file that matches the above format.</p>
<p>The key advantage of Complex Plugins is that the folder can contain other resources, such as images, HTML templates, or other <code>.lua</code> files - including 3rd-party libraries if desired. These can be accessed via two main mechanisms:</p>
<ol>
<li>The second <code>environment</code> parameter in the <code>init</code> function. This is a <a href="cp.plugins.env.md">cp.plugins.env</a> table, which provides access to files and templates inside the plugin folder. See the <a href="cp.plugins.env.md">documentation</a> for details.</li>
<li>The standard <code>require</code> method will allow loading of <code>*.lua</code> files inside the plugin from the <code>init.lua</code>.</li>
</ol>
<p>For example, if you have a file called <code>foo.lua</code> in your folder, it can be <code>required</code> like so:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">foo</span> <span class="o">=</span> <span class="nb">require</span><span class="p">(</span><span class="s2">&quot;foo&quot;</span><span class="p">)</span>
</pre></div>
<p>You do not have to know anything about where the plugin folder is stored, or use the plugin ID. Just use the local file path within the plugin. If you have another file in a <code>foo</code> folder called <code>bar.lua</code>, it can be loaded via:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">fooBar</span> <span class="o">=</span> <span class="nb">require</span><span class="p">(</span><span class="s2">&quot;foo.bar&quot;</span><span class="p">)</span>
</pre></div>
<p>These modules will not be accessible to other plugins or to the main application. They are only available to code inside the plugin.</p>

      </header>
        <h3>Submodules</h3>
        <ul>
        <li><a href="cp.plugins.env.html">cp.plugins.env</a></li>
        <li><a href="cp.plugins.plugin.html">cp.plugins.plugin</a></li>
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
            <a name="//apple_ref/cpp/Constant/CACHE" class="dashAnchor"></a>
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
            <a name="//apple_ref/cpp/Constant/SETTINGS_DISABLED" class="dashAnchor"></a>
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
            <a name="//apple_ref/cpp/Constant/SLOW_PLUGIN_WARNING_THRESHOLD" class="dashAnchor"></a>
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
            <a name="//apple_ref/cpp/Variable/IDS" class="dashAnchor"></a>
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
            <a name="//apple_ref/cpp/Function/addDependent" class="dashAnchor"></a>
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
            <a name="//apple_ref/cpp/Function/disable" class="dashAnchor"></a>
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
            <a name="//apple_ref/cpp/Function/enable" class="dashAnchor"></a>
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
            <a name="//apple_ref/cpp/Function/getDependents" class="dashAnchor"></a>
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
            <a name="//apple_ref/cpp/Function/getPlugin" class="dashAnchor"></a>
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
            <a name="//apple_ref/cpp/Function/getPluginIds" class="dashAnchor"></a>
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
            <a name="//apple_ref/cpp/Function/getPluginModule" class="dashAnchor"></a>
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
            <a name="//apple_ref/cpp/Function/getPlugins" class="dashAnchor"></a>
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
            <a name="//apple_ref/cpp/Function/init" class="dashAnchor"></a>
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
            <a name="//apple_ref/cpp/Function/initPlugin" class="dashAnchor"></a>
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
            <a name="//apple_ref/cpp/Function/initPlugins" class="dashAnchor"></a>
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
            <a name="//apple_ref/cpp/Function/isDisabled" class="dashAnchor"></a>
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
            <a name="//apple_ref/cpp/Function/loadComplexPlugin" class="dashAnchor"></a>
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
            <a name="//apple_ref/cpp/Function/loadDependencies" class="dashAnchor"></a>
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
            <a name="//apple_ref/cpp/Function/loadSimplePlugin" class="dashAnchor"></a>
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
            <a name="//apple_ref/cpp/Function/postInitPlugin" class="dashAnchor"></a>
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
            <a name="//apple_ref/cpp/Function/postInitPlugins" class="dashAnchor"></a>
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
            <a name="//apple_ref/cpp/Function/scanDirectory" class="dashAnchor"></a>
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
            <a name="//apple_ref/cpp/Function/watchPluginPaths" class="dashAnchor"></a>
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
