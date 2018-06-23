# [docs](index.md) » plugins.finalcutpro.browser.keywords
---

Browser Keywords Presets.

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
	<li><a href="#NUMBER_OF_PRESETS">NUMBER_OF_PRESETS</a></li>
	<li><a href="#NUMBER_OF_SHORTCUTS">NUMBER_OF_SHORTCUTS</a></li>
  </ul>
<li>Functions - API calls offered directly by the extension</li>
  <ul>
	<li><a href="#restore">restore</a></li>
	<li><a href="#save">save</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Constants</h4>
  <section id="NUMBER_OF_PRESETS">
	<h5><a href="#NUMBER_OF_PRESETS">NUMBER_OF_PRESETS</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.browser.keywords.NUMBER_OF_PRESETS -&gt; number</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The number of presets available.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="NUMBER_OF_SHORTCUTS">
	<h5><a href="#NUMBER_OF_SHORTCUTS">NUMBER_OF_SHORTCUTS</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.browser.keywords.NUMBER_OF_SHORTCUTS -&gt; number</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The number of Keyword Keyboard shortcuts available.</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Functions</h4>
  <section id="restore">
	<h5><a href="#restore">restore</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.browser.keywords.restore(preset) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Restores a Keyword preset.</p>
<p>Parameters:</p>
<ul>
<li>preset - A preset number between 1 and the value of <code>plugins.finalcutpro.browser.keywords.NUMBER_OF_PRESETS</code>.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="save">
	<h5><a href="#save">save</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.browser.keywords.save(preset) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Saves a Keyword preset.</p>
<p>Parameters:</p>
<ul>
<li>preset - A preset number between 1 and the value of <code>plugins.finalcutpro.browser.keywords.NUMBER_OF_PRESETS</code>.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
