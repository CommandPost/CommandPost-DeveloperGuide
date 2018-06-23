# [docs](index.md) » cp.apple.finalcutpro.main.TimelineContents
---

Timeline Contents Module.

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
	<li><a href="#clipsUI">clipsUI</a></li>
	<li><a href="#playheadClipsUI">playheadClipsUI</a></li>
  </ul>
<li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
  <ul>
	<li><a href="#horizontalScrollBarUI">horizontalScrollBarUI</a></li>
	<li><a href="#isFocused">isFocused</a></li>
	<li><a href="#isLoaded">isLoaded</a></li>
	<li><a href="#isShowing">isShowing</a></li>
	<li><a href="#scrollAreaUI">scrollAreaUI</a></li>
	<li><a href="#UI">UI</a></li>
	<li><a href="#verticalScrollBarUI">verticalScrollBarUI</a></li>
	<li><a href="#viewFrame">viewFrame</a></li>
  </ul>
<li>Methods - API calls which can only be made on an object returned by a constructor</li>
  <ul>
	<li><a href="#rangeSelectionUI">rangeSelectionUI</a></li>
	<li><a href="#selectedClipsUI">selectedClipsUI</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="clipsUI">
	<h5><a href="#clipsUI">clipsUI</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.TimelineContents:clipsUI(expandedGroups, filterFn) -&gt; table of axuielements</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a table containing the list of clips in the Timeline.</p>
<p>If <code>expandsGroups</code> is true any AXGroup items will be expanded to the list of contained AXLayoutItems.</p>
<p>If <code>filterFn</code> is provided it will be called with a single argument to check if the provided
clip should be included in the final table.</p>
<p>Parameters:</p>
<ul>
<li>expandGroups - (optional) if true, expand AXGroups to include contained AXLayoutItems</li>
<li>filterFn     - (optional) if provided, the function will be called to check each clip</li>
</ul>
<p>Returns:</p>
<ul>
<li>The table of axuielements that match the conditions</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="playheadClipsUI">
	<h5><a href="#playheadClipsUI">playheadClipsUI</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.TimelineContents:playheadClipsUI(expandedGroups, filterFn) -&gt; table of axuielements</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a table array containing the list of clips in the Timeline under the playhead, ordered with the
highest clips at the beginning of the array.</p>
<p>If <code>expandsGroups</code> is true any AXGroup items will be expanded to the list of contained <code>AXLayoutItems</code>.</p>
<p>If <code>filterFn</code> is provided it will be called with a single argument to check if the provided
clip should be included in the final table.</p>
<p>Parameters:</p>
<ul>
<li>expandGroups - (optional) if true, expand AXGroups to include contained AXLayoutItems</li>
<li>filterFn     - (optional) if provided, the function will be called to check each clip</li>
</ul>
<p>Returns:</p>
<ul>
<li>The table of axuielements that match the conditions</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Fields</h4>
  <section id="horizontalScrollBarUI">
	<h5><a href="#horizontalScrollBarUI">horizontalScrollBarUI</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.TimelineContents.horizontalScrollBarUI &lt;cp.prop: hs._asm.axuielement; read-only; live&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The <code>AXHorizontalScrolLbar</code> for the Timeline Contents area.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="isFocused">
	<h5><a href="#isFocused">isFocused</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.TimelineContents.isFocused &lt;cp.prop: booelan; read-only&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Checks if the Timeline is currently the focused panel.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="isLoaded">
	<h5><a href="#isLoaded">isLoaded</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.TimelineContents.isLoaded &lt;cp.prop: booelan; read-only; live&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Checks if the Timeline has content loaded.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="isShowing">
	<h5><a href="#isShowing">isShowing</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.TimelineContents.isShowing &lt;cp.prop: booelan; read-only; live&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Checks if the Timeline is currently showing.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="scrollAreaUI">
	<h5><a href="#scrollAreaUI">scrollAreaUI</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.TimelineContents.scrollAreaUI &lt;cp.prop: hs._asm.axuielement; read-only; live&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The parent <code>ScrollArea</code> UI of the Timeline Contents area.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="UI">
	<h5><a href="#UI">UI</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.TimelineContents.UI &lt;cp.prop: hs._asm.axuielement; read-only; live&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The main UI of the Timeline Contents area.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="verticalScrollBarUI">
	<h5><a href="#verticalScrollBarUI">verticalScrollBarUI</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.TimelineContents.verticalScrollBarUI &lt;cp.prop: hs._asm.axuielement; read-only; live&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The <code>AXVerticalScrollBar</code> for the Timeline Contents area.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="viewFrame">
	<h5><a href="#viewFrame">viewFrame</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.TimelineContents.viewFrame &lt;cp.prop: table; read-only; live&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The current 'frame' of the internal timeline content,  or <code>nil</code> if not available.</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Methods</h4>
  <section id="rangeSelectionUI">
	<h5><a href="#rangeSelectionUI">rangeSelectionUI</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.TimelineContents:rangeSelectionUI() -&gt; axuielements</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the UI for the current 'Range Selection', if present.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The 'Range Selection' UI or <code>nil</code></li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="selectedClipsUI">
	<h5><a href="#selectedClipsUI">selectedClipsUI</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.apple.finalcutpro.main.TimelineContents:selectedClipsUI(expandedGroups, filterFn) -&gt; table of axuielements</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a table containing the list of selected clips.</p>
<p>If <code>expandsGroups</code> is true any AXGroup items will be expanded to the list of contained AXLayoutItems.</p>
<p>If <code>filterFn</code> is provided it will be called with a single argument to check if the provided
clip should be included in the final table.</p>
<p>Parameters:</p>
<ul>
<li>expandGroups - (optional) if true, expand AXGroups to include contained AXLayoutItems</li>
<li>filterFn     - (optional) if provided, the function will be called to check each clip</li>
</ul>
<p>Returns:</p>
<ul>
<li>The table of selected axuielements that match the conditions</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
