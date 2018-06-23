# [docs](index.md) » cp.apple.finalcutpro.inspector.color.ColorWheels
---

Color Wheels Module.

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
	<li><a href="#matches">matches</a></li>
  </ul>
<li>Constructors - API calls which return an object, typically one that offers API methods</li>
  <ul>
	<li><a href="#new">new</a></li>
  </ul>
<li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
  <ul>
	<li><a href="#contentUI">contentUI</a></li>
	<li><a href="#hue">hue</a></li>
	<li><a href="#isShowing">isShowing</a></li>
	<li><a href="#maxValue">maxValue</a></li>
	<li><a href="#minValue">minValue</a></li>
	<li><a href="#mix">mix</a></li>
	<li><a href="#temperature">temperature</a></li>
	<li><a href="#tint">tint</a></li>
	<li><a href="#UI">UI</a></li>
	<li><a href="#value">value</a></li>
	<li><a href="#viewingAllWheels">viewingAllWheels</a></li>
  </ul>
<li>Methods - API calls which can only be made on an object returned by a constructor</li>
  <ul>
	<li><a href="#app">app</a></li>
	<li><a href="#highlights">highlights</a></li>
	<li><a href="#hueRow">hueRow</a></li>
	<li><a href="#hueTextField">hueTextField</a></li>
	<li><a href="#master">master</a></li>
	<li><a href="#midtones">midtones</a></li>
	<li><a href="#mixRow">mixRow</a></li>
	<li><a href="#mixSlider">mixSlider</a></li>
	<li><a href="#parent">parent</a></li>
	<li><a href="#shadows">shadows</a></li>
	<li><a href="#show">show</a></li>
	<li><a href="#temperatureRow">temperatureRow</a></li>
	<li><a href="#temperatureSlider">temperatureSlider</a></li>
	<li><a href="#tintRow">tintRow</a></li>
	<li><a href="#tintSlider">tintSlider</a></li>
	<li><a href="#viewMode">viewMode</a></li>
	<li><a href="#wheelType">wheelType</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="matches">
	<h5><a href="#matches">matches</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWheels.matches(element)</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Checks if the specified element is the Color Wheels element.</p>
<p>Parameters:</p>
<ul>
<li>element   - The element to check</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the element is the Color Wheels.</li>
</ul>
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
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWheels.new(parent) -&gt; ColorInspector</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constructor</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new ColorWheels object</p>
<p>Parameters:</p>
<ul>
<li><code>parent</code>     - The parent</li>
</ul>
<p>Returns:</p>
<ul>
<li>A new <code>ColorInspector</code> object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Fields</h4>
  <section id="contentUI">
	<h5><a href="#contentUI">contentUI</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWheels.contentUI &lt;cp.prop: hs._asm.axuielement; read-only&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The <code>axuielement</code> representing the content element of the ColorWheels corrector.
This contains all the individual UI elements of the corrector, and is typically an <code>AXScrollArea</code>.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="hue">
	<h5><a href="#hue">hue</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWheels.hue &lt;cp.prop: number&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The hue for the corrector. A number from <code>0</code> to <code>360</code>.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="isShowing">
	<h5><a href="#isShowing">isShowing</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWheels.isShowing &lt;cp.prop: boolean; read-only&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Is the Color Wheels Corrector currently showing?</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="maxValue">
	<h5><a href="#maxValue">maxValue</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWheels.maxValue &lt;cp.prop: number&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The maximum value of the indicator as a number.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="minValue">
	<h5><a href="#minValue">minValue</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWheels.minValue &lt;cp.prop: number&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The minimum value of the indicator as a number.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="mix">
	<h5><a href="#mix">mix</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWheels.mix &lt;cp.prop: number&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The mix amount for this corrector. A number ranging from <code>0</code> to <code>1</code>.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="temperature">
	<h5><a href="#temperature">temperature</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWheels.temperature &lt;cp.prop: number&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The color temperature for this corrector. A number from 2500 to 10000.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="tint">
	<h5><a href="#tint">tint</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWheels.tint &lt;cp.prop: number&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The tint for the corrector. A number from <code>-50</code> to <code>50</code>.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="UI">
	<h5><a href="#UI">UI</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWheels.UI &lt;cp.prop: hs._asm.axuielement; read-only&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The <code>axuielement</code> representing the ColorWheels corrector.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="value">
	<h5><a href="#value">value</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWheels.value &lt;cp.prop: number&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The value of the value indicator as a number.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="viewingAllWheels">
	<h5><a href="#viewingAllWheels">viewingAllWheels</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWheels.viewingAllWheels &lt;cp.prop: boolean&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Reports and modifies whether the ColorWheels corrector is showing "All Wheels" (<code>true</code>) or "Single Wheels" (<code>false</code>).</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Methods</h4>
  <section id="app">
	<h5><a href="#app">app</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWheels:app() -&gt; table</code></td>
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
  <section id="highlights">
	<h5><a href="#highlights">highlights</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWheels:highlights() -&gt; ColorWheel</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a <code>ColorWheel</code> that allows control of the 'highlights' color settings.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>ColorWheel</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="hueRow">
	<h5><a href="#hueRow">hueRow</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWheels:hueRow() -&gt; cp.ui.PropertyRow</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a <code>PropertyRow</code> that provides access to the 'Hue' parameter, and <code>axuielement</code>
values for that row.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>PropertyRow</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="hueTextField">
	<h5><a href="#hueTextField">hueTextField</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWheels:hueTextField() -&gt; cp.ui.TextField</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a <code>TextField</code> that provides access to the 'Hue' slider.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The Hue <code>Slider</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="master">
	<h5><a href="#master">master</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWheels:master() -&gt; ColorWheel</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a <code>ColorWheel</code> that allows control of the 'master' color settings.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>ColorWheel</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="midtones">
	<h5><a href="#midtones">midtones</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWheels:midtones() -&gt; ColorWheel</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a <code>ColorWheel</code> that allows control of the 'midtones' color settings.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>ColorWheel</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="mixRow">
	<h5><a href="#mixRow">mixRow</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWheels:mixRow() -&gt; cp.ui.PropertyRow</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a <code>PropertyRow</code> that provides access to the 'Mix' parameter, and <code>axuielement</code>
values for that row.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>PropertyRow</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="mixSlider">
	<h5><a href="#mixSlider">mixSlider</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWheels:mixSlider() -&gt; cp.ui.Slider</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a <code>Slider</code> that provides access to the 'Mix' slider.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The Mix <code>Slider</code>.</li>
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
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWheels:parent() -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the ColorWheels's parent table</p>
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
  <section id="shadows">
	<h5><a href="#shadows">shadows</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWheels:shadows() -&gt; ColorWheel</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a <code>ColorWheel</code> that allows control of the 'shadows' color settings.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>ColorWheel</code>.</li>
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
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWheels:show() -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Show's the Color Board within the Color Inspector.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>ColorWheels object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="temperatureRow">
	<h5><a href="#temperatureRow">temperatureRow</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWheels:temperatureRow() -&gt; cp.ui.PropertyRow</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a <code>PropertyRow</code> that provides access to the 'Temperatures' parameter, and <code>axuielement</code>
values for that row.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>PropertyRow</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="temperatureSlider">
	<h5><a href="#temperatureSlider">temperatureSlider</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWheels:temperatureSlider() -&gt; cp.ui.Slider</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a <code>Slider</code> that provides access to the 'Temperatures' slider.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The Temperatures <code>Slider</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="tintRow">
	<h5><a href="#tintRow">tintRow</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWheels:tintRow() -&gt; cp.ui.PropertyRow</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a <code>PropertyRow</code> that provides access to the 'Tint' parameter, and <code>axuielement</code>
values for that row.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>PropertyRow</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="tintSlider">
	<h5><a href="#tintSlider">tintSlider</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWheels:tintSlider() -&gt; cp.ui.Slider</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a <code>Slider</code> that provides access to the 'Tint' slider.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The Tint <code>Slider</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="viewMode">
	<h5><a href="#viewMode">viewMode</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWheels:viewMode() -&gt; MenuButton</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the <code>MenuButton</code> for the View menu button.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>MenuButton</code> for the View mode.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="wheelType">
	<h5><a href="#wheelType">wheelType</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWheels:wheelType() -&gt; RadioGroup</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the <code>RadioGroup</code> that allows selection of the wheel type. Only available when
<code>viewingAllWheels</code> is <code>true</code>.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>RadioGroup</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
