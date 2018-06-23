# [docs](index.md) » cp.just
---

This module provides functions to help with performing tasks which may be
delayed, up to a finite number of loops.

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
	<li><a href="#doUntil">doUntil</a></li>
	<li><a href="#doWhile">doWhile</a></li>
	<li><a href="#wait">wait</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="doUntil">
	<h5><a href="#doUntil">doUntil</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.just.doUntil(actionFn[, timeout[, frequency]]) -&gt; value</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Performs an <code>action</code> function, looping until the result of the function evaluates to <code>true</code> (or a non-nil value).
It will halt after the <code>timeout</code> in seconds after checking every <code>frequency</code> seconds.</p>
<p>Parameters:</p>
<ul>
<li><code>actionFn</code>   - a fuction which is called on each loop. It should return a 'truthy' value.</li>
<li><code>timeout</code>    - (optional) the number of seconds after which we will give up. Defaults to 1 second.</li>
<li><code>frequency</code>  - (optional) the amount of time between checks. Defaults to 1 millisecond.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The last return value of the action function.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="doWhile">
	<h5><a href="#doWhile">doWhile</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.just.doWhile(actionFn[, timeout[, frequency]]) -&gt; value</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Performs an 'action' function, looping while the result of the function evaluates to <code>true</code>.
It will halt after <code>timeout</code> seconds, checking with the specified <code>frequency</code>.</p>
<p>Parameters:</p>
<ul>
<li><code>actionFn</code>   - a fuction which is called on each loop. It should return a 'truthy' value.</li>
<li><code>timeout</code>    - (optional) the number of seconds after which we will give up. Defaults to 1 second.</li>
<li><code>frequency</code>  - (optional) the time between checks. Defaults to 1 millisecond.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The last return value of the action function.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="wait">
	<h5><a href="#wait">wait</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.just.wait(integer) -&gt; nil</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Pauses the application for the specified number of seconds.</p>
<p>Parameters:</p>
<ul>
<li>periodInSeconds - the number of seconds to pause for.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
