# [docs](index.md) » hs.application.watcher
---

Watch for application launch/terminate events

This module is based primarily on code from the previous incarnation of Mjolnir by [Markus Engelbrecht](https://github.com/mgee) and [Steven Degutis](https://github.com/sdegutis/).

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
	<li><a href="#activated">activated</a></li>
	<li><a href="#deactivated">deactivated</a></li>
	<li><a href="#hidden">hidden</a></li>
	<li><a href="#launched">launched</a></li>
	<li><a href="#launching">launching</a></li>
	<li><a href="#terminated">terminated</a></li>
	<li><a href="#unhidden">unhidden</a></li>
  </ul>
<li>Constructors - API calls which return an object, typically one that offers API methods</li>
  <ul>
	<li><a href="#new">new</a></li>
  </ul>
<li>Methods - API calls which can only be made on an object returned by a constructor</li>
  <ul>
	<li><a href="#start">start</a></li>
	<li><a href="#stop">stop</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Constants</h4>
  <section id="activated">
	<h5><a href="#activated">activated</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.application.watcher.activated</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>An application has been activated (i.e. given keyboard/mouse focus)</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="deactivated">
	<h5><a href="#deactivated">deactivated</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.application.watcher.deactivated</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>An application has been deactivated (i.e. lost keyboard/mouse focus)</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="hidden">
	<h5><a href="#hidden">hidden</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.application.watcher.hidden</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>An application has been hidden</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="launched">
	<h5><a href="#launched">launched</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.application.watcher.launched</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>An application has been launched</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="launching">
	<h5><a href="#launching">launching</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.application.watcher.launching</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>An application is in the process of being launched</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="terminated">
	<h5><a href="#terminated">terminated</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.application.watcher.terminated</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>An application has been terminated</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="unhidden">
	<h5><a href="#unhidden">unhidden</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.application.watcher.unhidden</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>An application has been unhidden</p>
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
		<td><code>hs.application.watcher.new(fn) -&gt; watcher</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constructor</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates an application event watcher</p>
<p>Parameters:</p>
<ul>
<li>fn - A function that will be called when application events happen. It should accept three parameters:<ul>
<li>A string containing the name of the application</li>
<li>An event type (see the constants defined above)</li>
<li>An <code>hs.application</code> object representing the application, or nil if the application couldn't be found</li>
</ul>
</li>
</ul>
<p>Returns:</p>
<ul>
<li>An <code>hs.application.watcher</code> object</li>
</ul>
<p>Notes:</p>
<ul>
<li>If the function is called with an event type of <code>hs.application.watcher.terminated</code> then the application name parameter will be <code>nil</code> and the <code>hs.application</code> parameter, will only be useful for getting the UNIX process ID (i.e. the PID) of the application</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Methods</h4>
  <section id="start">
	<h5><a href="#start">start</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.application.watcher:start()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Starts the application watcher</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>hs.application.watcher</code> object</li>
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
		<td><code>hs.application.watcher:stop()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Stops the application watcher</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>hs.application.watcher</code> object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
