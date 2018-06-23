# [docs](index.md) » cp.deferred
---

This extension makes it simple to defer multiple actions after a delay from the initial execution.
 Unlike `hs.timer.delayed`, the delay will not be extended
with subsequent `run()` calls, but the delay will trigger again if `run()` is called again later.

For example:

```lua
local update = deferred.new(1) -- defer 1 second
:action(function() print("Updated!"") end)
-- do something
update()
-- do something else
update()
-- one second after the inital call to `update()`, one "Updated!" is printed.
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
<li>Constructors - API calls which return an object, typically one that offers API methods</li>
  <ul>
	<li><a href="#new">new</a></li>
  </ul>
<li>Methods - API calls which can only be made on an object returned by a constructor</li>
  <ul>
	<li><a href="#action">action</a></li>
	<li><a href="#delay">delay</a></li>
	<li><a href="#run">run</a></li>
	<li><a href="#secondsRemaining">secondsRemaining</a></li>
	<li><a href="#stop">stop</a></li>
	<li><a href="#waiting">waiting</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Constructors</h4>
  <section id="new">
	<h5><a href="#new">new</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.deferred.new(delay) -&gt; cp.deferred</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constructor</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new <code>defer</code> instance, which will trigger any added <code>action</code>s by a set delay after
the initial call to <code>run()</code>.</p>
<p>Parameters:</p>
<ul>
<li>delay     - The number of seconds to delay when <code>run()</code> is initally called.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The new <code>cp.deferred</code> instance.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Methods</h4>
  <section id="action">
	<h5><a href="#action">action</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.deferred:action(actionFn) -&gt; self</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Adds the <code>action</code> the the list that will be called when the timer goes off.
It must be a <code>function</code> (or callable <code>table</code>) with the following signature:</p>
<div class="highlight"><pre><span></span><span class="kr">function</span><span class="p">()</span> <span class="o">-&gt;</span> <span class="kc">nil</span>
</pre></div>
<p>Multiple actions can be added and they will all be called when the delay timer
goes off.</p>
<p>Parameters:</p>
<ul>
<li>The callable action.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="delay">
	<h5><a href="#delay">delay</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.deferred:delay([value]) -&gt; self | number</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Sets/gets the delay period. If no <code>value</code> is provided, the current delay is returned.
If it is provided, then the new delay will be set. If it is currently waiting, then
the wait will be restarted with the new delay.</p>
<p>Parameters:</p>
<ul>
<li>value     - the new delay value.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.deferred</code> instance if a new value is provided, or the current delay if not.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="run">
	<h5><a href="#run">run</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.deferred:run() -&gt; self</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Ensures that the actions will run after the <code>delay</code>.
Multiple calls will not increase the delay from the initial call.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.deferred</code> instance.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="secondsRemaining">
	<h5><a href="#secondsRemaining">secondsRemaining</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.deferred:secondsRemaining() -&gt; number | nil</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the number of seconds until the next execution, or <code>nil</code> if it's not running.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The number of seconds until execution.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="stop">
	<h5><a href="#stop">stop</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.deferred:stop() -&gt; self</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Stops any execution of any deferred actions, if it is currently running.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The deferred timer.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="waiting">
	<h5><a href="#waiting">waiting</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.deferred:waiting() -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Checks if the defer is currently waiting to run.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the deferred action is waiting to execute.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
