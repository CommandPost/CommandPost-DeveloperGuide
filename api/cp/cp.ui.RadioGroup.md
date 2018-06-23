# [docs](index.md) » cp.ui.RadioGroup
---

Represents an `AXRadioGroup`, providing utility methods.

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
<li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
  <ul>
	<li><a href="#optionCount">optionCount</a></li>
	<li><a href="#selectedOption">selectedOption</a></li>
  </ul>
<li>Methods - API calls which can only be made on an object returned by a constructor</li>
  <ul>
	<li><a href="#isEnabled">isEnabled</a></li>
	<li><a href="#isShowing">isShowing</a></li>
	<li><a href="#new">new</a></li>
	<li><a href="#nextOption">nextOption</a></li>
	<li><a href="#parent">parent</a></li>
	<li><a href="#previousOption">previousOption</a></li>
	<li><a href="#snapshot">snapshot</a></li>
	<li><a href="#UI">UI</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="matches">
	<h5><a href="#matches">matches</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.RadioGroup.matches(element) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Checks if the provided <code>axuielement</code> is a RadioGroup.</p>
<p>Parameters:</p>
<ul>
<li>element   - The element to check.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the element is a RadioGroup.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Fields</h4>
  <section id="optionCount">
	<h5><a href="#optionCount">optionCount</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.RadioGroup.optionCount &lt;cp.prop: number; read-only&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The number of options in the group.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="selectedOption">
	<h5><a href="#selectedOption">selectedOption</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.RadioGroup.selectedOption &lt;cp.prop: number&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The currently selected option number.</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Methods</h4>
  <section id="isEnabled">
	<h5><a href="#isEnabled">isEnabled</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.RadioGroup:isEnabled()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Checks if the RadioGroup is enabled.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the RadioGroup is showing and enabled.</li>
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
		<td><code>cp.ui.RadioGroup:isShowing() -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Checks if the RadioGroup is visible.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the RadioGroup is visible.</li>
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
		<td><code>cp.ui.RadioGroup.new(parent, finderFn[, cached]) -&gt; RadioGroup</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new RadioGroup.</p>
<p>Parameters:</p>
<ul>
<li>parent    - The parent table.</li>
<li>finderFn  - The function which will find the <code>axuielement</code> representing the RadioGroup.</li>
<li>cached    - If set to <code>false</code>, the <code>axuielement</code> will not be cached. Defaults to <code>true</code>.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The new <code>RadioGroup</code> instance.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="nextOption">
	<h5><a href="#nextOption">nextOption</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.RadioGroup:nextOption() -&gt; self</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Selects the next option in the group. Cycles from the last to the first option.</p>
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
  <section id="parent">
	<h5><a href="#parent">parent</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.RadioGroup:parent() -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the parent object.</p>
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
  <section id="previousOption">
	<h5><a href="#previousOption">previousOption</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.RadioGroup:previousOption() -&gt; self</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Selects the previous option in the group. Cycles from the first to the last item.</p>
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
  <section id="snapshot">
	<h5><a href="#snapshot">snapshot</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.RadioGroup:snapshot([path]) -&gt; hs.image | nil</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Takes a snapshot of the UI in its current state as a PNG and returns it.
If the <code>path</code> is provided, the image will be saved at the specified location.</p>
<p>Parameters:</p>
<ul>
<li>path      - (optional) The path to save the file. Should include the extension (should be <code>.png</code>).</li>
</ul>
<p>Return:</p>
<ul>
<li>The <code>hs.image</code> that was created, or <code>nil</code> if the UI is not available.</li>
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
		<td><code>cp.ui.RadioGroup:UI() -&gt; axuielement</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the <code>axuielement</code> for the RadioGroup, or <code>nil</code> if not currently visible.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>asuielement</code> or <code>nil</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
