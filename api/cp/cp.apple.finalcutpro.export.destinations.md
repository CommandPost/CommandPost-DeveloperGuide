# [docs](index.md) » cp.apple.finalcutpro.export.destinations
---

Provides access to the list of Share Destinations configured for the user.

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
	<li><a href="#DESTINATIONS_FILE">DESTINATIONS_FILE</a></li>
	<li><a href="#DESTINATIONS_PATH">DESTINATIONS_PATH</a></li>
	<li><a href="#PREFERENCES_PATH">PREFERENCES_PATH</a></li>
  </ul>
<li>Functions - API calls offered directly by the extension</li>
  <ul>
	<li><a href="#details">details</a></li>
	<li><a href="#indexOf">indexOf</a></li>
	<li><a href="#names">names</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Constants</h4>
  <section id="DESTINATIONS_FILE">
	<h5><a href="#DESTINATIONS_FILE">DESTINATIONS_FILE</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.export.destinations.DESTINATIONS_FILE -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The Destinations File.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="DESTINATIONS_PATH">
	<h5><a href="#DESTINATIONS_PATH">DESTINATIONS_PATH</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.export.destinations.DESTINATIONS_PATH -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The Destinations Path.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="PREFERENCES_PATH">
	<h5><a href="#PREFERENCES_PATH">PREFERENCES_PATH</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.export.destinations.PREFERENCES_PATH -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The Preferences Path</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Functions</h4>
  <section id="details">
	<h5><a href="#details">details</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.export.destinations.details() -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the full details of the current Share Destinations as a table.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The table of Share Destinations.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="indexOf">
	<h5><a href="#indexOf">indexOf</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.export.destinations.indexOf(name) -&gt; number</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the index of the Destination with the specified name, or <code>nil</code> if not found.</p>
<p>Parameters:</p>
<ul>
<li><code>name</code>   - The name of the Destination</li>
</ul>
<p>Returns:</p>
<ul>
<li>The index of the named Destination, or <code>nil</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="names">
	<h5><a href="#names">names</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.export.destinations.names() -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns an array of the names of destinations, in their current order.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The table of Share Destination names.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
