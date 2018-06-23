# [docs](index.md) » plugins.core.watchfolders.manager.panel
---

Watch Folder Panel Manager.

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
	<li><a href="#addButton">addButton</a></li>
	<li><a href="#addCheckbox">addCheckbox</a></li>
	<li><a href="#addContent">addContent</a></li>
	<li><a href="#addHandler">addHandler</a></li>
	<li><a href="#addHeading">addHeading</a></li>
	<li><a href="#addParagraph">addParagraph</a></li>
	<li><a href="#addPassword">addPassword</a></li>
	<li><a href="#addSelect">addSelect</a></li>
	<li><a href="#addTextbox">addTextbox</a></li>
	<li><a href="#generateContent">generateContent</a></li>
	<li><a href="#getToolbarItem">getToolbarItem</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Constructors</h4>
  <section id="new">
	<h5><a href="#new">new</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.watchfolders.manager.panel.new(priority, id) -&gt; panel object</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constructor</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Constructs a new panel with the specified priority and ID.</p>
<p>Parameters:</p>
<ul>
<li>priority - Defines the order in which the panel appears.</li>
<li>id       - The unique ID for the panel.</li>
<li>webview  - The webview the panel is attached to.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A panel object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Methods</h4>
  <section id="addButton">
	<h5><a href="#addButton">addButton</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.watchfolders.manager.panel:addButton(priority, params, itemFn, customWidth) -&gt; panel</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Adds a button to the panel with the specified <code>priority</code> and <code>params</code>.</p>
<p>Parameters:</p>
<ul>
<li><code>priority</code> - The priority number for the button.</li>
<li><code>params</code> - The set of parameters for the button.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The panel.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="addCheckbox">
	<h5><a href="#addCheckbox">addCheckbox</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.watchfolders.manager.panel:addCheckbox(priority, params) -&gt; panel</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Adds a checkbox to the panel with the specified <code>priority</code> and <code>params</code>.</p>
<p>Parameters:</p>
<ul>
<li><code>priority</code>   - The priority number for the checkbox.</li>
<li><code>params</code>     - The set of parameters for the checkbox.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The panel.</li>
</ul>
<p>Notes:</p>
<ul>
<li>The <code>params</code> can contain the following fields:
<strong> <code>id</code>        - (optional) The unique ID. If none is provided, one will be generated.</strong> <code>name</code>      - (optional) The name of the checkbox field.
<strong> <code>label</code>     - (optional) The text label to display after the checkbox.</strong> <code>onchange</code>  - (optional) a function that will get called when the checkbox value changes. It will be passed two parameters, <code>id</code> and <code>params</code>, the latter of which is a table containing the <code>value</code> and <code>checked</code> values of the checkbox.
** <code>class</code>     - (optional) the CSS class list to apply to the checkbox.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="addContent">
	<h5><a href="#addContent">addContent</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.watchfolders.manager.panel:addContent(priority, content[, escaped]) -&gt; panel</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Adds the specified <code>content</code> to the panel, with the specified <code>priority</code> order.</p>
<p>Parameters:</p>
<ul>
<li><code>priority</code> - the priority order of the content.</li>
<li><code>content</code> - a value that can be converted to a string.</li>
<li><code>escaped</code> - if <code>true</code>, the content will be escaped.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The panel object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="addHandler">
	<h5><a href="#addHandler">addHandler</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.watchfolders.manager.panel:addHandler(event, id, handlerFn, keys) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Adds a handler</p>
<p>Parameters:</p>
<ul>
<li>event - The JavaScript event as string</li>
<li>id - The ID as string</li>
<li>handlerFn - The handler function</li>
<li>keys - Table of keys</li>
</ul>
<p>Returns:</p>
<ul>
<li>The panel object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="addHeading">
	<h5><a href="#addHeading">addHeading</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.watchfolders.manager.panel:addHeading(priority, text, level) -&gt; panel</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Adds a heading to the panel with the specified <code>priority</code> and <code>text</code>.</p>
<p>Parameters:</p>
<ul>
<li><code>priority</code> - The priority number for the heading.</li>
<li><code>text</code> - The content of the heading as a string.</li>
<li><code>level</code> - The level of the heading.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The panel object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="addParagraph">
	<h5><a href="#addParagraph">addParagraph</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.watchfolders.manager.panel:addParagraph(priority, content[, escaped[, class]]) -&gt; panel</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Adds a paragraph to the panel with the specified <code>priority</code> and <code>content</code>.</p>
<p>Parameters:</p>
<ul>
<li><code>priority</code> - The priority number for the paragraph.</li>
<li><code>content</code> - The content you want to include as a string.</li>
<li><code>escaped</code> - Whether or not the HTML is escaped as a boolean.</li>
<li><code>class</code> - The class name as a string.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The panel object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="addPassword">
	<h5><a href="#addPassword">addPassword</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.watchfolders.manager.panel:addPassword(priority, params) -&gt; panel</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Adds a password textbox to the panel with the specified <code>priority</code> and <code>params</code>.</p>
<p>Parameters:</p>
<ul>
<li><code>priority</code>   - The priority number for the password.</li>
<li><code>params</code>     - The set of parameters for the password.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The panel.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="addSelect">
	<h5><a href="#addSelect">addSelect</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.watchfolders.manager.panel:addSelect(priority, params) -&gt; panel</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Adds a select to the panel with the specified <code>priority</code> and <code>params</code>.</p>
<p>Parameters:</p>
<ul>
<li><code>priority</code> - The priority number for the select.</li>
<li><code>params</code> - The set of parameters for the select.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The panel.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="addTextbox">
	<h5><a href="#addTextbox">addTextbox</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.watchfolders.manager.panel:addTextbox(priority, params) -&gt; panel</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Adds a textbox to the panel with the specified <code>priority</code> and <code>params</code>.</p>
<p>Parameters:</p>
<ul>
<li><code>priority</code>   - The priority number for the textbox.</li>
<li><code>params</code>     - The set of parameters for the textbox.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The panel.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="generateContent">
	<h5><a href="#generateContent">generateContent</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.watchfolders.manager.panel:generateContent() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets generated toolbar content</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A string of generated content</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getToolbarItem">
	<h5><a href="#getToolbarItem">getToolbarItem</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.watchfolders.manager.panel:getToolbarItem() -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a Toolbar Item</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>Table of Toolbar Item Values</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
