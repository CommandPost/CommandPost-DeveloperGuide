# [docs](index.md) » cp.apple.finalcutpro.inspector.color.ColorPuck
---

Color Puck Module.

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
	<li><a href="#DEFAULT_ANGLES">DEFAULT_ANGLES</a></li>
	<li><a href="#ELASTICITY">ELASTICITY</a></li>
	<li><a href="#NATURAL_LENGTH">NATURAL_LENGTH</a></li>
	<li><a href="#RANGE">RANGE</a></li>
  </ul>
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
	<li><a href="#skimming">skimming</a></li>
  </ul>
<li>Methods - API calls which can only be made on an object returned by a constructor</li>
  <ul>
	<li><a href="#accumulate">accumulate</a></li>
	<li><a href="#app">app</a></li>
	<li><a href="#cleanup">cleanup</a></li>
	<li><a href="#colorMarker">colorMarker</a></li>
	<li><a href="#contentUI">contentUI</a></li>
	<li><a href="#drawMarker">drawMarker</a></li>
	<li><a href="#getArc">getArc</a></li>
	<li><a href="#getBrightness">getBrightness</a></li>
	<li><a href="#hasAngle">hasAngle</a></li>
	<li><a href="#index">index</a></li>
	<li><a href="#isShowing">isShowing</a></li>
	<li><a href="#loop">loop</a></li>
	<li><a href="#parent">parent</a></li>
	<li><a href="#reset">reset</a></li>
	<li><a href="#select">select</a></li>
	<li><a href="#shiftAngle">shiftAngle</a></li>
	<li><a href="#shiftPercent">shiftPercent</a></li>
	<li><a href="#show">show</a></li>
	<li><a href="#start">start</a></li>
	<li><a href="#stop">stop</a></li>
	<li><a href="#UI">UI</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Constants</h4>
  <section id="DEFAULT_ANGLES">
	<h5><a href="#DEFAULT_ANGLES">DEFAULT_ANGLES</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorPuck.DEFAULT_ANGLES -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The table of default angles for the various pucks (1-4).</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="ELASTICITY">
	<h5><a href="#ELASTICITY">ELASTICITY</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorPuck.ELASTICITY -&gt; number</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Elasticity as number.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="NATURAL_LENGTH">
	<h5><a href="#NATURAL_LENGTH">NATURAL_LENGTH</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorPuck.NATURAL_LENGTH -&gt; number</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Natural Length as number.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="RANGE">
	<h5><a href="#RANGE">RANGE</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorPuck.RANGE -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Table of puck ranges.</p>
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
		<td><code>cp.apple.finalcutpro.inspector.color.ColorPuck.matches(element) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Checks to see if an element matches what we think it should be.</p>
<p>Parameters:</p>
<ul>
<li>element - An <code>axuielementObject</code> to check.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if matches otherwise <code>false</code></li>
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
		<td><code>cp.apple.finalcutpro.inspector.color.ColorPuck.new(parent, puckNumber, labelKeys, hasAngle) -&gt; ColorPuck</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constructor</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new <code>ColorPuck</code> object</p>
<p>Parameters:</p>
<ul>
<li><code>parent</code>     - The parent</li>
<li><code>puckNumber</code> - The puck number</li>
<li><code>labelKeys</code>  - Label Keys</li>
<li><code>hasAngle</code>   - If <code>true</code>, the puck has an <code>angle</code> parameter.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A ColorInspector object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Fields</h4>
  <section id="skimming">
	<h5><a href="#skimming">skimming</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorPuck.skimming &lt;cp.prop: boolean&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The Skimming Preferences value.</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Methods</h4>
  <section id="accumulate">
	<h5><a href="#accumulate">accumulate</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorPuck:accumulate() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Accumulate's the Shift Values.</p>
<p>Parameters:</p>
<ul>
<li><code>xShift</code> - <code>x</code> value as number</li>
<li><code>yShift</code> - <code>y</code> value as number</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>x</code> - Accumulated <code>x</code> value as number</li>
<li><code>y</code> - Accumulated <code>y</code> value as number</li>
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
		<td><code>cp.apple.finalcutpro.inspector.color.ColorPuck:app() -&gt; App</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the App instance representing Final Cut Pro.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>App</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="cleanup">
	<h5><a href="#cleanup">cleanup</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorPuck:cleanup() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Cleans up the Color Puck drawings.</p>
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
  <section id="colorMarker">
	<h5><a href="#colorMarker">colorMarker</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorPuck:colorMarker(pct, angle) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Draws a Color Marker.</p>
<p>Parameters:</p>
<ul>
<li>pct - Percentage</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="contentUI">
	<h5><a href="#contentUI">contentUI</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorPuck:contentUI() -&gt; axuielementObject</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the Content Accessibility Object</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>An <code>axuielementObject</code> or <code>nil</code></li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="drawMarker">
	<h5><a href="#drawMarker">drawMarker</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorPuck:drawMarker() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Draws a marker.</p>
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
  <section id="getArc">
	<h5><a href="#getArc">getArc</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorPuck:getArc() -&gt; number</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets the arc value.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The arc value as number.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getBrightness">
	<h5><a href="#getBrightness">getBrightness</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorPuck:getBrightness() -&gt; number</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets the brightness value.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The brightness value as number.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="hasAngle">
	<h5><a href="#hasAngle">hasAngle</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorPuck:hasAngle() -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Indicates if the puck has an <code>angle</code> parameter. The <code>angle</code> <code>cp.prop</code> will always
exist regardless, but if this is <code>false</code>, it will never return a result.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the puck has an <code>angle</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="index">
	<h5><a href="#index">index</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorPuck:index() -&gt; number</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the puck number (1 through 4).</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The puck number.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="isShowing">
	<h5><a href="#isShowing">isShowing</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorPuck:isShowing() -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets whether or not the Color Puck is showing.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if showing or <code>false</code> if not.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="loop">
	<h5><a href="#loop">loop</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorPuck:loop() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Loops the Color Puck function.</p>
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
  <section id="parent">
	<h5><a href="#parent">parent</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorPuck:parent() -&gt; object</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the Parent object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The parent object.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="reset">
	<h5><a href="#reset">reset</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorPuck:reset() -&gt; cp.apple.finalcutpro.inspector.color.ColorPuck</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Resets the puck to its default settings.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>ColorPuck</code> instance.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="select">
	<h5><a href="#select">select</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorPuck:select() -&gt; cp.apple.finalcutpro.inspector.color.ColorPuck</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Selects this puck.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>ColorPuck</code> instance.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="shiftAngle">
	<h5><a href="#shiftAngle">shiftAngle</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorPuck:shiftAngle(amount) -&gt; cp.apple.finalcutpro.inspector.color.ColorPuck</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Shifts the angle value by the provide amount.</p>
<p>Parameters:</p>
<ul>
<li>amount - The amount to shift the angle value.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>ColorPuck</code> instance.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="shiftPercent">
	<h5><a href="#shiftPercent">shiftPercent</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorPuck:shiftPercent(amount) -&gt; cp.apple.finalcutpro.inspector.color.ColorPuck</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Shifts the percent value by the provide amount.</p>
<p>Parameters:</p>
<ul>
<li><code>amount</code> - The amount to shift the percent value.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The updated value.</li>
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
		<td><code>cp.apple.finalcutpro.inspector.color.ColorPuck:show() -&gt; cp.apple.finalcutpro.inspector.color.ColorPuck</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Shows the Color Puck</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.apple.finalcutpro.inspector.color.ColorPuck</code> object for method chaining.</li>
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
		<td><code>cp.apple.finalcutpro.inspector.color.ColorPuck:start() -&gt; cp.apple.finalcutpro.inspector.color.ColorPuck</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Starts a Color Puck.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>ColorPuck</code> instance.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="stop">
	<h5><a href="#stop">stop</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorPuck:stop() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Stops a Color Puck.</p>
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
  <section id="UI">
	<h5><a href="#UI">UI</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorPuck:UI() -&gt; axuielementObject</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the Color Puck Accessibility Object</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>An <code>axuielementObject</code> or <code>nil</code></li>
</ul>
</td>
	  </tr>
	</table>
  </section>
