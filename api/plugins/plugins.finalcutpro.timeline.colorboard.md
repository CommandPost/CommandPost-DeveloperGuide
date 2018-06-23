# [docs](index.md) » plugins.finalcutpro.timeline.colorboard
---

Color Board Plugins.

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
	<li><a href="#colorBoardMousePuckRelease">colorBoardMousePuckRelease</a></li>
	<li><a href="#nextAspect">nextAspect</a></li>
	<li><a href="#startMousePuck">startMousePuck</a></li>
	<li><a href="#startShiftingPuck">startShiftingPuck</a></li>
	<li><a href="#stopShiftingPuck">stopShiftingPuck</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="colorBoardMousePuckRelease">
	<h5><a href="#colorBoardMousePuckRelease">colorBoardMousePuckRelease</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.timeline.colorboard.colorBoardMousePuckRelease() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Color Board Mouse Puck Release</p>
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
  <section id="nextAspect">
	<h5><a href="#nextAspect">nextAspect</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.timeline.colorboard.nextAspect() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Goes to the next Color Board aspect.</p>
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
  <section id="startMousePuck">
	<h5><a href="#startMousePuck">startMousePuck</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.timeline.colorboard.startMousePuck(aspect, property) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Color Board - Puck Control Via Mouse</p>
<p>Parameters:</p>
<ul>
<li>aspect - "global", "shadows", "midtones" or "highlights"</li>
<li>property - "Color", "Saturation" or "Exposure"</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="startShiftingPuck">
	<h5><a href="#startShiftingPuck">startShiftingPuck</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.timeline.colorboard.startShiftingPuck(puck, percentShift, angleShift) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Starts shifting the puck, repeating at the keyboard repeat rate. Runs until <code>stopShiftingPuck()</code> is called.</p>
<p>Parameters:</p>
<ul>
<li>puck         - The puck to shift</li>
<li>property     - The property to shift (typically the <code>percent</code> or <code>angle</code> value for the puck)</li>
<li>amount       - The amount to shift the property.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="stopShiftingPuck">
	<h5><a href="#stopShiftingPuck">stopShiftingPuck</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.timeline.colorboard.stopShiftingPuck() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Stops the puck from shifting with the keyboard.</p>
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
