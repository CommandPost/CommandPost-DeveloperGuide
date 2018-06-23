# [docs](index.md) » cp.apple.finalcutpro.inspector.color.ColorWell
---

Represents a single Color Well in the Color Wheels Inspector.

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
	<li><a href="#KEY_PRESS">KEY_PRESS</a></li>
  </ul>
<li>Functions - API calls offered directly by the extension</li>
  <ul>
	<li><a href="#matches">matches</a></li>
  </ul>
<li>Constructors - API calls which return an object, typically one that offers API methods</li>
  <ul>
	<li><a href="#new">new</a></li>
  </ul>
<li>Methods - API calls which can only be made on an object returned by a constructor</li>
  <ul>
	<li><a href="#app">app</a></li>
	<li><a href="#nudge">nudge</a></li>
	<li><a href="#parent">parent</a></li>
	<li><a href="#reset">reset</a></li>
	<li><a href="#select">select</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Constants</h4>
  <section id="KEY_PRESS">
	<h5><a href="#KEY_PRESS">KEY_PRESS</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWell.KEY_PRESS</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>This can be used with <code>nudge</code> to shift by the same distance
as a key press. Multiple key presses can be simulated by
multiplying it by the number of keys. For example:</p>
<div class="highlight"><pre><span></span><span class="c1">-- Nudge it two key presses to the right</span>
<span class="n">colorWell</span><span class="p">:</span><span class="n">nudge</span><span class="p">(</span><span class="mi">2</span><span class="o">*</span><span class="n">ColorWell</span><span class="p">.</span><span class="n">KEY_PRESS</span><span class="p">,</span> <span class="mi">0</span><span class="p">)</span>
</pre></div>
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
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWell.matches(element)</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Checks if the specified element is a Color Well.</p>
<p>Parameters:</p>
<ul>
<li>element   - The element to check</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the element is a Color Well.</li>
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
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWell.new(parent, finderFn) -&gt; ColorWell</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constructor</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new <code>ColorWell</code> instance, with the specified parent and finder function.
The finder function should return the specific color well UI element that this instance represents.</p>
<p>Parameters:</p>
<ul>
<li>parent - The parent object</li>
<li>finderFn - Returns the <code>axuielement</code> that represents the color well.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A new <code>ColorWell</code> instance.</li>
</ul>
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
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWell:app() -&gt; cp.apple.finalcutpro</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the Final Cut Pro object.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The Final Cut Pro object.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="nudge">
	<h5><a href="#nudge">nudge</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWell:nudge(right, up) -&gt; self</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Nudges the <code>colorPosition</code> by <code>right</code>/<code>up</code> values. Negative <code>right</code> values shift left,
negative <code>up</code> values shift down. You may have decimal shift values.</p>
<p>Parameters:</p>
<ul>
<li><code>right</code> - The number of steps to shift right. May be negative to shift left.</li>
<li><code>up</code> - The number of pixels to shift down. May be negative to shift down.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>ColorWell</code> instance.</li>
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
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWell:parent() -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the Color Well parent table</p>
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
  <section id="reset">
	<h5><a href="#reset">reset</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWell:reset() -&gt; self</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Resets the color wheel.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>ColorWell</code> instance.</li>
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
		<td><code>cp.apple.finalcutpro.inspector.color.ColorWell:select() -&gt; cp.apple.finalcutpro.inspector.color.ColorWell</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Selects this color well.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>ColorWell</code> instance.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
