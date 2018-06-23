# [docs](index.md) » hs.tabs
---

Place the windows of an application into tabs drawn on its titlebar

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
	<li><a href="#enableForApp">enableForApp</a></li>
	<li><a href="#focusTab">focusTab</a></li>
	<li><a href="#tabWindows">tabWindows</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="enableForApp">
	<h5><a href="#enableForApp">enableForApp</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.tabs.enableForApp(app)</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Places all the windows of an app into one place and tab them</p>
<p>Parameters:</p>
<ul>
<li>app - An <code>hs.application</code> object or the app title</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="focusTab">
	<h5><a href="#focusTab">focusTab</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.tabs.focusTab(app, num)</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Focuses a specific tab of an app</p>
<p>Parameters:</p>
<ul>
<li>app - An <code>hs.application</code> object previously enabled for tabbing</li>
<li>num - A tab number to switch to</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
<p>Notes:</p>
<ul>
<li>If num is higher than the number of tabs, the last tab will be focussed</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="tabWindows">
	<h5><a href="#tabWindows">tabWindows</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.tabs.tabWindows(app)</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets a list of the tabs of a window</p>
<p>Parameters:</p>
<ul>
<li>app - An <code>hs.application</code> object</li>
</ul>
<p>Returns:</p>
<ul>
<li>An array of the tabbed windows of an app in the same order as they would be tabbed</li>
</ul>
<p>Notes:</p>
<ul>
<li>This function can be used when writing tab switchers</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
