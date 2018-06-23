# [docs](index.md) » plugins.finalcutpro.notifications.pushover
---

Pushover Notifications Plugin.

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
	<li><a href="#validateAPIKeys">validateAPIKeys</a></li>
  </ul>
<li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
  <ul>
	<li><a href="#apiValidated">apiValidated</a></li>
	<li><a href="#appAPIKey">appAPIKey</a></li>
	<li><a href="#enabled">enabled</a></li>
	<li><a href="#userAPIKey">userAPIKey</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="init">
	<h5><a href="#init">init</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.notifications.pushover.init() -&gt; none</code></td>
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
		<td><code>plugins.finalcutpro.notifications.pushover.sendNotification(message, [title]) -&gt; none</code></td>
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
<li>[title] - An optional Title for the message as a string.</li>
</ul>
<p>Returns:</p>
<ul>
<li>success - <code>true</code> if successful otherwise <code>false</code></li>
<li>errorMessage - a string containing any error messages</li>
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
		<td><code>plugins.finalcutpro.notifications.pushover.update() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Enables or disables Pushover Notifications depending on the user's preferences.</p>
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
  <section id="validateAPIKeys">
	<h5><a href="#validateAPIKeys">validateAPIKeys</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.notifications.pushover.validateAPIKeys(userKey, appKey) -&gt; success, errorMessage</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Validates a Pushover User &amp; Application API Key</p>
<p>Parameters:</p>
<ul>
<li>userKey - The User API Key as a string</li>
<li>appKey - The Application API Key as a string</li>
</ul>
<p>Returns:</p>
<ul>
<li>success - <code>true</code> if successful otherwise <code>false</code></li>
<li>errorMessage - a string containing any error messages</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Fields</h4>
  <section id="apiValidated">
	<h5><a href="#apiValidated">apiValidated</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.notifications.pushover.apiValidated &lt;cp.prop: boolean&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Whether or not the API keys have been validated.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="appAPIKey">
	<h5><a href="#appAPIKey">appAPIKey</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.notifications.pushover.appAPIKey &lt;cp.prop: string&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Application API Key</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="enabled">
	<h5><a href="#enabled">enabled</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.notifications.pushover.enabled &lt;cp.prop: boolean&gt;</code></td>
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
  <section id="userAPIKey">
	<h5><a href="#userAPIKey">userAPIKey</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.notifications.pushover.userAPIKey &lt;cp.prop: string&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>User API Key</p>
</td>
	  </tr>
	</table>
  </section>
