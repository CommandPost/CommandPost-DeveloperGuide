# [docs](index.md) » cp.strings.source.plist
---

Loads strings from a `plist` with allowing for a given language variation. Eg:

```lua
local plistSource = require("cp.strings.source.plist").new("/Path/To/Resources/${language}.lproj/MYLocalization.strings")
local value = plistSource:find("en", "AKey")
```

This will load the file for the specified language (replacing `${language}` with `"en"` in the path) and return the value.
Note: This will load the file on each request. To have values cached, use the `cp.strings` module and specify a `plist` as a source.

<style type="text/css">
	a { text-decoration: none; }
	a:hover { text-decoration: underline; }
	th { background-color: #DDDDDD; vertical-align: top; padding: 3px; }
	td { width: 100%; background-color: #EEEEEE; vertical-align: top; padding: 3px; }
	table { width: 100% ; border: 1px solid #0; text-align: left; }
	section > table table td { width: 0; }
</style>
<link rel="stylesheet" href="../../css/docs.css" type="text/css" media="screen" />
<h3>API Overview</h3>
<ul>
<li>Constants - Useful values which cannot be changed</li>
  <ul>
	<li><a href="#defaultCacheSeconds">defaultCacheSeconds</a></li>
  </ul>
<li>Constructors - API calls which return an object, typically one that offers API methods</li>
  <ul>
	<li><a href="#new">new</a></li>
  </ul>
<li>Methods - API calls which can only be made on an object returned by a constructor</li>
  <ul>
	<li><a href="#context">context</a></li>
	<li><a href="#find">find</a></li>
	<li><a href="#findKeys">findKeys</a></li>
	<li><a href="#loadFile">loadFile</a></li>
	<li><a href="#pathToAbsolute">pathToAbsolute</a></li>
	<li><a href="#reset">reset</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Constants</h4>
  <section id="defaultCacheSeconds">
	<h5><a href="#defaultCacheSeconds">defaultCacheSeconds</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.strings.source.plist.defaultCacheSeconds</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The default number of seconds to cache results.</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Constructors</h4>
  <section id="new">
	<h5><a href="#new">new</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.strings.source.plist.new(pathPattern[, cacheSeconds]) -&gt; source</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constructor</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new <code>cp.strings</code> source that loads strings from a plist file.</p>
<p>Parameters:</p>
<ul>
<li><code>pathPattern</code>    - The path to load from. May contain a special <code>${language}</code> marker which will be replace with the provided langauge when searching.</li>
<li><code>cacheSeconds</code>   - (optional) How long in seconds to keep the loaded values cached in memory. Defaults to <a href="#defaultCacheSeconds">defaultCacheSeconds</a></li>
</ul>
<p>Returns:</p>
<ul>
<li>The new plist <code>source</code> instance.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Methods</h4>
  <section id="context">
	<h5><a href="#context">context</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.strings.source.plist:context([context]) -&gt; table | self</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets or sets a context to be set for the source. This typically includes a <code>language</code>, which
provides the default language code, but may have other source-specific properties.
Calling this method may may clear caches, etc.</p>
<p>Eg:</p>
<div class="highlight"><pre><span></span><span class="n">mySource</span><span class="p">:</span><span class="n">context</span><span class="p">({</span><span class="n">language</span> <span class="o">=</span> <span class="s2">&quot;fr&quot;</span><span class="p">})</span> <span class="c1">-- set the default language to French.</span>
</pre></div>
<p>Parameters:</p>
<ul>
<li>context   - A table with values which may be used by the source.</li>
</ul>
<p>Returns:</p>
<ul>
<li>If a new context is provided, the <code>cp.string.source</code> is returned, otherwise the current context table is returned.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="find">
	<h5><a href="#find">find</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.strings.source.plist:find(key[, context]) -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Finds the specified <code>key</code> value in the plist, if the plist can be found, and contains matching key value.</p>
<p>Parameters:</p>
<ul>
<li><code>key</code>        - The key to retrieve from the file.</li>
<li><code>context</code>    - Optional table with additional/alternate context. It will be added to the current context temporarily.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The value of the key, or <code>nil</code> if not found.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="findKeys">
	<h5><a href="#findKeys">findKeys</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.strings.source.plist:findKeys(pattern) -&gt; {string}</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Finds the array of keys who's value matches the pattern in this table. It will check that the pattern matches the beginning of the value.</p>
<p>Parameters:</p>
<ul>
<li>`pattern     - The string pattern to match.</li>
<li><code>context</code>    - An optional additional context for the source.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The array of keys, or <code>{}</code> if none were fround</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="loadFile">
	<h5><a href="#loadFile">loadFile</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.strings.source.plist:loadFile([context]) -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Loads the plist file for the specified context, returning the value as a table.</p>
<p>Parameters:</p>
<ul>
<li><code>context</code>    - The context to determine the absolute path with. This will be added to any values provided in the default <a href="#context">context</a>.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The table for the specified language, or <code>nil</code> if the file doesn't exist.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="pathToAbsolute">
	<h5><a href="#pathToAbsolute">pathToAbsolute</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.strings.source.plist:pathToAbsolute([context]) -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Finds the abolute path to the <code>plist</code> represented by this source for the specified langauge, or <code>nil</code> if it does not exist.</p>
<p>Parameters:</p>
<ul>
<li><code>context</code>    - The context to determine the absolute path with. This will be added to any values provided in the default <a href="#context">context</a>.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The path to the file, or <code>nil</code> if not found.</li>
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
		<td><code>cp.strings.source.plist:reset() -&gt; cp.strings</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Clears any stored key values.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The current <code>cp.strings</code> instance.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
