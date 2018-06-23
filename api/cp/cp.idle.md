# [docs](index.md) » cp.idle
---

This library allows tasks to be queue for execution when the computer has
been idle for a specified amount of time. 'Idle' is defined as no keyboard
or mouse movement.

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
	<li><a href="#queue">queue</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="queue">
	<h5><a href="#queue">queue</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.idle.queue(idleSeconds, actionFn[, retryOnError]) -&gt; nothing</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Adds an action to the idle queue, which will be run after the the computer has been idle
for at least the specified number of seconds. It may be longer, if other items are on the queue,
or if other tasks are running in the application.</p>
<p>Parameters:</p>
<ul>
<li><code>idleSeconds</code>     - The number of seconds of idle time must have elapsed run the action</li>
<li><code>actionFn</code>        - The function to execute</li>
<li><code>retryOnError</code>    - Optional. If set to <code>true</code>, the action will try running again if there is an error.</li>
</ul>
<p>Returns:</p>
<ul>
<li>Nothing</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
