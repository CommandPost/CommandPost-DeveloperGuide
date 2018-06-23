# [docs](index.md) » hs.streamdeck
---

Configure/control an Elgato Stream Deck

Please note that in order for this module to work, the official Elgato Stream Deck app should not be running

This module would not have been possible without standing on the shoulders of others:
 * https://github.com/OpenStreamDeck/StreamDeckSharp
 * https://github.com/Lange/node-elgato-stream-deck
 * Hopper

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
	<li><a href="#discoveryCallback">discoveryCallback</a></li>
	<li><a href="#getDevice">getDevice</a></li>
	<li><a href="#init">init</a></li>
	<li><a href="#numDevices">numDevices</a></li>
  </ul>
<li>Methods - API calls which can only be made on an object returned by a constructor</li>
  <ul>
	<li><a href="#buttonCallback">buttonCallback</a></li>
	<li><a href="#firmwareVersion">firmwareVersion</a></li>
	<li><a href="#reset">reset</a></li>
	<li><a href="#serialNumber">serialNumber</a></li>
	<li><a href="#setBrightness">setBrightness</a></li>
	<li><a href="#setButtonColor">setButtonColor</a></li>
	<li><a href="#setButtonImage">setButtonImage</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="discoveryCallback">
	<h5><a href="#discoveryCallback">discoveryCallback</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.streamdeck.discoveryCallback(fn)</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Sets/clears a callback for reacting to device discovery events</p>
<p>Parameters:</p>
<ul>
<li>fn - A function that will be called when a Streaming Deck is connected or disconnected. It should take the following arguments:<ul>
<li>A boolean, true if a device was connected, false if a device was disconnected</li>
<li>An hs.streamdeck object, being the device that was connected/disconnected</li>
</ul>
</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getDevice">
	<h5><a href="#getDevice">getDevice</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.streamdeck.getDevice(num)</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets an hs.streamdeck object for the specified device</p>
<p>Parameters:</p>
<ul>
<li>num - A number that should be within the bounds of the number of connected devices</li>
</ul>
<p>Returns:</p>
<ul>
<li>An hs.streamdeck object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="init">
	<h5><a href="#init">init</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.streamdeck.init(fn)</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Initialises the Stream Deck driver and sets a discovery callback</p>
<p>Parameters:</p>
<ul>
<li>fn - A function that will be called when a Streaming Deck is connected or disconnected. It should take the following arguments:<ul>
<li>A boolean, true if a device was connected, false if a device was disconnected</li>
<li>An hs.streamdeck object, being the device that was connected/disconnected</li>
</ul>
</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
<p>Notes:</p>
<ul>
<li>This function must be called before any other parts of this module are used</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="numDevices">
	<h5><a href="#numDevices">numDevices</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.streamdeck.numDevices()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets the number of Stream Deck devices connected</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A number containing the number of Stream Deck devices attached to the system</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Methods</h4>
  <section id="buttonCallback">
	<h5><a href="#buttonCallback">buttonCallback</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.streamdeck:buttonCallback(fn)</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Sets/clears the button callback function for a deck</p>
<p>Parameters:</p>
<ul>
<li>fn - A function to be called when a button is pressed/released on the stream deck. It should receive three arguments:<ul>
<li>The hs.streamdeck userdata object</li>
<li>A number containing the button that was pressed/released</li>
<li>A boolean indicating whether the button was pressed (true) or released (false)</li>
</ul>
</li>
</ul>
<p>Returns:</p>
<ul>
<li>The hs.streamdeck device</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="firmwareVersion">
	<h5><a href="#firmwareVersion">firmwareVersion</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.streamdeck:firmwareVersion()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets the firmware version of a deck</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A string containing the firmware version of the deck</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="reset">
	<h5><a href="#reset">reset</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.streamdeck:reset()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Resets a deck</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The hs.streamdec object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="serialNumber">
	<h5><a href="#serialNumber">serialNumber</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.streamdeck:serialNumber()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets the serial number of a deck</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A string containing the serial number of the deck</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="setBrightness">
	<h5><a href="#setBrightness">setBrightness</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.streamdeck:setBrightness(brightness)</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Sets the brightness of a deck</p>
<p>Parameters:</p>
<ul>
<li>brightness - A whole number between 0 and 100 indicating the percentage brightness level to set</li>
</ul>
<p>Returns:</p>
<ul>
<li>The hs.streamdeck device</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="setButtonColor">
	<h5><a href="#setButtonColor">setButtonColor</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.streamdeck:setButtonColor(button, color)</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Sets a button on the deck to the specified color</p>
<p>Parameters:</p>
<ul>
<li>button - A number (from 1 to 15) describing which button to set the color on</li>
<li>color - An hs.drawing.color object</li>
</ul>
<p>Returns:</p>
<ul>
<li>The hs.streamdeck object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="setButtonImage">
	<h5><a href="#setButtonImage">setButtonImage</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.streamdeck:setButtonImage(button, image)</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Sets the image of a button on the deck</p>
<p>Parameters:</p>
<ul>
<li>button - A number (from 1 to 15) describing which button to set the image for</li>
<li>image - An hs.image object</li>
</ul>
<p>Returns:</p>
<ul>
<li>The hs.streamdeck object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
