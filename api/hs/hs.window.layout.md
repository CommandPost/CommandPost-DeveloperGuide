# [docs](index.md) » hs.window.layout
---

**WARNING**: EXPERIMENTAL MODULE. DO **NOT** USE IN PRODUCTION.
This module is *for testing purposes only*. It can undergo breaking API changes or *go away entirely* **at any point and without notice**.
(Should you encounter any issues, please feel free to report them on https://github.com/Hammerspoon/hammerspoon/issues
or #hammerspoon on irc.freenode.net)

Window management

Windowlayouts work by selecting certain windows via windowfilters and arranging them onscreen according to specific rules.

A **layout** is composed of a list of rules and, optionally, a screen arrangement definition.
Rules within a layout are evaluated in order; once a window is acted upon by a rule, subsequent rules will not affect it further.
A **rule** needs a **windowfilter**, producing a dynamic list of windows (the "window pool") to which the rule is applied,
and a list of commands, evaluated in order.
A **command** acts on one or more of the windows, and is composed of:
* an **action**, it can be
  - `move`: moves the window(s) to a specified onscreen rect (if the action is omitted, `move` is assumed)
  - `minimize`, `maximize`, `fullscreen`
  - `tile`, `fit`: tiles the windows onto a specified rect, using `hs.window.tiling.tileWindows()`; for `fit`, the
    `preserveRelativeArea` parameter will be set to true
  - `hide`, `unhide`: hides or unhides the window's application (like when using cmd-h)
  - `noaction`: skip action on the window(s)
* a **maxn** number, indicating how many windows from this rule's window pool will be affected (at most) by this command;
  if omitted (or if explicitly the string `all`) all the remaining windows will be processed by this command; processed
  windows are "consumed" and are excluded from the window pool for subsequent commands in this rule, and from subsequent rules
* a **selector**, describing the sort order used to pick the first *maxn* windows from the window pool for this command;
  it can be one of `focused` (pick *maxn* most recently focused windows), `frontmost` (pick the recent focused window if its  
  application is frontmost applicaion, otherwise the command will be skipped), `newest` (most recently created), `oldest`
  (least recently created), or `closest` (pick the *maxn* windows that are closest to the destination rect); if omitted,
  defaults to `closest` for move, tile and fit, and `newest` for everything else
* an `hs.geometry` *size* (only valid for tile and fit) indicating the desired optimal aspect ratio for the tiled windows;
  if omitted, defaults to 1x1 (i.e. square windows)
* for move, tile and fit, an `hs.geometry` *rect*, or a *unit rect* plus a *screen hint* (for `hs.screen.find()`),
  indicating the destination rect for the command
* for fullscreen and maximize, a *screen hint* indicating the desired screen; if omitted, uses the window's current screen

You should place higher-priority rules (with highly specialized windowfilters) first, and "fallback" rules
(with more generic windowfilters) last; similarly, *within* a rule, you should have commands for the more "important"
(i.e. relevant to your current workflow) windows first (move, maximize...) and after that deal with less prominent
windows, if any remain, e.g. by placing them out of the way (minimize).
`unhide` and `hide`, if used, should usually go into their own rules (with a windowfilter that allows invisible windows
for `unhide`) that come *before* other rules that deal with actual window placement - unlike the other actions,
they don't "consume" windows making them unavailable for subsequent rules, as they act on applications.

In order to avoid dealing with deeply nested maps, you can define a layout in your scripts via a list, where each element
(or row) denotes a rule; in turn every rule can be a simplified list of two elements:
  - a windowfilter or a constructor argument table for one (see `hs.window.filter.new()` and `hs.window.filter:setFilters()`)
  - a single string containing all the commands (action and parameters) in order; actions and selectors can be shortened to
    3 characters; all tokens must be separated by spaces (do not use spaces inside `hs.geometry` constructor strings);
    for greater clarity you can separate commands with `|` (pipe character)

Some command string examples:
- `"move 1 [0,0,50,50] -1,0"` moves the closest window to the topleft quadrant of the left screen
- `"max 0,0"` maximizes all the windows onto the primary screen, one on top of another
- `"move 1 foc [0,0,30,100] 0,0 | tile all foc [30,0,100,100] 0,0"` moves the most recently focused window to the left third,
and tiles the remaining windows onto the right side, keeping the most recently focused on top and to the left
- `"1 new [0,0,50,100] 0,0 | 1 new [50,0,100,100] 0,0 | min"` divides the primary screen between the two newest windows
and minimizes any other windows

Each layout can work in "passive" or "active" modes; passive layouts must be triggered manually (via `hs.hotkey.bind()`,
`hs.menubar`, etc.) while active layouts continuously keep their rules enforced (see `hs.window.layout:start()`
for more information); in general you should avoid having multiple active layouts targeting the same windows, as the
results will be unpredictable (if such a situation is detected, you'll see an error in the Hammerspoon console); you
*can* have multiple active layouts, but be careful to maintain a clear "separation of concerns" between their respective windowfilters.

Each layout can have an associated screen configuration; if so, the layout will only be valid while the current screen
arrangement satisfies it; see `hs.window.layout:setScreenConfiguration()` for more information.

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
<li>Variables - Configurable values</li>
  <ul>
	<li><a href="#applyDelay">applyDelay</a></li>
	<li><a href="#screensChangedDelay">screensChangedDelay</a></li>
  </ul>
<li>Functions - API calls offered directly by the extension</li>
  <ul>
	<li><a href="#applyLayout">applyLayout</a></li>
	<li><a href="#pauseAllInstances">pauseAllInstances</a></li>
	<li><a href="#resumeAllInstances">resumeAllInstances</a></li>
  </ul>
<li>Constructors - API calls which return an object, typically one that offers API methods</li>
  <ul>
	<li><a href="#new">new</a></li>
  </ul>
<li>Methods - API calls which can only be made on an object returned by a constructor</li>
  <ul>
	<li><a href="#apply">apply</a></li>
	<li><a href="#getRules">getRules</a></li>
	<li><a href="#pause">pause</a></li>
	<li><a href="#resume">resume</a></li>
	<li><a href="#setScreenConfiguration">setScreenConfiguration</a></li>
	<li><a href="#start">start</a></li>
	<li><a href="#stop">stop</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Variables</h4>
  <section id="applyDelay">
	<h5><a href="#applyDelay">applyDelay</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.window.layout.applyDelay</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>When "active mode" windowlayouts apply a rule, they will pause briefly for this amount of time in seconds, to allow windows
to "settle" in their new configuration without triggering other rules (or the same rule), which could result in a
cascade (or worse, a loop) or rules being applied. Defaults to 1; increase this if you experience unwanted repeated
triggering of rules due to sluggish performance.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="screensChangedDelay">
	<h5><a href="#screensChangedDelay">screensChangedDelay</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.window.layout.screensChangedDelay</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The number of seconds to wait, after a screen configuration change has been detected, before
resuming any active windowlayouts that are allowed in the new configuration; defaults
to 10, to give sufficient time to OSX to do its own housekeeping</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Functions</h4>
  <section id="applyLayout">
	<h5><a href="#applyLayout">applyLayout</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.window.layout.applyLayout(rules)</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Applies a layout</p>
<p>Parameters:</p>
<ul>
<li>rules - see <code>hs.window.layout.new()</code></li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
<p>Notes:</p>
<ul>
<li>this is a convenience wrapper for "passive mode" use that creates, applies, and deletes a windowlayout object;
do <em>not</em> use shared windowfilters in <code>rules</code>, as they'll be deleted; you can just use constructor argument maps instead</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="pauseAllInstances">
	<h5><a href="#pauseAllInstances">pauseAllInstances</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.window.layout.pauseAllInstances()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Pauses all active windowlayout instances</p>
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
  <section id="resumeAllInstances">
	<h5><a href="#resumeAllInstances">resumeAllInstances</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.window.layout.resumeAllInstances()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Resumes all active windowlayout instances</p>
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
<h4 class="documentation-section">Constructors</h4>
  <section id="new">
	<h5><a href="#new">new</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.window.layout.new(rules[,logname[,loglevel]]) -&gt; hs.window.layout object</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constructor</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new hs.window.layout instance</p>
<p>Parameters:</p>
<ul>
<li>rules - a table containing the rules for this windowlayout (see the module description); additionally, if a special key <code>screens</code>
is present, its value must be a valid screen configuration as per <code>hs.window.layout:setScreenConfiguration()</code></li>
<li>logname - (optional) name of the <code>hs.logger</code> instance for the new windowlayout; if omitted, the class logger will be used</li>
<li>loglevel - (optional) log level for the <code>hs.logger</code> instance for the new windowlayout</li>
</ul>
<p>Returns:</p>
<ul>
<li>a new windowlayout instance</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Methods</h4>
  <section id="apply">
	<h5><a href="#apply">apply</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.window.layout:apply()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Applies the layout</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>the <code>hs.window.layout</code> object</li>
</ul>
<p>Notes:</p>
<ul>
<li>if a screen configuration is defined for this windowfilter, and currently not satisfied, this method will do nothing</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getRules">
	<h5><a href="#getRules">getRules</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.window.layout:getRules() -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Return a table with all the rules (and the screen configuration, if present) defined for this windowlayout</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>a table containing the rules of this windowlayout; you can pass this table (optionally
after performing valid manipulations) to <code>hs.window.layout.new()</code></li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="pause">
	<h5><a href="#pause">pause</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.window.layout:pause() -&gt; hs.window.layout object</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Pauses an active windowlayout instance; while paused no automatic window management will occur</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>the <code>hs.window.layout</code> object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="resume">
	<h5><a href="#resume">resume</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.window.layout:resume() -&gt; hs.window.layout object</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Resumes an active windowlayout instance after it was paused</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>the <code>hs.window.layout</code> object</li>
</ul>
<p>Notes:</p>
<ul>
<li>if a screen configuration is defined for this windowfilter, and currently not satisfied, this method will do nothing</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="setScreenConfiguration">
	<h5><a href="#setScreenConfiguration">setScreenConfiguration</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.window.layout:setScreenConfiguration(screens) -&gt; hs.window.layout object</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Determines the screen configuration that permits applying this windowlayout</p>
<p>With this method you can define different windowlayouts for different screen configurations
(as per System Preferences-&gt;Displays-&gt;Arrangement).
For example, suppose you define two "graphics design work" windowlayouts, one for "desk with dual monitors"
and one for "laptop only mode":</p>
<ul>
<li>"passive mode" use: you call <code>:apply()</code> on <em>both</em> on your chosen hotkey (via <code>hs.hotkey:bind()</code>), but
only the appropriate layout for the current arrangement will be applied</li>
<li>"active mode" use: you just call <code>:start()</code> on both windowlayouts; as you switch between workplaces
(by attaching or detaching external screens) the correct layout "kicks in"
automatically - this is in effect a convenience wrapper that calls <code>:pause()</code> on the no longer relevant
layout, and <code>:resume()</code> on the appropriate one, at every screen configuration change</li>
</ul>
<p>Parameters:</p>
<ul>
<li>screens - a map, where each <em>key</em> must be a valid "hint" for <code>hs.screen.find()</code>, and the corresponding
value can be:<ul>
<li><code>true</code> - the screen must be currently present (attached and enabled)</li>
<li><code>false</code> - the screen must be currently absent</li>
<li>an <code>hs.geometry</code> point (or constructor argument) - the screen must be present and in this specific
position in the current arragement (as per <code>hs.screen:position()</code>)</li>
</ul>
</li>
</ul>
<p>Returns:</p>
<ul>
<li>the <code>hs.window.layout</code> object</li>
</ul>
<p>Notes:</p>
<ul>
<li>if <code>screens</code> is <code>nil</code>, any previous screen configuration is removed, and this windowlayout will be always allowed</li>
<li>for "active" windowlayouts, call this method <em>before</em> calling <code>hs.window.layout:start()</code></li>
<li>by using <code>hs.geometry</code> size objects as hints you can define separate layouts for the same physical
screen at different resolutions</li>
</ul>
<p>Usage:</p>

<pre><code>local laptop_layout,desk_layout=... -- define your layouts
-- just the laptop screen:
laptop_layout:setScreenConfiguration{['Color LCD']='0,0',dell=false,['3840x2160']=false}:start()
-- attached to a 4k primary + a Dell on the right:
desk_layout:setScreenConfiguration{['3840x2160']='0,0',['dell']='1,0',['Color LCD']='-1,0'}:start()
-- as above, but in clamshell mode (laptop lid closed):
clamshell_layout:setScreenConfiguration{['3840x2160']='0,0',['dell']='1,0',['Color LCD']=false}:start()</code></pre>
</td>
	  </tr>
	</table>
  </section>
  <section id="start">
	<h5><a href="#start">start</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.window.layout:start() -&gt; hs.window.layout object</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Puts a windowlayout instance in "active mode"</p>
<p>When in active mode, a windowlayout instance will constantly monitor the windowfilters for its rules,
by subscribing to all the relevant events. As soon as any change is detected (e.g. when you drag a window,
switch focus, open or close apps/windows, etc.) the relative rule will be automatically re-applied.
In other words, the rules you defined will remain enforced all the time, instead of waiting for manual
intervention via <code>hs.window.layout:apply()</code>.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>the <code>hs.window.layout</code> object</li>
</ul>
<p>Notes:</p>
<ul>
<li>if a screen configuration is defined for this windowfilter, and currently not satisfied, this
windowfilter will be put in "active mode" but will remain paused until the screen configuration
requirements are met</li>
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
		<td><code>hs.window.layout:stop() -&gt; hs.window.layout object</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Stops a windowlayout instance (i.e. not in "active mode" anymore)</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>the <code>hs.window.layout</code> object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
