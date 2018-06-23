# [docs](index.md) » plugins.core.streamdeck.manager
---

Elgato Stream Deck Manager Plugin.

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
	<li><a href="#DEFAULT_GROUP">DEFAULT_GROUP</a></li>
	<li><a href="#FILE_NAME">FILE_NAME</a></li>
	<li><a href="#FOLDER_NAME">FOLDER_NAME</a></li>
  </ul>
<li>Variables - Configurable values</li>
  <ul>
	<li><a href="#maxItems">maxItems</a></li>
  </ul>
<li>Functions - API calls offered directly by the extension</li>
  <ul>
	<li><a href="#activeGroup">activeGroup</a></li>
	<li><a href="#appWatcherCallback">appWatcherCallback</a></li>
	<li><a href="#buttonCallback">buttonCallback</a></li>
	<li><a href="#clear">clear</a></li>
	<li><a href="#discoveryCallback">discoveryCallback</a></li>
	<li><a href="#getAction">getAction</a></li>
	<li><a href="#getActionHandlerID">getActionHandlerID</a></li>
	<li><a href="#getActionTitle">getActionTitle</a></li>
	<li><a href="#getIcon">getIcon</a></li>
	<li><a href="#getLabel">getLabel</a></li>
	<li><a href="#groupStatus">groupStatus</a></li>
	<li><a href="#init">init</a></li>
	<li><a href="#start">start</a></li>
	<li><a href="#update">update</a></li>
	<li><a href="#updateAction">updateAction</a></li>
	<li><a href="#updateIcon">updateIcon</a></li>
	<li><a href="#updateLabel">updateLabel</a></li>
  </ul>
<li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
  <ul>
	<li><a href="#enabled">enabled</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Constants</h4>
  <section id="DEFAULT_GROUP">
	<h5><a href="#DEFAULT_GROUP">DEFAULT_GROUP</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.streamdeck.manager.DEFAULT_GROUP -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The default group.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="FILE_NAME">
	<h5><a href="#FILE_NAME">FILE_NAME</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.streamdeck.manager.FILE_NAME -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>File name of settings file.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="FOLDER_NAME">
	<h5><a href="#FOLDER_NAME">FOLDER_NAME</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.streamdeck.manager.FOLDER_NAME -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Folder Name where settings file is contained.</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Variables</h4>
  <section id="maxItems">
	<h5><a href="#maxItems">maxItems</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.streamdeck.manager.maxItems -&gt; number</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The maximum number of Stream Deck items per group.</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Functions</h4>
  <section id="activeGroup">
	<h5><a href="#activeGroup">activeGroup</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.streamdeck.manager.activeGroup() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the active group.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>Returns the active group or <code>manager.defaultGroup</code> as a string.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="appWatcherCallback">
	<h5><a href="#appWatcherCallback">appWatcherCallback</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.streamdeck.manager.appWatcherCallback(name, event, app) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Stream Deck App Watcher Callback</p>
<p>Parameters:</p>
<ul>
<li>name - A string containing the name of the application</li>
<li>event - An event type</li>
<li>app - An <code>hs.application</code> object representing the application, or <code>nil</code> if the application couldn't be found</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="buttonCallback">
	<h5><a href="#buttonCallback">buttonCallback</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.streamdeck.manager.buttonCallback(object, buttonID, pressed) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Stream Deck Button Callback</p>
<p>Parameters:</p>
<ul>
<li>object - The <code>hs.streamdeck</code> userdata object</li>
<li>buttonID - A number containing the button that was pressed/released</li>
<li>pressed - A boolean indicating whether the button was pressed (<code>true</code>) or released (<code>false</code>)</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="clear">
	<h5><a href="#clear">clear</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.streamdeck.manager.clear() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Clears the Stream Deck items.</p>
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
  <section id="discoveryCallback">
	<h5><a href="#discoveryCallback">discoveryCallback</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.streamdeck.manager.discoveryCallback(connected, object) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Stream Deck Discovery Callback</p>
<p>Parameters:</p>
<ul>
<li>connected - A boolean, <code>true</code> if a device was connected, <code>false</code> if a device was disconnected</li>
<li>object - An <code>hs.streamdeck</code> object, being the device that was connected/disconnected</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getAction">
	<h5><a href="#getAction">getAction</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.streamdeck.manager.getAction(button, group) -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a specific Stream Deck Action.</p>
<p>Parameters:</p>
<ul>
<li>button - Button ID as string</li>
<li>group - Group ID as string</li>
</ul>
<p>Returns:</p>
<ul>
<li>Action as string</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getActionHandlerID">
	<h5><a href="#getActionHandlerID">getActionHandlerID</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.streamdeck.manager.getActionHandlerID(button, group) -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a specific Stream Deck Action Handler ID.</p>
<p>Parameters:</p>
<ul>
<li>button - Button ID as string</li>
<li>group - Group ID as string</li>
</ul>
<p>Returns:</p>
<ul>
<li>Action as string</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getActionTitle">
	<h5><a href="#getActionTitle">getActionTitle</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.streamdeck.manager.getActionTitle(button, group) -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a specific Stream Deck Action Title.</p>
<p>Parameters:</p>
<ul>
<li>button - Button ID as string</li>
<li>group - Group ID as string</li>
</ul>
<p>Returns:</p>
<ul>
<li>Action as string</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getIcon">
	<h5><a href="#getIcon">getIcon</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.streamdeck.manager.getIcon(button, group) -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a specific Stream Deck Icon.</p>
<p>Parameters:</p>
<ul>
<li>button - Button ID as string</li>
<li>group - Group ID as string</li>
</ul>
<p>Returns:</p>
<ul>
<li>Icon data as string</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getLabel">
	<h5><a href="#getLabel">getLabel</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.streamdeck.manager.getLabel(button, group) -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a specific Stream Deck Label.</p>
<p>Parameters:</p>
<ul>
<li>button - Button ID as string</li>
<li>group - Group ID as string</li>
</ul>
<p>Returns:</p>
<ul>
<li>Label as string</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="groupStatus">
	<h5><a href="#groupStatus">groupStatus</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.streamdeck.manager.groupStatus(groupID, status) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Updates a group's visibility status.</p>
<p>Parameters:</p>
<ul>
<li>groupID - the group you want to update as a string.</li>
<li>status - the status of the group as a boolean.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
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
		<td><code>plugins.core.streamdeck.manager.init(deps, env) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Initialises the Stream Deck Plugin</p>
<p>Parameters:</p>
<ul>
<li>deps - Dependencies Table</li>
<li>env - Environment Table</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
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
		<td><code>plugins.core.streamdeck.manager.start() -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Stops the Stream Deck Plugin</p>
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
  <section id="update">
	<h5><a href="#update">update</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.streamdeck.manager.update() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Updates the Stream Deck.</p>
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
  <section id="updateAction">
	<h5><a href="#updateAction">updateAction</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.streamdeck.manager.updateAction(button, group, action) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Updates a Stream Deck action.</p>
<p>Parameters:</p>
<ul>
<li>button - Button ID as string</li>
<li>group - Group ID as string</li>
<li>action - Action as string</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="updateIcon">
	<h5><a href="#updateIcon">updateIcon</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.streamdeck.manager.updateIcon(button, group, icon) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Updates a Stream Deck icon.</p>
<p>Parameters:</p>
<ul>
<li>button - Button ID as string</li>
<li>group - Group ID as string</li>
<li>icon - Icon Data as string</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="updateLabel">
	<h5><a href="#updateLabel">updateLabel</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.streamdeck.manager.updateLabel(button, group, label) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Updates a Stream Deck action.</p>
<p>Parameters:</p>
<ul>
<li>button - Button ID as string</li>
<li>group - Group ID as string</li>
<li>label - Label as string</li>
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
		<td><code>plugins.core.streamdeck.manager.enabled &lt;cp.prop: boolean&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Enable or disable Stream Deck Support.</p>
</td>
	  </tr>
	</table>
  </section>
