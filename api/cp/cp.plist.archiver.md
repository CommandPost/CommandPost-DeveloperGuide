# [docs](index.md) » cp.plist.archiver
---

Supports 'defrosting' a table which is made up from an 'NSKeyArchiver' record.

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
	<li><a href="#unarchive">unarchive</a></li>
	<li><a href="#unarchiveFile">unarchiveFile</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="unarchive">
	<h5><a href="#unarchive">unarchive</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.plist.archiver.unarchive(archive, defrostFn) -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Unarchives a LUA table which was archived into a plist using the NSKeyedArchiver.</p>
<p>Parameters:</p>
<ul>
<li><code>archive</code>        - the table containing the archive plist as a table</li>
<li><code>defrostFn</code>  - (optional) a function which will be passed an object with a '$class' entry</li>
</ul>
<p>Returns:</p>
<ul>
<li>The unarchived plist table</li>
</ul>
<p>Notes:</p>
<ul>
<li><p>A 'defrost' function can be provided, which will be called whenever a table with a '$class'
structure is present. It will receive the table and the classname and should either return a modified value
if the class was handled, or <code>nil</code> if it was unable to handle the class. Eg:</p>

<pre><code>local result = archiver.unarchive(archiveData, function(frozen, classname)
    if classname == "XXMyClass" then
        return MyClass:new(frozen.foo, frozen.bar)
    end
        return nil
end)</code></pre>
</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="unarchiveFile">
	<h5><a href="#unarchiveFile">unarchiveFile</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.plist.archiver.unarchiveFile(filename, defrostFn) -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Unarchives a plist file which was archived into a plist using the NSKeyedArchiver.</p>
<p>Parameters:</p>
<ul>
<li><code>filename</code>   - the file containing the archive plist</li>
<li><code>defrostFn</code>  - (optional) a function which will be passed an object with a '$class' entry</li>
</ul>
<p>Returns:</p>
<ul>
<li>The unarchived plist.</li>
</ul>
<p>Notes:</p>
<ul>
<li><p>A 'defrost' function can be provided, which will be called whenever a table with a '$class'
structure is present. It will receive the table and the classname and should either return a modified value
if the class was handled, or <code>nil</code> if it was unable to handle the class. Eg:</p>

<pre><code>local result = archiver.unarchiveFile(filename, function(frozen, classname)
    if classname == "XXMyClass" then
        return MyClass:new(frozen.foo, frozen.bar)
    end
        return nil
end)</code></pre>
</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
