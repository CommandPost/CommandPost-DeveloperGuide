# [docs](index.md) » plugins.core.menu.manager
---

Menu Manager Plugin.

<style type="text/css">
	a { text-decoration: none; }
	a:hover { text-decoration: underline; }
	th { background-color: #DDDDDD; vertical-align: top; padding: 3px; }
	td { width: 100%; background-color: #EEEEEE; vertical-align: top; padding: 3px; }
	table { width: 100% ; border: 1px solid #0; text-align: left; }
	section > table table td { width: 0; }
</style>
<link rel="stylesheet" href="../../css/docs.css" type="text/css" media="screen" />
<h3>Submodules</h3>
<ul>
<li><a href="plugins.core.menu.manager.section.md">plugins.core.menu.manager.section</a></li>
</ul>
<h3>API Overview</h3>
<ul>
<li>Variables - Configurable values</li>
  <ul>
	<li><a href="#rootSection">rootSection</a></li>
	<li><a href="#titleSuffix">titleSuffix</a></li>
  </ul>
<li>Functions - API calls offered directly by the extension</li>
  <ul>
	<li><a href="#addSection">addSection</a></li>
	<li><a href="#addTitleSuffix">addTitleSuffix</a></li>
	<li><a href="#disable">disable</a></li>
	<li><a href="#enable">enable</a></li>
	<li><a href="#generateMenuTable">generateMenuTable</a></li>
	<li><a href="#init">init</a></li>
	<li><a href="#updateMenubarIcon">updateMenubarIcon</a></li>
  </ul>
<li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
  <ul>
	<li><a href="#displayMenubarAsIcon">displayMenubarAsIcon</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Variables</h4>
  <section id="rootSection">
	<h5><a href="#rootSection">rootSection</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.menu.manager.rootSection() -&gt; section</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>A new Root Section</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="titleSuffix">
	<h5><a href="#titleSuffix">titleSuffix</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.menu.manager.titleSuffix() -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Table of Title Suffix's</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Functions</h4>
  <section id="addSection">
	<h5><a href="#addSection">addSection</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.menu.manager.addSection(priority) -&gt; section</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new menu section, which can have items and sub-menus added to it.</p>
<p>Parameters:</p>
<ul>
<li>priority - The priority order of menu items created in the section relative to other sections.</li>
</ul>
<p>Returns:</p>
<ul>
<li>section - The section that was created.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="addTitleSuffix">
	<h5><a href="#addTitleSuffix">addTitleSuffix</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.menu.manager.addTitleSuffix(fnTitleSuffix)</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Allows you to add a custom Suffix to the Menubar Title</p>
<p>Parameters:</p>
<ul>
<li>fnTitleSuffix - A function that returns a single string</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="disable">
	<h5><a href="#disable">disable</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.menu.manager.disable(priority) -&gt; menubaritem</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Removes the menu from the system menu bar.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>the menubaritem</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="enable">
	<h5><a href="#enable">enable</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.menu.manager.enable(priority) -&gt; menubaritem</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the previously removed menu back to the system menu bar.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>the menubaritem</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="generateMenuTable">
	<h5><a href="#generateMenuTable">generateMenuTable</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.menu.manager.generateMenuTable()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Generates the Menu Table</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The Menu Table</li>
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
		<td><code>plugins.core.menu.manager.init() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Initialises the module.</p>
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
  <section id="updateMenubarIcon">
	<h5><a href="#updateMenubarIcon">updateMenubarIcon</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.menu.manager.updateMenubarIcon(priority) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Updates the Menubar Icon</p>
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
  <section id="displayMenubarAsIcon">
	<h5><a href="#displayMenubarAsIcon">displayMenubarAsIcon</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.menu.manager.displayMenubarAsIcon &lt;cp.prop: boolean&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>If <code>true</code>, the menubar item will be the app icon. If not, it will be the app name.</p>
</td>
	  </tr>
	</table>
  </section>
