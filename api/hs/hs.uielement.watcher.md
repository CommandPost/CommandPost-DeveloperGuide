# [docs](index.md) » hs.uielement.watcher
---

Watch for events on certain UI elements (including windows and applications)

You can watch the following events:
### Application-level events
See hs.application.watcher for more events you can watch.
* hs.uielement.watcher.applicationActivated: The current application switched to this one.
* hs.uielement.watcher.applicationDeactivated: The current application is no longer this one.
* hs.uielement.watcher.applicationHidden: The application was hidden.
* hs.uielement.watcher.applicationShown: The application was shown.

#### Focus change events
These events are watched on the application level, but send the relevant child element to the handler.
* hs.uielement.watcher.mainWindowChanged: The main window of the application was changed.
* hs.uielement.watcher.focusedWindowChanged: The focused window of the application was changed. Note that the application may not be activated itself.
* hs.uielement.watcher.focusedElementChanged: The focused UI element of the application was changed.

### Window-level events
* hs.uielement.watcher.windowCreated: A window was created. You should watch for this event on the application, or the parent window.
* hs.uielement.watcher.windowMoved: The window was moved.
* hs.uielement.watcher.windowResized: The window was resized.
* hs.uielement.watcher.windowMinimized: The window was minimized.
* hs.uielement.watcher.windowUnminimized: The window was unminimized.

### Element-level events
These work on all UI elements, including windows.
* hs.uielement.watcher.elementDestroyed: The element was destroyed.
* hs.uielement.watcher.titleChanged: The element's title was changed.

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
<li>Methods - API calls which can only be made on an object returned by a constructor</li>
  <ul>
	<li><a href="#element">element</a></li>
	<li><a href="#start">start</a></li>
	<li><a href="#stop">stop</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Methods</h4>
  <section id="element">
	<h5><a href="#element">element</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.uielement.watcher:element() -&gt; object</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the element the watcher is watching.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The element the watcher is watching.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="start">
	<h5><a href="#start">start</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.uielement.watcher:start(events) -&gt; hs.uielement.watcher</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Tells the watcher to start watching for the given list of events.</p>
<p>Parameters:</p>
<ul>
<li>An array of events to be watched for.</li>
</ul>
<p>Returns:</p>
<ul>
<li>hs.uielement.watcher</li>
</ul>
<p>Notes:</p>
<ul>
<li>See hs.uielement.watcher for a list of events. You may also specify arbitrary event names as strings.</li>
<li>Does nothing if the watcher has already been started. To start with different events, stop it first.</li>
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
		<td><code>hs.uielement.watcher:stop() -&gt; hs.uielement.watcher</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Tells the watcher to stop listening for events.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>hs.uielement.watcher</li>
</ul>
<p>Notes:</p>
<ul>
<li>This is automatically called if the element is destroyed.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
