# [docs](index.md) » cp.ui.axutils
---

Utility functions to support `hs._asm.axuielement`.

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
	<li><a href="#cache">cache</a></li>
	<li><a href="#childAtIndex">childAtIndex</a></li>
	<li><a href="#childFromBottom">childFromBottom</a></li>
	<li><a href="#childFromLeft">childFromLeft</a></li>
	<li><a href="#childFromRight">childFromRight</a></li>
	<li><a href="#childFromTop">childFromTop</a></li>
	<li><a href="#childMatching">childMatching</a></li>
	<li><a href="#children">children</a></li>
	<li><a href="#childrenMatching">childrenMatching</a></li>
	<li><a href="#childrenWith">childrenWith</a></li>
	<li><a href="#childrenWithRole">childrenWithRole</a></li>
	<li><a href="#childWith">childWith</a></li>
	<li><a href="#childWithDescription">childWithDescription</a></li>
	<li><a href="#childWithID">childWithID</a></li>
	<li><a href="#childWithRole">childWithRole</a></li>
	<li><a href="#compareBottomToTop">compareBottomToTop</a></li>
	<li><a href="#compareLeftToRight">compareLeftToRight</a></li>
	<li><a href="#compareRightToLeft">compareRightToLeft</a></li>
	<li><a href="#compareTopToBottom">compareTopToBottom</a></li>
	<li><a href="#hasAttributeValue">hasAttributeValue</a></li>
	<li><a href="#isValid">isValid</a></li>
	<li><a href="#snapshot">snapshot</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="cache">
	<h5><a href="#cache">cache</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.axutils.cache(source, key, finderFn, [verifyFn]) -&gt; axuielement</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Checks if the cached value at the <code>source[key]</code> is a valid axuielement. If not
it will call the provided <code>finderFn()</code> function (with no arguments), cache the result and return it.</p>
<p>If the optional <code>verifyFn</code> is provided, it will be called to check that the cached
value is still valid. It is passed a single parameter (the axuielement) and is expected
to return <code>true</code> or <code>false</code>.</p>
<p>Parameters:</p>
<ul>
<li>source       - the table containing the cache</li>
<li>key          - the key the value is cached under</li>
<li>finderFn     - the function which will return the element if not found.</li>
<li>[verifyFn]   - an optional function which will check the cached element to verify it is still valid.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The valid cached value.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="childAtIndex">
	<h5><a href="#childAtIndex">childAtIndex</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.axutils.childAtIndex(element, index, compareFn[, matcherFn]) -&gt; axuielement</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Searches for the child element which is at number <code>index</code> when sorted using the <code>compareFn</code>.</p>
<p>Parameters:</p>
<ul>
<li>element      - the axuielement or array of axuielements</li>
<li>index        - the index number of the child to find.</li>
<li>compareFn    - a function to compare the elements.</li>
<li>matcherFn    - an optional function which is passed each child and returns <code>true</code> if the child should be processed.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The child, or <code>nil</code> if the index is larger than the number of children.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="childFromBottom">
	<h5><a href="#childFromBottom">childFromBottom</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.axutils.childFromBottom(element, index) -&gt; axuielement</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Searches for the child element which is at number <code>index</code> when sorted bottom-to-top.</p>
<p>Parameters:</p>
<ul>
<li>element      - the axuielement or array of axuielements</li>
<li>index        - the index number of the child to find.</li>
<li>matcherFn    - an optional function which is passed each child and returns <code>true</code> if the child should be processed.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The child, or <code>nil</code> if the index is larger than the number of children.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="childFromLeft">
	<h5><a href="#childFromLeft">childFromLeft</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.axutils.childFromLeft(element, index[, matcherFn]) -&gt; axuielement</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Searches for the child element which is at number <code>index</code> when sorted left-to-right.</p>
<p>Parameters:</p>
<ul>
<li>element      - the axuielement or array of axuielements</li>
<li>index        - the index number of the child to find.</li>
<li>matcherFn    - an optional function which is passed each child and returns <code>true</code> if the child should be processed.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The child, or <code>nil</code> if the index is larger than the number of children.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="childFromRight">
	<h5><a href="#childFromRight">childFromRight</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.axutils.childFromRight(element, index[, matcherFn]) -&gt; axuielement</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Searches for the child element which is at number <code>index</code> when sorted right-to-left.</p>
<p>Parameters:</p>
<ul>
<li>element      - the axuielement or array of axuielements</li>
<li>index        - the index number of the child to find.</li>
<li>matcherFn    - an optional function which is passed each child and returns <code>true</code> if the child should be processed.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The child, or <code>nil</code> if the index is larger than the number of children.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="childFromTop">
	<h5><a href="#childFromTop">childFromTop</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.axutils.childFromTop(element, index[, matcherFn]) -&gt; axuielement</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Searches for the child element which is at number <code>index</code> when sorted top-to-bottom.</p>
<p>Parameters:</p>
<ul>
<li>element      - the axuielement or array of axuielements</li>
<li>index        - the index number of the child to find.</li>
<li>matcherFn    - an optional function which is passed each child and returns <code>true</code> if the child should be processed.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The child, or <code>nil</code> if the index is larger than the number of children.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="childMatching">
	<h5><a href="#childMatching">childMatching</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.axutils.childMatching(element, matcherFn[, index]) -&gt; axuielement</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>This searches for the first child of the specified element for which the provided function returns <code>true</code>.
The function will receive one parameter - the current child.</p>
<p>Parameters:</p>
<ul>
<li>element      - the axuielement</li>
<li>matcherFn    - the function which checks if the child matches the requirements.</li>
<li>index        - the number of matching child to return. Defaults to <code>1</code>.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The first matching child, or nil if none was found</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="children">
	<h5><a href="#children">children</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.axutils.children(element) -&gt; table | nil</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Finds the children for the element. If it is an <code>hs._asm.axuielement</code>, it will
attempt to get the <code>AXChildren</code> attribute. If it is a table with a <code>children</code> function,
that will get called. Otherwise, the element is returned.</p>
<p>Parameters:</p>
<ul>
<li>element   - The element to retrieve the children of.</li>
</ul>
<p>Returns:</p>
<ul>
<li>the children table, or <code>nil</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="childrenMatching">
	<h5><a href="#childrenMatching">childrenMatching</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.axutils.childrenMatching(element, matcherFn) -&gt; { axuielement }</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>This searches for all children of the specified element for which the provided
function returns <code>true</code>. The function will receive one parameter - the current child.</p>
<p>Parameters:</p>
<ul>
<li>element  - the axuielement</li>
<li>matcherFn    - the function which checks if the child matches the requirements.</li>
</ul>
<p>Returns:</p>
<ul>
<li>All matching children, or <code>nil</code> if none was found</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="childrenWith">
	<h5><a href="#childrenWith">childrenWith</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.axutils.childrenWith(element, name, value) -&gt; axuielement</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>This searches for all children of the specified element which has an attribute with the matching name and value.</p>
<p>Parameters:</p>
<ul>
<li>element  - the axuielement</li>
<li>name     - the name of the attribute</li>
<li>value    - the value of the attribute</li>
</ul>
<p>Returns:</p>
<ul>
<li>All matching children, or <code>nil</code> if none was found</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="childrenWithRole">
	<h5><a href="#childrenWithRole">childrenWithRole</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.axutils.childrenWithRole(element, value) -&gt; axuielement</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>This searches for all children of the specified element which has an <code>AXRole</code> attribute with the matching value.</p>
<p>Parameters:</p>
<ul>
<li>element  - the axuielement</li>
<li>value    - the value of the attribute</li>
</ul>
<p>Returns:</p>
<ul>
<li>All matching children, or <code>nil</code> if none was found</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="childWith">
	<h5><a href="#childWith">childWith</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.axutils.childWith(element, name, value) -&gt; axuielement</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>This searches for the first child of the specified element which has an attribute with the matching name and value.</p>
<p>Parameters:</p>
<ul>
<li>element  - the axuielement</li>
<li>name     - the name of the attribute</li>
<li>value    - the value of the attribute</li>
</ul>
<p>Returns:</p>
<ul>
<li>The first matching child, or nil if none was found</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="childWithDescription">
	<h5><a href="#childWithDescription">childWithDescription</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.axutils.childWithDescription(element, value) -&gt; axuielement</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>This searches for the first child of the specified element which has <code>AXDescription</code> with the specified value.</p>
<p>Parameters:</p>
<ul>
<li>element  - the axuielement</li>
<li>value    - the value</li>
</ul>
<p>Returns:</p>
<ul>
<li>The first matching child, or <code>nil</code> if none was found</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="childWithID">
	<h5><a href="#childWithID">childWithID</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.axutils.childWithID(element, value) -&gt; axuielement</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>This searches for the first child of the specified element which has <code>AXIdentifier</code> with the specified value.</p>
<p>Parameters:</p>
<ul>
<li>element  - the axuielement</li>
<li>value    - the value</li>
</ul>
<p>Returns:</p>
<ul>
<li>The first matching child, or <code>nil</code> if none was found</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="childWithRole">
	<h5><a href="#childWithRole">childWithRole</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.axutils.childWithRole(element, value) -&gt; axuielement</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>This searches for the first child of the specified element which has <code>AXRole</code> with the specified value.</p>
<p>Parameters:</p>
<ul>
<li>element  - the axuielement</li>
<li>value    - the value</li>
</ul>
<p>Returns:</p>
<ul>
<li>The first matching child, or <code>nil</code> if none was found</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="compareBottomToTop">
	<h5><a href="#compareBottomToTop">compareBottomToTop</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.axutils.compareBottomToTop(a, b) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns <code>true</code> if element <code>a</code> is below element <code>b</code>. May be used with <code>table.sort</code>.</p>
<p>Parameters</p>
<ul>
<li>a    - The first element</li>
<li>b    - The second element</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if <code>a</code> is below <code>b</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="compareLeftToRight">
	<h5><a href="#compareLeftToRight">compareLeftToRight</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.axutils.compareLeftToRight(a, b) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns <code>true</code> if element <code>a</code> is left of element <code>b</code>. May be used with <code>table.sort</code>.</p>
<p>Parameters</p>
<ul>
<li>a    - The first element</li>
<li>b    - The second element</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if <code>a</code> is left of <code>b</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="compareRightToLeft">
	<h5><a href="#compareRightToLeft">compareRightToLeft</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.axutils.compareRightToLeft(a, b) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns <code>true</code> if element <code>a</code> is right of element <code>b</code>. May be used with <code>table.sort</code>.</p>
<p>Parameters</p>
<ul>
<li>a    - The first element</li>
<li>b    - The second element</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if <code>a</code> is right of <code>b</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="compareTopToBottom">
	<h5><a href="#compareTopToBottom">compareTopToBottom</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.axutils.compareTopToBottom(a, b) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns <code>true</code> if element <code>a</code> is above element <code>b</code>. May be used with <code>table.sort</code>.</p>
<p>Parameters</p>
<ul>
<li>a    - The first element</li>
<li>b    - The second element</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if <code>a</code> is above <code>b</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="hasAttributeValue">
	<h5><a href="#hasAttributeValue">hasAttributeValue</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.axutils.hasAttributeValue(element, name, value) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Checks to see if an element has a specific value.</p>
<p>Parameters:</p>
<ul>
<li>element  - the <code>axuielement</code></li>
<li>name     - the name of the attribute</li>
<li>value    - the value of the attribute</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the <code>element</code> has the supplied attribute value, otherwise <code>false</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="isValid">
	<h5><a href="#isValid">isValid</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.ui.axutils.isValid(element) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Checks if the axuilelement is still valid - that is, still active in the UI.</p>
<p>Parameters:</p>
<ul>
<li>element  - the axuielement</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the element is valid.</li>
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
		<td><code>cp.ui.axutils.snapshot(element, [filename]) -&gt; hs.image</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Takes a snapshot of the specified <code>axuielement</code> and returns it.
If the <code>filename</code> is provided it also saves the file to the specified location.</p>
<p>Parameters:</p>
<ul>
<li>element      - The <code>axuielement</code> to snap.</li>
<li>filename     - (optional) The path to save the image as a PNG file.</li>
</ul>
<p>Returns:</p>
<ul>
<li>An <code>hs.image</code> file, or <code>nil</code> if the element could not be snapped.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
