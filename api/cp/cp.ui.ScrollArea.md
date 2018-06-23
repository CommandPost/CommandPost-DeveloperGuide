# [docs](index.md) » cp.ui.ScrollArea
---

Scroll Area Module.

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
<li>Methods - API calls which can only be made on an object returned by a constructor</li>
  <ul>
	<li><a href="#app">app</a></li>
	<li><a href="#childrenUI">childrenUI</a></li>
	<li><a href="#contentsUI">contentsUI</a></li>
	<li><a href="#deselectAll">deselectAll</a></li>
	<li><a href="#horizontalScrollBarUI">horizontalScrollBarUI</a></li>
	<li><a href="#isShowing">isShowing</a></li>
	<li><a href="#loadLayout">loadLayout</a></li>
	<li><a href="#parent">parent</a></li>
	<li><a href="#saveLayout">saveLayout</a></li>
	<li><a href="#selectAll">selectAll</a></li>
	<li><a href="#selectChild">selectChild</a></li>
	<li><a href="#selectChildAt">selectChildAt</a></li>
	<li><a href="#selectedChildrenUI">selectedChildrenUI</a></li>
	<li><a href="#showChild">showChild</a></li>
	<li><a href="#showChildAt">showChildAt</a></li>
	<li><a href="#snapshot">snapshot</a></li>
	<li><a href="#UI">UI</a></li>
	<li><a href="#verticalScrollBarUI">verticalScrollBarUI</a></li>
	<li><a href="#viewFrame">viewFrame</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="matches">
	<h5><a href="#matches">matches</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.ScrollArea.matches(element) -&gt; boolean</code></td>
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
		<td><code>cp.ui.ScrollArea.new(parent, finderFn) -&gt; cp.ui.ScrollArea</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constructor</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new <code>ScrollArea</code>.</p>
<p>Parameters:</p>
<ul>
<li>parent       - The parent object.</li>
<li>finderFn     - A function which will return the <code>hs._asm.axuielement</code> when available.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The new <code>ScrollArea</code>.</li>
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
		<td><code>cp.ui.ScrollArea:app() -&gt; App</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the app instance representing Final Cut Pro.</p>
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
  <section id="childrenUI">
	<h5><a href="#childrenUI">childrenUI</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.ScrollArea:childrenUI(filterFn) -&gt; hs._asm.axuielement | nil</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the <code>axuielement</code> representing the Scroll Area Contents, or <code>nil</code> if not available.</p>
<p>Parameters:</p>
<ul>
<li>filterFn - The function which checks if the child matches the requirements.</li>
</ul>
<p>Return:</p>
<ul>
<li>The <code>axuielement</code> or <code>nil</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="contentsUI">
	<h5><a href="#contentsUI">contentsUI</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.ScrollArea:contentsUI() -&gt; hs._asm.axuielement | nil</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the <code>axuielement</code> representing the Scroll Area Contents, or <code>nil</code> if not available.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Return:</p>
<ul>
<li>The <code>axuielement</code> or <code>nil</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="deselectAll">
	<h5><a href="#deselectAll">deselectAll</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.ScrollArea:deselectAll() -&gt; self</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Deselect all children in a scroll area.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Return:</p>
<ul>
<li>Self</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="horizontalScrollBarUI">
	<h5><a href="#horizontalScrollBarUI">horizontalScrollBarUI</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.ScrollArea:horizontalScrollBarUI() -&gt; hs._asm.axuielement | nil</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the <code>axuielement</code> representing the Horizontal Scroll Bar, or <code>nil</code> if not available.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Return:</p>
<ul>
<li>The <code>axuielement</code> or <code>nil</code>.</li>
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
		<td><code>cp.ui.ScrollArea:isShowing() -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Is the Scroll Area showing?</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Return:</p>
<ul>
<li><code>true</code> if showing otherwise `false.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="loadLayout">
	<h5><a href="#loadLayout">loadLayout</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.ScrollArea:loadLayout(layout) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Loads a Scroll Area layout.</p>
<p>Parameters:</p>
<ul>
<li>layout - A table containing the Browser layout settings - created using <code>cp.apple.finalcutpro.main.Browser:saveLayout()</code>.</li>
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
		<td><code>cp.ui.ScrollArea:parent() -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The parent object.</p>
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
  <section id="saveLayout">
	<h5><a href="#saveLayout">saveLayout</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.ScrollArea:saveLayout() -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Saves the current Scroll Area layout to a table.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table containing the current Scroll Area Layout.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="selectAll">
	<h5><a href="#selectAll">selectAll</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.ScrollArea:selectAll(childrenUI) -&gt; self</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Select all children in a scroll area.</p>
<p>Parameters:</p>
<ul>
<li>childrenUI - A table of <code>hs._asm.axuielement</code> objects.</li>
</ul>
<p>Return:</p>
<ul>
<li>Self</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="selectChild">
	<h5><a href="#selectChild">selectChild</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.ScrollArea:selectChild(childUI) -&gt; self</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Select a specific child within a Scroll Area.</p>
<p>Parameters:</p>
<ul>
<li>childUI - The <code>hs._asm.axuielement</code> object of the child you want to select.</li>
</ul>
<p>Return:</p>
<ul>
<li>Self</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="selectChildAt">
	<h5><a href="#selectChildAt">selectChildAt</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.ScrollArea:selectChildAt(index) -&gt; self</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Select a child element in a Scroll Area given a specific index.</p>
<p>Parameters:</p>
<ul>
<li>index - The index of the child you want to select.</li>
</ul>
<p>Return:</p>
<ul>
<li>Self</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="selectedChildrenUI">
	<h5><a href="#selectedChildrenUI">selectedChildrenUI</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.ScrollArea:selectedChildrenUI() -&gt; hs._asm.axuielement | nil</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the <code>axuielement</code> representing the Scroll Area Selected Children, or <code>nil</code> if not available.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Return:</p>
<ul>
<li>The <code>axuielement</code> or <code>nil</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="showChild">
	<h5><a href="#showChild">showChild</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.ScrollArea:showChild(childUI) -&gt; self</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Show's a child element in a Scroll Area.</p>
<p>Parameters:</p>
<ul>
<li>childUI - The <code>hs._asm.axuielement</code> object of the child you want to show.</li>
</ul>
<p>Return:</p>
<ul>
<li>Self</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="showChildAt">
	<h5><a href="#showChildAt">showChildAt</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.ScrollArea:showChildAt(index) -&gt; self</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Show's a child element in a Scroll Area given a specific index.</p>
<p>Parameters:</p>
<ul>
<li>index - The index of the child you want to show.</li>
</ul>
<p>Return:</p>
<ul>
<li>Self</li>
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
		<td><code>cp.ui.ScrollArea:snapshot([path]) -&gt; hs.image | nil</code></td>
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
<li>path - (optional) The path to save the file. Should include the extension (should be <code>.png</code>).</li>
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
		<td><code>cp.ui.ScrollArea:UI() -&gt; hs._asm.axuielement | nil</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the <code>axuielement</code> representing the <code>ScrollArea</code>, or <code>nil</code> if not available.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Return:</p>
<ul>
<li>The <code>axuielement</code> or <code>nil</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="verticalScrollBarUI">
	<h5><a href="#verticalScrollBarUI">verticalScrollBarUI</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.ScrollArea:verticalScrollBarUI() -&gt; hs._asm.axuielement | nil</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the <code>axuielement</code> representing the Vertical Scroll Bar, or <code>nil</code> if not available.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Return:</p>
<ul>
<li>The <code>axuielement</code> or <code>nil</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="viewFrame">
	<h5><a href="#viewFrame">viewFrame</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.ScrollArea:viewFrame() -&gt; hs.geometry rect</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the Scroll Area frame.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Return:</p>
<ul>
<li>The frame in the form of a <code>hs.geometry</code> rect object.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
