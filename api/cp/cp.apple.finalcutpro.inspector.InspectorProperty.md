# [docs](index.md) » cp.apple.finalcutpro.inspector.InspectorProperty
---

`InspectorProperty` contains helper functions for handling common property
types that occur in various `Inspectors` in FCP.

In addition to specific property row types like `textField`, `slider`, etc.,
there is also a `section`, which is for rows which expand/collapse to reveal
other properties.

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
	<li><a href="#checkBox">checkBox</a></li>
	<li><a href="#hasProperties">hasProperties</a></li>
	<li><a href="#menuButton">menuButton</a></li>
	<li><a href="#numberField">numberField</a></li>
	<li><a href="#popUpButton">popUpButton</a></li>
	<li><a href="#section">section</a></li>
	<li><a href="#simple">simple</a></li>
	<li><a href="#slider">slider</a></li>
	<li><a href="#staticText">staticText</a></li>
	<li><a href="#textField">textField</a></li>
	<li><a href="#xy">xy</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="checkBox">
	<h5><a href="#checkBox">checkBox</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.InspectorProperty.checkBox(labelKey[, index]) -&gt; cp.prop &lt;cp.ui.PropertyRow; read-only&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new <code>cp.prop</code> that contains a <code>PropertyRow</code>  matching the <code>labelKey</code>.</p>
<p>It has one additional property:</p>
<ul>
<li><code>value</code>   - A <code>cp.ui.CheckBox</code> which contains the boolean value for the row.</li>
</ul>
<p>Parameters:</p>
<ul>
<li>labelKey      - The I18N key that the row lable matches.</li>
<li>index         - The instance number of that label (defaults to <code>1</code>).</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.prop</code> that returns the <code>PropertyRow</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="hasProperties">
	<h5><a href="#hasProperties">hasProperties</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.InspectorProperty.hasProperties(parent, uiFinder) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>This will prepare the <code>parent</code> to handle containing <code>PropertyRow</code> children, and returns
a function which can pass in a table of properties to bind to the parent.</p>
<p>E.g.:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">o</span> <span class="o">=</span> <span class="p">{</span>
    <span class="n">propertiesUI</span> <span class="o">=</span> <span class="p">...,</span>
<span class="p">}</span>
<span class="n">InspectorProperty</span><span class="p">.</span><span class="n">hasProperties</span><span class="p">(</span><span class="n">o</span><span class="p">,</span> <span class="n">o</span><span class="p">.</span><span class="n">propertiesUI</span><span class="p">)</span> <span class="p">{</span>
    <span class="n">propOne</span>     <span class="o">=</span> <span class="n">InspectorProperty</span><span class="p">.</span><span class="n">textField</span> <span class="s2">&quot;FFPropOne&quot;</span><span class="p">,</span>
    <span class="n">sectionOne</span>  <span class="o">=</span> <span class="n">InspectorProperty</span><span class="p">.</span><span class="n">section</span> <span class="s2">&quot;FFSectionOne&quot;</span> <span class="p">{</span>
        <span class="n">sliderOne</span>   <span class="o">=</span> <span class="n">InspectorProperty</span><span class="p">.</span><span class="n">slider</span> <span class="s2">&quot;FFSliderOne&quot;</span><span class="p">,</span>
    <span class="p">},</span>
<span class="p">}</span>
</pre></div>
<p>Parameters:</p>
<ul>
<li>parent    - The parent table.</li>
<li>uiFinder  - The function or cp.prop which will be called to find the parent UI element. Functions will be passed the <code>parent</code> when being executed.</li>
</ul>
<p>Returns:</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="menuButton">
	<h5><a href="#menuButton">menuButton</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.InspectorProperty.menuButton(labelKey[, index]) -&gt; cp.prop &lt;cp.ui.PropertyRow; read-only&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new <code>cp.prop</code> that contains a <code>PropertyRow</code>  matching the <code>labelKey</code>.</p>
<p>It has one additional property:</p>
<ul>
<li><code>value</code>   - A <code>cp.ui.MenuButton</code> which contains the text value.</li>
</ul>
<p>Parameters:</p>
<ul>
<li>labelKey      - The I18N key that the row lable matches.</li>
<li>index         - The instance number of that label (defaults to <code>1</code>).</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.prop</code> that returns the <code>PropertyRow</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="numberField">
	<h5><a href="#numberField">numberField</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.InspectorProperty.numberField(labelKey[, index]) -&gt; cp.prop &lt;cp.ui.PropertyRow; read-only&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new <code>cp.prop</code> that contains a <code>PropertyRow</code>  matching the <code>labelKey</code>.</p>
<p>It has one additional property:</p>
<ul>
<li><code>value</code>   - A <code>cp.ui.TextField</code> which contains the number value.</li>
</ul>
<p>Parameters:</p>
<ul>
<li>labelKey      - The I18N key that the row lable matches.</li>
<li>index         - The instance number of that label (defaults to <code>1</code>).</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.prop</code> that returns the <code>PropertyRow</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="popUpButton">
	<h5><a href="#popUpButton">popUpButton</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.InspectorProperty.popUpButton(labelKey[, index]) -&gt; cp.prop &lt;cp.ui.PropertyRow; read-only&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new <code>cp.prop</code> that contains a <code>PropertyRow</code>  matching the <code>labelKey</code>.</p>
<p>It has one additional property:</p>
<ul>
<li><code>value</code>   - A <code>cp.ui.PopUpButton</code> which contains the text value.</li>
</ul>
<p>Parameters:</p>
<ul>
<li>labelKey      - The I18N key that the row lable matches.</li>
<li>index         - The instance number of that label (defaults to <code>1</code>).</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.prop</code> that returns the <code>PropertyRow</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="section">
	<h5><a href="#section">section</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.InspectorProperty.section(labelKey[, index]) -&gt; function</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a 'section row' factory function that can be called to create a section row that contains other <code>PropertyRow'</code>cp.prop`s.</p>
<p>This does <em>not</em> return an actual <code>cp.prop</code>. Rather, it returns a 'factory' function that will help configure the sub-properties of
of the section. This can be used as follows:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">o</span> <span class="o">=</span> <span class="p">{}</span>
<span class="n">prop</span><span class="p">.</span><span class="n">bind</span><span class="p">(</span><span class="n">o</span><span class="p">)</span> <span class="p">{</span>
  <span class="n">sectionOne</span>         <span class="o">=</span> <span class="n">InspectorProperty</span><span class="p">.</span><span class="n">section</span> <span class="s2">&quot;FFHeaderOneKey&quot;</span> <span class="p">{</span>     <span class="c1">-- has sub-properties inside the `{}`</span>
    <span class="n">subRowOne</span>       <span class="o">=</span> <span class="n">InspectorProperty</span><span class="p">.</span><span class="n">textField</span> <span class="s2">&quot;FFSubRowOneKey&quot;</span><span class="p">,</span>
    <span class="n">subRowTwo</span>       <span class="o">=</span> <span class="n">InspectorProperty</span><span class="p">.</span><span class="n">slider</span> <span class="s2">&quot;FFSubRowTwoKey&quot;</span><span class="p">,</span>
  <span class="p">},</span>
  <span class="n">sectionTwo</span>         <span class="o">=</span> <span class="n">InspectorProperty</span><span class="p">.</span><span class="n">section</span> <span class="s2">&quot;FFHeaderTwoKey&quot;</span> <span class="p">{}</span>    <span class="c1">-- no sub-properties, still needs `{}`</span>
<span class="p">}</span>

<span class="c1">-- access subRowOne</span>
<span class="kd">local</span> <span class="n">value</span> <span class="o">=</span> <span class="n">o</span><span class="p">:</span><span class="n">sectionOne</span><span class="p">():</span><span class="n">subRowOne</span><span class="p">()</span>
</pre></div>
<p>The <code>o.sectionOne</code> property will be a <code>cp.prop</code> with the following built-in additional properties:</p>
<ul>
<li><code>enabled</code>     - a <code>cp.ui.CheckBox</code> which reports if the section row is enabled.</li>
<li><code>toggle</code>      - a <code>cp.ui.Button</code> which will toggle the show/hide button (if present)</li>
<li><code>reset</code>       - a <code>cp.ui.Button</code> which will reset the sub-property values, if present in the UI.</li>
<li><code>expanded</code>    - a <code>cp.prop</code> which reports if the section is currently expanded.</li>
</ul>
<p>Parameters:</p>
<ul>
<li>labelKey      - The I18N lookup key to find the row with.</li>
<li>index         - (optional) The occurrence of the key value in the parent. Sometimes multiple rows have the same title. Defaults to <code>1</code>.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A function which will create the section row when called.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="simple">
	<h5><a href="#simple">simple</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.InspectorProperty.simple(labelKey[, prepareFn][, index]]) -&gt; cp.prop &lt;cp.ui.PropertyRow; read-only&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new <code>cp.prop</code> that contains a <code>PropertyRow</code>  matching the <code>labelKey</code>.</p>
<p>It has no additional properties, but it does allow a <code>prepareFn</code> to be provided, which will be
called after the <code>PropertyRow</code> is created, and passed the new <code>PropertyRow</code> as the first argument.</p>
<p>Parameters:</p>
<ul>
<li>labelKey      - The I18N key that the row lable matches.</li>
<li>prepareFn     - The function to call to perform additional preparations on the row.</li>
<li>index         - The instance number of that label (defaults to <code>1</code>).</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.prop</code> that returns the <code>PropertyRow</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="slider">
	<h5><a href="#slider">slider</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.InspectorProperty.slider(labelKey[, index]) -&gt; cp.prop &lt;cp.ui.PropertyRow; read-only&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new <code>cp.prop</code> that contains a <code>PropertyRow</code>  matching the <code>labelKey</code>.</p>
<p>It has one additional property:</p>
<ul>
<li><code>value</code>   - A <code>cp.ui.TextField</code> which contains the value of the slider.</li>
</ul>
<p>Parameters:</p>
<ul>
<li>labelKey      - The I18N key that the row lable matches.</li>
<li>index         - The instance number of that label (defaults to <code>1</code>).</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.prop</code> that returns the <code>PropertyRow</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="staticText">
	<h5><a href="#staticText">staticText</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.InspectorProperty.staticText(labelKey[, index]) -&gt; cp.prop &lt;cp.ui.PropertyRow; read-only&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new <code>cp.prop</code> that contains a <code>PropertyRow</code>  matching the <code>labelKey</code>.</p>
<p>It has one additional property:</p>
<ul>
<li><code>value</code>   - A <code>cp.ui.StaticText</code> which contains the text value.</li>
</ul>
<p>Parameters:</p>
<ul>
<li>labelKey      - The I18N key that the row lable matches.</li>
<li>index         - The instance number of that label (defaults to <code>1</code>).</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.prop</code> that returns the <code>PropertyRow</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="textField">
	<h5><a href="#textField">textField</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.InspectorProperty.textField(labelKey[, index]) -&gt; cp.prop &lt;cp.ui.PropertyRow; read-only&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new <code>cp.prop</code> that contains a <code>PropertyRow</code>  matching the <code>labelKey</code>.</p>
<p>It has one additional property:</p>
<ul>
<li><code>value</code>   - A <code>cp.ui.TextField</code> which contains the text value.</li>
</ul>
<p>Parameters:</p>
<ul>
<li>labelKey      - The I18N key that the row lable matches.</li>
<li>index         - The instance number of that label (defaults to <code>1</code>).</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.prop</code> that returns the <code>PropertyRow</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="xy">
	<h5><a href="#xy">xy</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.InspectorProperty.xy(labelKey[, index]) -&gt; cp.prop &lt;cp.ui.PropertyRow; read-only&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new <code>cp.prop</code> that contains a <code>PropertyRow</code>  matching the <code>labelKey</code>.</p>
<p>It has two additional properties:</p>
<ul>
<li><code>x</code>   - A <code>cp.ui.TextField</code> containing the 'X' value.</li>
<li><code>y</code>   - A <code>cp.ui.TextField</code> containing the <code>Y</code> value.</li>
</ul>
<p>Parameters:</p>
<ul>
<li>labelKey      - The I18N key that the row lable matches.</li>
<li>index         - The instance number of that label (defaults to <code>1</code>).</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.prop</code> that returns the <code>PropertyRow</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
