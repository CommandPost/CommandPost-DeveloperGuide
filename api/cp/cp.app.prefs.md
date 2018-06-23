# [docs](index.md) » cp.app.prefs
---

Provides access to application preferences, typically stored via `NSUserDefaults` or `CFProperties`.
To access the preferences, simply pass in the Bundle ID (eg. "com.apple.Preview") and it will return
a table whose keys can be accessed or updated, or iterated via `ipairs`.

For example:

```lua
local previewPrefs = require("cp.app.prefs").new("com.apple.Preview")
previewPrefs.MyCustomPreference = "Hello world"
print(previewPrefs.MyCustomPreference) --> "Hello world"

for k,v in pairs(previewPrefs) do
    print(k .. " = " .. tostring(v))
end
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
<h3>API Overview</h3>
<ul>
<li>Functions - API calls offered directly by the extension</li>
  <ul>
	<li><a href="#bundleID">bundleID</a></li>
	<li><a href="#get">get</a></li>
	<li><a href="#is">is</a></li>
	<li><a href="#prop">prop</a></li>
	<li><a href="#set">set</a></li>
	<li><a href="#watch">watch</a></li>
  </ul>
<li>Constructors - API calls which return an object, typically one that offers API methods</li>
  <ul>
	<li><a href="#new">new</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="bundleID">
	<h5><a href="#bundleID">bundleID</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.app.prefs.bundleID(prefs) -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Retrieves the <code>bundleID</code> associated with the <code>cp.app.prefs</code> instance.</p>
<p>Parameters:</p>
<ul>
<li>prefs     - the <code>prefs</code> object to query</li>
</ul>
<p>Returns:</p>
<ul>
<li>The Bundle ID string, or <code>nil</code> if it's not a <code>cp.app.prefs</code>.</li>
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
		<td><code>cp.app.prefs.get(prefs, key[, defaultValue])</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Retrieves the specifed <code>key</code> from the provided <code>prefs</code>.
If there is no current value, the <code>defaultValue</code> is returned.</p>
<p>Parameters:</p>
<ul>
<li>prefs         - The <code>prefs</code> instance.</li>
<li>key           - The key to retrieve.</li>
<li>defaultValue  - The value to return if none is currentl set.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The current value, or <code>defaultValue</code> if not set.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="is">
	<h5><a href="#is">is</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.app.prefs.is(thing) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Checks if the <code>thing</code> is a <code>cp.app.prefs</code> instance.</p>
<p>Parameters:</p>
<ul>
<li>thing     - The value to check</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if if's a <code>prefs</code>, otherwise <code>false</code>.</li>
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
		<td><code>cp.app.prefs.prop(prefs, key[, defaultValue]) -&gt; cp.prop</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Retrieves the <code>cp.prop</code> for the specified key. It can be <code>watched</code> for changes.
Subsequent calls will return the same <code>cp.prop</code> instance.</p>
<p>Parameters:</p>
<ul>
<li>prefs         - The <code>prefs</code> instance.</li>
<li>key           - The key to get/set.</li>
<li>defaultValue  - The value if no default values is currently set.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.prop</code> for the key.</li>
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
		<td><code>cp.app.prefs.set(prefs, key, value) -&gt; nil</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Sets the key/value for the specified <code>prefs</code> instance.</p>
<p>Parameters:</p>
<ul>
<li>prefs     - The <code>prefs</code> instance.</li>
<li>key       - The key to set.</li>
<li>value     - the new value.</li>
</ul>
<p>Returns:</p>
<ul>
<li>Nothing.</li>
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
		<td><code>cp.app.prefs.watch(prefs, watchFn) -&gt; nil</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Adds a watch function which will be notified when the preferences change.
The <code>watchFn</code> is a function which will be passed the <code>prefs</code> when it has been updated.</p>
<p>Parameters:</p>
<ul>
<li>prefs     - The <code>prefs</code> instance to watch.</li>
<li>watchFn   - The function that will get called.</li>
</ul>
<p>Returns:</p>
<ul>
<li>Nothing</li>
</ul>
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
		<td><code>cp.app.prefs.new(bundleID) -&gt; cp.app.prefs</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constructor</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new <code>cp.app.prefs</code> instance, pointing at the specified <code>bundleID</code>.</p>
<p>Parameters:</p>
<ul>
<li>bundleID      The Bundle ID to access preferences for.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A new <code>cp.app.prefs</code> with read/write access to the application's preferences.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
