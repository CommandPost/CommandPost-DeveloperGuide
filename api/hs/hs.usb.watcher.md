# [docs](index.md) » hs.usb.watcher
---

Watch for USB device connection/disconnection events

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
	<li><a href="#start">start</a></li>
	<li><a href="#stop">stop</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Constructors</h4>
  <section id="new">
	<h5><a href="#new">new</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.usb.watcher.new(fn) -&gt; watcher</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constructor</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new watcher for USB device events</p>
<p>Parameters:</p>
<ul>
<li>fn - A function that will be called when a USB device is inserted or removed. The function should accept a single parameter, which is a table containing the following keys:<ul>
<li>eventType - A string containing either "added" or "removed" depending on whether the USB device was connected or disconnected</li>
<li>productName - A string containing the name of the device</li>
<li>vendorName - A string containing the name of the device vendor</li>
<li>vendorID - A number containing the Vendor ID of the device</li>
<li>productID - A number containing the Product ID of the device</li>
</ul>
</li>
</ul>
<p>Returns:</p>
<ul>
<li>A <code>hs.usb.watcher</code> object</li>
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
		<td><code>hs.usb.watcher:start() -&gt; watcher</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Starts the USB watcher</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>hs.usb.watcher</code> object</li>
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
		<td><code>hs.usb.watcher:stop() -&gt; watcher</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Stops the USB watcher</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>hs.usb.watcher</code> object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
