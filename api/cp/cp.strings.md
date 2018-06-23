# [docs](index.md) » cp.strings
---

Provides strings from (potentially) multiple sources, with support for loading from multiple languages.

```lua
local strs = require("cp.strings").new():fromPlist("/Path/To/Resources/${language}.lproj/MYLocalization.strings")
local value = strs:find("en", "AKey")
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
<h3>Submodules</h3>
<ul>
<li><a href="cp.strings.source.md">cp.strings.source</a></li>
</ul>
<h3>API Overview</h3>
<ul>
<li>Constructors - API calls which return an object, typically one that offers API methods</li>
  <ul>
	<li><a href="#new">new</a></li>
  </ul>
<li>Methods - API calls which can only be made on an object returned by a constructor</li>
  <ul>
	<li><a href="#context">context</a></li>
	<li><a href="#find">find</a></li>
	<li><a href="#findInSources">findInSources</a></li>
	<li><a href="#findKeys">findKeys</a></li>
	<li><a href="#findKeysInSources">findKeysInSources</a></li>
	<li><a href="#from">from</a></li>
	<li><a href="#fromPlist">fromPlist</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Constructors</h4>
  <section id="new">
	<h5><a href="#new">new</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.strings.new(context) -&gt; cp.strings</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constructor</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new <code>strings</code> instance. You should add sources with the <a href="#from">from</a> or <a href="#fromPlist">fromPlist</a> methods.</p>
<p>Parameters:</p>
<ul>
<li>context      - The initial context.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The new <code>cp.strings</code></li>
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
		<td><code>cp.strings:context([context]) -&gt; table | self</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets or sets a context to be set for the strings. This typically includes a <code>language</code>, which
provides the default language code, but may have other source-specific properties.
Calling this method may may clear caches, etc.</p>
<p>Eg:</p>
<div class="highlight"><pre><span></span><span class="n">string</span><span class="p">:</span><span class="n">context</span><span class="p">({</span><span class="n">language</span> <span class="o">=</span> <span class="s2">&quot;fr&quot;</span><span class="p">})</span> <span class="c1">-- set the default language to French.</span>
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
		<td><code>cp.strings:find(key[, context[, quiet]) -&gt; string | nil</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Searches for the specified key, caching the result when found.</p>
<p>Parameters:</p>
<ul>
<li><code>key</code>        - The key to retrieve from the file.</li>
<li><code>context</code>    - Optional table with additional/alternate context.</li>
<li><code>quiet</code>      - Optional boolean, defaults to <code>false</code>. If <code>true</code>, no warnings are logged for missing keys.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The value of the key, or <code>nil</code> if not found.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="findInSources">
	<h5><a href="#findInSources">findInSources</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.strings:findInSources(key[, context[, quiet]]) -&gt; string | nil</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Searches directly in the sources for the specified key.</p>
<p>Parameters:</p>
<ul>
<li><code>key</code>        - The key to retrieve from the file.</li>
<li><code>context</code>    - Optional table with additional/alternate context.</li>
<li><code>quiet</code>      - Optional boolean, defaults to <code>false</code>. If <code>true</code>, no warnings are logged for missing keys.</li>
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
		<td><code>cp.strings:findKeys(value[, context]) -&gt; string | nil</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Searches for the list of keys with a matching value, in the specified language.</p>
<p>Parameters:</p>
<ul>
<li><code>value</code>      - The value to search for.</li>
<li><code>context</code>    - The language code to look for (e.g. <code>"en"</code>, or <code>"fr"</code>).</li>
</ul>
<p>Returns:</p>
<ul>
<li>The array of keys, or <code>{}</code> if not found.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="findKeysInSources">
	<h5><a href="#findKeysInSources">findKeysInSources</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.strings:findKeysInSources(value[, context]) -&gt; string | nil</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Searches directly in the sources for the specified key value pattern.</p>
<p>Parameters:</p>
<ul>
<li><code>value</code>      - The value to search for.</li>
<li><code>context</code>    - Optional additional context for the request.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The array of keys, or <code>{}</code> if not found.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="from">
	<h5><a href="#from">from</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.strings:from(source) -&gt; cp.strings</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Adds the source to the strings sources.</p>
<p>Parameters:</p>
<ul>
<li><code>source</code>     - The source to add.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The current <code>cp.strings</code> instance.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="fromPlist">
	<h5><a href="#fromPlist">fromPlist</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.strings:fromPlist(pathPattern) -&gt; cp.strings</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Convenience method for adding a <code>plist</code> source to the strings instance.</p>
<p>Parameters:</p>
<ul>
<li><code>pathPattern</code>    - The path to load from. May contain a special <code>${language}</code> marker which will be replace with the provided langauge when searching.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The current <code>cp.strings</code> instance.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
