# [docs](index.md) » cp.apple.finalcutpro.inspector.color.ColorInspector
---

Color Inspector Module.

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
	<li><a href="#CORRECTION_TYPES">CORRECTION_TYPES</a></li>
  </ul>
<li>Functions - API calls offered directly by the extension</li>
  <ul>
	<li><a href="#matches">matches</a></li>
  </ul>
<li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
  <ul>
	<li><a href="#correctorUI">correctorUI</a></li>
	<li><a href="#isAdvanced">isAdvanced</a></li>
	<li><a href="#isShowing">isShowing</a></li>
	<li><a href="#topBarUI">topBarUI</a></li>
	<li><a href="#UI">UI</a></li>
  </ul>
<li>Methods - API calls which can only be made on an object returned by a constructor</li>
  <ul>
	<li><a href="#activateCorrection">activateCorrection</a></li>
	<li><a href="#addCorrection">addCorrection</a></li>
	<li><a href="#app">app</a></li>
	<li><a href="#colorBoard">colorBoard</a></li>
	<li><a href="#colorCurves">colorCurves</a></li>
	<li><a href="#colorWheels">colorWheels</a></li>
	<li><a href="#corrections">corrections</a></li>
	<li><a href="#hide">hide</a></li>
	<li><a href="#hueSaturationCurves">hueSaturationCurves</a></li>
	<li><a href="#new">new</a></li>
	<li><a href="#parent">parent</a></li>
	<li><a href="#show">show</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Constants</h4>
  <section id="CORRECTION_TYPES">
	<h5><a href="#CORRECTION_TYPES">CORRECTION_TYPES</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorInspector.CORRECTION_TYPES</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Table of Correction Types:</p>
<ul>
<li>"Color Board"</li>
<li>"Color Wheels"</li>
<li>"Color Curves"</li>
<li>"Hue/Saturation Curves"</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Functions</h4>
  <section id="matches">
	<h5><a href="#matches">matches</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorInspector.matches(element)</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Checks if the specified element is the Color Inspector element.</p>
<p>Parameters:</p>
<ul>
<li>element   - The element to check</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the element is the Color Inspector.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Fields</h4>
  <section id="correctorUI">
	<h5><a href="#correctorUI">correctorUI</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorInspector.correctorUI &lt;cp.prop: hs._asm.axuielement; read-only&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the <code>hs._asm.axuielement</code> object representing the currently-selected corrector panel.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="isAdvanced">
	<h5><a href="#isAdvanced">isAdvanced</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorInspector.isAdvanced &lt;cp.prop: boolean; read-only&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Is the Color Inspector the advanced version that was added in 10.4?</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="isShowing">
	<h5><a href="#isShowing">isShowing</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorInspector.isShowing &lt;cp.prop: boolean; read-only; live&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Checks if the Color Inspector is visible.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="topBarUI">
	<h5><a href="#topBarUI">topBarUI</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorInspector.topBarUI &lt;cp.prop: hs._asm.axuielement; read-only&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the <code>hs._asm.axuielement</code> object representing the top bar.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="UI">
	<h5><a href="#UI">UI</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorInspector.UI &lt;cp.prop: hs._asm.axuielement; read-only&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the <code>hs._asm.axuielement</code> object for the Color Inspector. Prior to FCPX 10.4 this will be the Color Board.</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Methods</h4>
  <section id="activateCorrection">
	<h5><a href="#activateCorrection">activateCorrection</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorInspector:activateCorrection(correctionType[, number]) -&gt; self</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Activates the named correction type and number, if present. If no corrector with the type/number combination exists, a new one is added.</p>
<p>Parameters:</p>
<ul>
<li>correctionType   - The string for the type of correction (in English). E.g. "Color Wheels", "Color Board", etc.</li>
<li>number           - The correction number for that type. Defaults to <code>1</code>.</li>
</ul>
<p>Returns:</p>
<ul>
<li>ColorInspector object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="addCorrection">
	<h5><a href="#addCorrection">addCorrection</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorInspector:addCorrection(correctionType) -&gt; self</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Adds the named correction type.</p>
<p>Parameters:</p>
<ul>
<li>correctionType   - The string for the type of correction (in English). E.g. "Color Wheels", "Color Board", etc.</li>
</ul>
<p>Returns:</p>
<ul>
<li>ColorInspector object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="app">
	<h5><a href="#app">app</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorInspector:app() -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the <code>cp.apple.finalcutpro</code> app table</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The application object as a table</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="colorBoard">
	<h5><a href="#colorBoard">colorBoard</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorInspector:colorBoard() -&gt; ColorBoard</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets the ColorBoard object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A new ColorBoard object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="colorCurves">
	<h5><a href="#colorCurves">colorCurves</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorInspector:colorCurves() -&gt; ColorCurves</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets the ColorCurves object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A new ColorCurves object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="colorWheels">
	<h5><a href="#colorWheels">colorWheels</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorInspector:colorWheels() -&gt; ColorWheels</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets the ColorWheels object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A new ColorWheels object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="corrections">
	<h5><a href="#corrections">corrections</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorInspector:corrections() -&gt; CorrectionsBar</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the <code>CorrectionsBar</code> instance representing the available corrections,
and currently selected correction type.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>CorrectionsBar</code> instance.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="hide">
	<h5><a href="#hide">hide</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorInspector:hide() -&gt; ColorInspector</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Hides the Color Inspector</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>ColorInspector object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="hueSaturationCurves">
	<h5><a href="#hueSaturationCurves">hueSaturationCurves</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorInspector:hueSaturationCurves() -&gt; HueSaturationCurves</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets the HueSaturationCurves object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A new HueSaturationCurves object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="new">
	<h5><a href="#new">new</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorInspector.new(parent) -&gt; ColorInspector object</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new ColorInspector object</p>
<p>Parameters:</p>
<ul>
<li><code>parent</code>     - The parent</li>
</ul>
<p>Returns:</p>
<ul>
<li>A ColorInspector object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="parent">
	<h5><a href="#parent">parent</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorInspector:parent() -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the ColorInspector's parent table.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The parent object as a table</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="show">
	<h5><a href="#show">show</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorInspector:show() -&gt; self</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Shows the Color Inspector.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>ColorInspector object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
