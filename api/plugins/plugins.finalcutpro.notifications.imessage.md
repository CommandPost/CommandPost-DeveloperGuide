# [docs](index.md) » plugins.finalcutpro.notifications.imessage
---

iMessage Notifications Plugin.

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
	<li><a href="#init">init</a></li>
	<li><a href="#sendNotification">sendNotification</a></li>
	<li><a href="#update">update</a></li>
  </ul>
<li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
  <ul>
	<li><a href="#enabled">enabled</a></li>
	<li><a href="#target">target</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="init">
	<h5><a href="#init">init</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.notifications.imessage.init() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Initialises the plugin.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="sendNotification">
	<h5><a href="#sendNotification">sendNotification</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.notifications.imessage.sendNotification(message) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Sends a notification.</p>
<p>Parameters:</p>
<ul>
<li>message - The message you want to send as a string.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="update">
	<h5><a href="#update">update</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.notifications.imessage.update() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Enables or disables iMessage Notifications depending on the user's preferences.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Fields</h4>
  <section id="enabled">
	<h5><a href="#enabled">enabled</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.notifications.imessage.enabled &lt;cp.prop: boolean&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Whether or not the plugin has been enabled.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="target">
	<h5><a href="#target">target</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.notifications.imessage.target &lt;cp.prop: string&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>A string containing a mobile number or Apple ID</p>
</td>
	  </tr>
	</table>
  </section>
