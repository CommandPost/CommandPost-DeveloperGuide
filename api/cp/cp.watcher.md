# [docs](index.md) » cp.watcher
---

This extension provides support for setting up 'event watchers'.

For example, if you want to allow interested parties to watch for 'update'
events, you might have something like this:

```lua
local thing = {}

thing.watchers = watcher.new('update')

thing.watch(events)
	return thing.watchers:watch(events)
end

thing.update(value)
	thing.value = value
	thing.watchers:notify('update', value)
end
```

Then, your other code could get notifications like so:

```lua
thing.watch({
	update = function(value) print "New value is "..value end
})
```

Then, whenever `thing.update(xxx)` is called, the watcher will output `"New value is xxx"`.

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
	<li><a href="#new">new</a></li>
  </ul>
<li>Methods - API calls which can only be made on an object returned by a constructor</li>
  <ul>
	<li><a href="#events">events</a></li>
	<li><a href="#getCount">getCount</a></li>
	<li><a href="#notify">notify</a></li>
	<li><a href="#unwatch">unwatch</a></li>
	<li><a href="#watch">watch</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="new">
	<h5><a href="#new">new</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.watcher.new(...) -&gt; watcher</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Constructs a new watcher instance.</p>
<p>Parameters:</p>
<ul>
<li><code>...</code> - The list of event name strings supported by the watcher.</li>
</ul>
<p>Returns:</p>
<ul>
<li>a new watcher instance</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Methods</h4>
  <section id="events">
	<h5><a href="#events">events</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.watcher:events()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a list of the event names supported by this watcher.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The table of event names.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getCount">
	<h5><a href="#getCount">getCount</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.watcher:getCount()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the number of watchers currently registered.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The number of watchers.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="notify">
	<h5><a href="#notify">notify</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.watcher:notify(type, ...) -&gt; nil</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Notifies watchers of the specified event type.</p>
<p>Parameters:</p>
<ul>
<li><code>type</code>   - The event type to notify. Must be one of the supported events.</li>
<li><code>...</code>    - These parameters are passed directly to the event watcher functions.</li>
</ul>
<p>Returns:</p>
<ul>
<li>Nothing.</li>
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
		<td><code>cp.watcher:unwatch(id) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Removes the watchers which were added with the specified ID.</p>
<p>Parameters:</p>
<ul>
<li><code>id</code>     - The unique ID returned from <code>watch</code>.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if a watcher with the specified ID exists and was successfully removed.</li>
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
		<td><code>cp.watcher:watch(events) -&gt; id</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Adds a watcher for the specified events.</p>
<p>Parameters:</p>
<ul>
<li><code>events</code>     - A table of functions, one for each event to watch.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A unique ID that can be passed to <code>unwatch</code> to stop watching.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
