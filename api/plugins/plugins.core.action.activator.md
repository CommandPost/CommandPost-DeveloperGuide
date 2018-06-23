# [docs](index.md) » plugins.core.action.activator
---

This module provides provides a way of activating choices provided by action handlers.
It also provide support for making a particular action a favourite, returning
results based on popularity, and completely hiding particular actions, or categories of action.

Activators are accessed via the [action manager](plugins.core.action.manager.md) like so:

```lua
local activator = actionManager.getActivator("foobar")
activator:disableHandler("videoEffect")
activator:show()
```

Any changes made to the settings of a finder (such as calling `disableHandler` above) will
be preserved for future loads of the finder with the same ID. They are also local
to instances of this activator, so disabling "videoEffect" in the "foobar" activator
will not affect the "yadayada" activator.

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
<li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
  <ul>
	<li><a href="#reducedTransparency">reducedTransparency</a></li>
  </ul>
<li>Methods - API calls which can only be made on an object returned by a constructor</li>
  <ul>
	<li><a href="#activate">activate</a></li>
	<li><a href="#activeChoices">activeChoices</a></li>
	<li><a href="#allChoices">allChoices</a></li>
	<li><a href="#allowHandlers">allowHandlers</a></li>
	<li><a href="#disableAllHandlers">disableAllHandlers</a></li>
	<li><a href="#disableHandler">disableHandler</a></li>
	<li><a href="#enableAllHandlers">enableAllHandlers</a></li>
	<li><a href="#enableHandler">enableHandler</a></li>
	<li><a href="#favoriteChoice">favoriteChoice</a></li>
	<li><a href="#findChoice">findChoice</a></li>
	<li><a href="#getActiveHandler">getActiveHandler</a></li>
	<li><a href="#getPopularity">getPopularity</a></li>
	<li><a href="#hide">hide</a></li>
	<li><a href="#hideChoice">hideChoice</a></li>
	<li><a href="#id">id</a></li>
	<li><a href="#incPopularity">incPopularity</a></li>
	<li><a href="#isDisabledHandler">isDisabledHandler</a></li>
	<li><a href="#isHiddenChoice">isHiddenChoice</a></li>
	<li><a href="#onActivate">onActivate</a></li>
	<li><a href="#preloadChoices">preloadChoices</a></li>
	<li><a href="#refresh">refresh</a></li>
	<li><a href="#refreshChooser">refreshChooser</a></li>
	<li><a href="#rightClickAction">rightClickAction</a></li>
	<li><a href="#rightClickMain">rightClickMain</a></li>
	<li><a href="#show">show</a></li>
	<li><a href="#sortChoices">sortChoices</a></li>
	<li><a href="#unfavoriteChoice">unfavoriteChoice</a></li>
	<li><a href="#unhiddenChoices">unhiddenChoices</a></li>
	<li><a href="#unhideChoice">unhideChoice</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Fields</h4>
  <section id="reducedTransparency">
	<h5><a href="#reducedTransparency">reducedTransparency</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.action.activator.reducedTransparency &lt;cp.prop: boolean&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>A property which will be true if the 'reduce transparency' mode is enabled.</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Methods</h4>
  <section id="activate">
	<h5><a href="#activate">activate</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.action.activator:activate(result) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Triggered when the chooser is closed.</p>
<p>Parameters:</p>
<ul>
<li><code>result</code>      - The result from the chooser.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="activeChoices">
	<h5><a href="#activeChoices">activeChoices</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.action.activator:activeChoices() -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a table with active choices. If <a href="#showHidden">showHidden</a> is set to <code>true</code>  hidden
items are returned, otherwise they are not.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>Table of choices that can be displayed by an <code>hs.chooser</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="allChoices">
	<h5><a href="#allChoices">allChoices</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.action.activator:allChoices() -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a table of all available choices, even if hidden. Choices from
disabled action handlers are not included.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>Table of choices that can be displayed by an <code>hs.chooser</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="allowHandlers">
	<h5><a href="#allowHandlers">allowHandlers</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.action.activator:allowHandlers(...) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Specifies that only the handlers with the specified IDs will be active in
this activator. By default all handlers are allowed.</p>
<p>Parameters:</p>
<ul>
<li><code>...</code>     - The list of Handler ID strings to allow.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the handlers were found.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="disableAllHandlers">
	<h5><a href="#disableAllHandlers">disableAllHandlers</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.action.activator:disableAllHandlers() -&gt; nothing</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Disables the all allowed handlers.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>Nothing</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="disableHandler">
	<h5><a href="#disableHandler">disableHandler</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.action.activator:disableHandler(id) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Disables the handler with the specified ID.</p>
<p>Parameters:</p>
<ul>
<li><code>id</code>      - The unique action handler ID.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the handler exists and was disabled.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="enableAllHandlers">
	<h5><a href="#enableAllHandlers">enableAllHandlers</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.action.activator:enableAllHandlers() -&gt; nothing</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Enables the all allowed handlers.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>Nothing</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="enableHandler">
	<h5><a href="#enableHandler">enableHandler</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.action.activator:enableHandler(id) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Enables the handler with the specified ID.</p>
<p>Parameters:</p>
<ul>
<li><code>id</code>      - The unique action handler ID.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the handler exists and was enabled.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="favoriteChoice">
	<h5><a href="#favoriteChoice">favoriteChoice</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.action.activator:favoriteChoice(id) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Marks the choice with the specified ID as a favorite.</p>
<p>Parameters:</p>
<ul>
<li><code>id</code>          - The choice ID to favorite.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successfully favorited otherwise <code>false</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="findChoice">
	<h5><a href="#findChoice">findChoice</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.action.activator:findChoice(id) -&gt; choice</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets a choice</p>
<p>Parameters:</p>
<ul>
<li><code>id</code>          - The choice ID.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The choice or <code>nil</code> if not found</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getActiveHandler">
	<h5><a href="#getActiveHandler">getActiveHandler</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.action.activator:getActiveHandler(id) -&gt; handler</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the active handler with the specified ID, or <code>nil</code> if not available.</p>
<p>Parameters:</p>
<ul>
<li><code>id</code>      - The Handler ID</li>
</ul>
<p>Returns:</p>
<ul>
<li>The action handler, or <code>nil</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getPopularity">
	<h5><a href="#getPopularity">getPopularity</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.action.activator:getPopularity(id) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the popularity of the specified choice.</p>
<p>Parameters:</p>
<ul>
<li><code>id</code>          - The choice ID to retrieve.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The number of times the choice has been executed.</li>
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
		<td><code>plugins.core.action.activator:hide()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Hides a chooser listing the available actions.</p>
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
  <section id="hideChoice">
	<h5><a href="#hideChoice">hideChoice</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.action.activator:hideChoice(id) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Hides the choice with the specified ID.</p>
<p>Parameters:</p>
<ul>
<li><code>id</code>          - The choice ID to hide.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successfully hidden otherwise <code>false</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="id">
	<h5><a href="#id">id</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.action.activator:id() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the activator's unique ID.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The activator ID.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="incPopularity">
	<h5><a href="#incPopularity">incPopularity</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.action.activator:incPopularity(choice, id) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Increases the popularity of the specified choice.</p>
<p>Parameters:</p>
<ul>
<li><code>choice</code>      - The choice.</li>
<li><code>id</code>          - The choice ID to popularise.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successfully unfavourited, otherwise <code>false</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="isDisabledHandler">
	<h5><a href="#isDisabledHandler">isDisabledHandler</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.action.activator:isDisabledHandler(id) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns <code>true</code> if the specified handler is disabled.</p>
<p>Parameters:</p>
<ul>
<li><code>id</code>          - The handler ID.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the handler is disabled.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="isHiddenChoice">
	<h5><a href="#isHiddenChoice">isHiddenChoice</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.action.activator:isHiddenChoice(id) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Checks if the specified choice is hidden.</p>
<p>Parameters:</p>
<ul>
<li><code>id</code>          - The choice ID to check.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if currently hidden.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="onActivate">
	<h5><a href="#onActivate">onActivate</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.action.activator:onActivate(activateFn) -&gt; activator</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Registers the provided function to handle 'activate' actions, when the user selects
an item in the main chooser.</p>
<p>By default, the activator will 'execute' the action, but you can choose to provide an
alternative action. It will get passed the <code>handler</code> object and the <code>action</code> table. Eg:</p>
<div class="highlight"><pre><span></span><span class="n">activator</span><span class="p">:</span><span class="n">onActivate</span><span class="p">(</span><span class="kr">function</span><span class="p">(</span><span class="n">handler</span><span class="p">,</span> <span class="n">action</span><span class="p">))</span>
</pre></div>
<p>Parameters:</p>
<ul>
<li><code>activateFn</code>      - The function to call when an item is activated.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The activator.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="preloadChoices">
	<h5><a href="#preloadChoices">preloadChoices</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.action.activator:preloadChoices([afterSeconds]) -&gt; activator</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Indicates the activator should preload the choices after a number of seconds.
Defaults to 0 seconds if no value is provided.</p>
<p>Parameters:</p>
<ul>
<li><code>afterSeconds</code>    - The number of seconds to wait before preloading.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The activator.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="refresh">
	<h5><a href="#refresh">refresh</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.action.activator:refresh()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Clears the existing set of choices and requests new ones from enabled action handlers.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="refreshChooser">
	<h5><a href="#refreshChooser">refreshChooser</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.action.activator:refreshChooser()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Refreshes a Chooser.</p>
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
  <section id="rightClickAction">
	<h5><a href="#rightClickAction">rightClickAction</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.action.activator:rightClickAction(index) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Triggered when a user right clicks on a chooser.</p>
<p>Parameters:</p>
<ul>
<li><code>index</code>      - The row the right click occurred in or 0 if there is currently no selectable row where the right click occurred.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="rightClickMain">
	<h5><a href="#rightClickMain">rightClickMain</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.action.activator:rightClickMain(index) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Triggered when a user right clicks on a chooser.</p>
<p>Parameters:</p>
<ul>
<li><code>index</code>      - The row the right click occurred in or 0 if there is currently no selectable row where the right click occurred.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
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
		<td><code>plugins.core.action.activator:show()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Shows a chooser listing the available actions. When selected by the user,
the <a href="#onActivate">onActivate</a> function is called.</p>
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
  <section id="sortChoices">
	<h5><a href="#sortChoices">sortChoices</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.action.activator:sortChoices() -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Sorts the current set of choices in the activator. It takes into account
whether it's a favorite (first priority) and its overall popularity.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the action executed successfully, otherwise <code>false</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="unfavoriteChoice">
	<h5><a href="#unfavoriteChoice">unfavoriteChoice</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.action.activator:unfavoriteChoice(id) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Marks the choice with the specified ID as not a favorite.</p>
<p>Parameters:</p>
<ul>
<li><code>id</code>          - The choice ID to unfavorite.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successfully unfavorited.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="unhiddenChoices">
	<h5><a href="#unhiddenChoices">unhiddenChoices</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.action.activator:unhiddenChoices() -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a table with visible choices.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>Table of choices that can be displayed by an <code>hs.chooser</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="unhideChoice">
	<h5><a href="#unhideChoice">unhideChoice</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.action.activator:unhideChoice(id) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Reveals the choice with the specified ID.</p>
<p>Parameters:</p>
<ul>
<li><code>id</code>          - The choice ID to hide.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successfully unhidden otherwise <code>false</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
