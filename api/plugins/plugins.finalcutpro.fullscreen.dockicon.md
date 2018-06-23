# [docs](index.md) » plugins.finalcutpro.fullscreen.dockicon
---

Manages the CommandPost dock icon when FCP is full-screen.
[Due to some quirkiness](https://github.com/Hammerspoon/hammerspoon/issues/1184)
in how macOS manages full-screen windows, it seems that we need to make
CP 'dockless' when an app we are working with goes full-screen. Otherwise
our drawing/canvas images will not display correctly.

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
<li>Variables - Configurable values</li>
  <ul>
	<li><a href="#dockIconEnabled">dockIconEnabled</a></li>
	<li><a href="#fcpActiveFullScreen">fcpActiveFullScreen</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Variables</h4>
  <section id="dockIconEnabled">
	<h5><a href="#dockIconEnabled">dockIconEnabled</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.fullscreen.dockicon.dockIconEnabled &lt;cp.prop: boolean; read-only; live&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>If <code>true</code> the CommandPost dock icon should be hidden.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="fcpActiveFullScreen">
	<h5><a href="#fcpActiveFullScreen">fcpActiveFullScreen</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.fullscreen.dockicon.fcpActiveFullScreen &lt;cp.prop: boolean; read-only; live&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>If <code>true</code> FCP is full-screen and the frontmost app.</p>
</td>
	  </tr>
	</table>
  </section>
