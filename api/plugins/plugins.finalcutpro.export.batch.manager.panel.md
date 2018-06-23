# [docs](index.md) » plugins.finalcutpro.export.batch.manager.panel
---

CommandPost Batch Export Panel.

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
	<li><a href="#DEFAULT_PRIORITY">DEFAULT_PRIORITY</a></li>
	<li><a href="#HANDLER_PRIORITY">HANDLER_PRIORITY</a></li>
  </ul>
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
	<li><a href="#addStatus">addStatus</a></li>
	<li><a href="#addTextbox">addTextbox</a></li>
	<li><a href="#getToolbarItem">getToolbarItem</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Constants</h4>
  <section id="DEFAULT_PRIORITY">
	<h5><a href="#DEFAULT_PRIORITY">DEFAULT_PRIORITY</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.export.batch.manager.panel.DEFAULT_PRIORITY -&gt; number</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The default priority for panels.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="HANDLER_PRIORITY">
	<h5><a href="#HANDLER_PRIORITY">HANDLER_PRIORITY</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.export.batch.manager.panel.HANDLER_PRIORITY -&gt; number</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The default priority for handler scripts.</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Constructors</h4>
  <section id="new">
	<h5><a href="#new">new</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.export.batch.manager.panel.new(priority, id) -&gt; cp.core.preferences.manager.panel</code></td>
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
<li>priority  - Defines the order in which the panel appears.</li>
<li>id        - The unique ID for the panel.</li>
<li>webview   - The webview the panel is attached to.</li>
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
		<td><code>plugins.finalcutpro.export.batch.manager.panel:addButton(params) -&gt; panel</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Adds a button to the panel.</p>
<p>Parameters:</p>
<ul>
<li>params - The list of parameters.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The same panel.</li>
</ul>
<p>Notes:</p>
<ul>
<li>The <code>params</code> table may contain:
<strong> <code>id</code>        - (optional) the unique ID for the button. If none is provided, one is generated.</strong> <code>value</code>     - The value of the button. This is sent to the <code>onclick</code> function.
<strong> <code>label</code>     - The text label for the button. Defaults to the <code>value</code> if not provided.</strong> <code>width</code>     - The width of the button in pixels.
** <code>onclick</code>   - the function to execute when the button is clicked. The function should have the signature of <code>function(id, value)</code>, where <code>id</code> is the id of the button that was clicked, and <code>value</code> is the value of the button.</li>
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
		<td><code>plugins.finalcutpro.export.batch.manager.panel:addCheckbox(priority, params) -&gt; panel</code></td>
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
<li>The panel.
Notes:</li>
<li>The <code>params</code> can contain the following fields:
<strong> <code>id</code>         - (optional) The unique ID. If none is provided, one will be generated.</strong> <code>name</code>       - (optional) The name of the checkbox field.
<strong> <code>label</code>      - (optional) The text label to display after the checkbox.</strong> <code>onchange</code>   - (optional) a function that will get called when the checkbox value changes. It will be passed two parameters, <code>id</code> and <code>params</code>, the latter of which is a table containing the <code>value</code> and <code>checked</code> values of the checkbox.
** <code>class</code>      - (optional) the CSS class list to apply to the checkbox.</li>
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
		<td><code>plugins.finalcutpro.export.batch.manager.panel:addContent(priority, content[, escaped]) -&gt; panel</code></td>
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
<li><code>priority</code>        - the priority order of the content.</li>
<li><code>content</code>         - a value that can be converted to a string.</li>
<li><code>escaped</code>         - if <code>true</code>, the content will be escaped.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The panel.</li>
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
		<td><code>plugins.finalcutpro.export.batch.manager.panel:addHandler(event, id, handlerFn, keys) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets a handler from an Handler ID</p>
<p>Parameters:</p>
<ul>
<li>event - The event</li>
<li>id - the Handler ID</li>
<li>handlerFn - The Handler function</li>
<li>keys - Keys</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
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
		<td><code>plugins.finalcutpro.export.batch.manager.panel:addHeading(text) -&gt; panel</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Adds a heading to the panel</p>
<p>Parameters:</p>
<ul>
<li>text - The text of the heading as a string</li>
</ul>
<p>Returns:</p>
<ul>
<li>The panel object.</li>
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
		<td><code>plugins.finalcutpro.export.batch.manager.panel:addParagraph(content[, escaped[, class]]) -&gt; panel</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Adds a Paragraph to the panel</p>
<p>Parameters:</p>
<ul>
<li>content - The content as a string</li>
<li>escaped - Whether or not the HTML should be escaped as a boolean. Defaults to <code>true</code> for simple text.</li>
<li>class - The class as a string</li>
</ul>
<p>Returns:</p>
<ul>
<li>The panel object.</li>
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
		<td><code>plugins.finalcutpro.export.batch.manager.panel:addPassword(params) -&gt; panel</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Adds a password text-box to the panel.</p>
<p>Parameters:</p>
<ul>
<li>params - A table of parameters</li>
</ul>
<p>Returns:</p>
<ul>
<li>The panel object.</li>
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
		<td><code>plugins.finalcutpro.export.batch.manager.panel:addSelect(params) -&gt; panel</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Adds a select to the panel.</p>
<p>Parameters:</p>
<ul>
<li>priority - Priority of the item as number.</li>
<li>params - A table of parameters</li>
</ul>
<p>Returns:</p>
<ul>
<li>The panel object.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="addStatus">
	<h5><a href="#addStatus">addStatus</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.export.batch.manager.panel:addStatus(priority, content, default) -&gt; panel</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Adds a Paragraph to the panel</p>
<p>Parameters:</p>
<ul>
<li>content - The content value</li>
<li>default - The default value to display if the <code>content</code> is <code>nil</code>. It will be displayed with a different style.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The panel object.</li>
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
		<td><code>plugins.finalcutpro.export.batch.manager.panel:addTextbox(params) -&gt; panel</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Adds a text-box to the panel</p>
<p>Parameters:</p>
<ul>
<li>params - A table of parameters</li>
</ul>
<p>Returns:</p>
<ul>
<li>The panel object.</li>
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
		<td><code>plugins.finalcutpro.export.batch.manager.panel:getToolbarItem() -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets the Tool Bar as a table</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The toolbar item as a table.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
