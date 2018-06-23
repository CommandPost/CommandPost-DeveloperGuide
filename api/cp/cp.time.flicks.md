# [docs](index.md) » cp.time.flicks
---

Provides support for measuring time in `flicks`, a base unit of time useful for
working with media, such as video or audio files.

From the [Flicks GitHub project]():


A flick (frame-tick) is a very small unit of time. It is 1/705600000 of a second, exactly.

`1 flick = 1/705600000 second`

This unit of time is the smallest time unit which is LARGER than a nanosecond, and can in integer quantities exactly
represent a single frame duration for 24 Hz, 25 Hz, 30 Hz, 48 Hz, 50 Hz, 60 Hz, 90 Hz, 100 Hz, 120 Hz, and
also 1/1000 divisions of each, as well as a single sample duration for 8 kHz, 16 kHz, 22.05 kHz, 24 kHz, 32 kHz,
44.1 kHz, 48 kHz, 88.2 kHz, 96 kHz, and 192kHz, as well as the NTSC frame durations for 24 * (1000/1001) Hz,
30 * (1000/1001) Hz, 60 * (1000/1001) Hz, and 120 * (1000/1001) Hz.

That above was one hell of a run-on sentence, but it's strictly and completely correct in its description of
the unit.

This makes flicks suitable for use via std::chrono::duration and std::ratio for doing timing work against the
system high resolution clock, which is in nanoseconds, but doesn't get slightly out of sync when doing
common frame rates.

We also support some common audio sample rates as well. This list is not exhaustive, but covers the majority
of digital audio formats. They are 8kHz, 16kHz, 22.05kHz, 24kHz, 32kHz, 44.1kHz, 48kHz, 88.2kHz, 96kHz, and 192kHz.

Though it is not part of the design criteria, 144 Hz, which some newer monitors refresh at, does work
correctly with flicks.

NTSC IS NOT EXPLICITLY SUPPORTED IN ALL OF ITS SUBTLE NUANCES, BUT: The NTSC variations (~23.976, ~29.97, etc)
are approximately defined as 24 * 1000/1001 and 30 * 1000/1001, etc. These can be represented exactly in flicks,
but 1/1000 divisions are not available.

Many folks online have pointed out that NTSC technically has a variable frame rate, and that this is handled
correctly in other media playback libraries such as QuickTime. The goal of flicks is to provide a simple,
convenient std::chrono::duration to work with when writing code that works with simulation and time in media,
but not explicitly to handle complex variable-rate playback scenarios. So we'll stick with the 1000/1001
approximations, and leave it at that!

# Details

* 24 fps frame: 29400000 flicks
* 25 fps frame: 28224000 flicks
* 30 fps frame: 23520000 flicks
* 48 fps frame: 14700000 flicks
* 50 fps frame: 14112000 flicks
* 60 fps frame: 11760000 flicks
* 90 fps frame: 7840000 flicks
* 100 fps frame: 7056000 flicks
* 120 fps frame: 5880000 flicks
* 8000 fps frame: 88200 flicks
* 16000 fps frame: 44100 flicks
* 22050 fps frame: 32000 flicks
* 24000 fps frame: 29400 flicks
* 32000 fps frame: 22050 flicks
* 44100 fps frame: 16000 flicks
* 48000 fps frame: 14700 flicks
* 88200 fps frame: 8000 flicks
* 96000 fps frame: 7350 flicks
* 192000 fps frame: 3675 flicks

# NTSC:

* 24 * 1000/1001 (~23.976) fps frame: 29429400 flicks
* 30 * 1000/1001 (~29.97) fps frame: 23543520 flicks
* 60 * 1000/1001 (~59.94) fps frame: 11771760 flicks
* 120 * 1000/1001 (~119.88) fps frame: 5885880 flicks

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
	<li><a href="#perFrame100">perFrame100</a></li>
	<li><a href="#perFrame120">perFrame120</a></li>
	<li><a href="#perFrame120NTSC">perFrame120NTSC</a></li>
	<li><a href="#perFrame24">perFrame24</a></li>
	<li><a href="#perFrame24NTSC">perFrame24NTSC</a></li>
	<li><a href="#perFrame25">perFrame25</a></li>
	<li><a href="#perFrame30">perFrame30</a></li>
	<li><a href="#perFrame30NTSC">perFrame30NTSC</a></li>
	<li><a href="#perFrame44100">perFrame44100</a></li>
	<li><a href="#perFrame48">perFrame48</a></li>
	<li><a href="#perFrame48000">perFrame48000</a></li>
	<li><a href="#perFrame50">perFrame50</a></li>
	<li><a href="#perFrame60">perFrame60</a></li>
	<li><a href="#perFrame60NTSC">perFrame60NTSC</a></li>
	<li><a href="#perFrame90">perFrame90</a></li>
	<li><a href="#perHour">perHour</a></li>
	<li><a href="#perMinutes">perMinutes</a></li>
	<li><a href="#perSecond">perSecond</a></li>
  </ul>
<li>Functions - API calls offered directly by the extension</li>
  <ul>
	<li><a href="#is">is</a></li>
  </ul>
<li>Constructors - API calls which return an object, typically one that offers API methods</li>
  <ul>
	<li><a href="#new">new</a></li>
	<li><a href="#parse">parse</a></li>
  </ul>
<li>Methods - API calls which can only be made on an object returned by a constructor</li>
  <ul>
	<li><a href="#toFrames">toFrames</a></li>
	<li><a href="#toSeconds">toSeconds</a></li>
	<li><a href="#toTimecode">toTimecode</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Constants</h4>
  <section id="perFrame100">
	<h5><a href="#perFrame100">perFrame100</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.time.flicks.perFrame100</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The number of flicks in 1 frame at 100 fps.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="perFrame120">
	<h5><a href="#perFrame120">perFrame120</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.time.flicks.perFrame120</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The number of flicks in 1 frame at 120 fps.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="perFrame120NTSC">
	<h5><a href="#perFrame120NTSC">perFrame120NTSC</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.time.flicks.perFrame120NTSC</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>An approximate for flicks in 1 frame at 120 fps in NTSC, a.k.a. ~119.88 fps.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="perFrame24">
	<h5><a href="#perFrame24">perFrame24</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.time.flicks.perFrame24</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The number of flicks in 1 frame at 24 fps.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="perFrame24NTSC">
	<h5><a href="#perFrame24NTSC">perFrame24NTSC</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.time.flicks.perFrame24NTSC</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>An approximate for flicks in 1 frame at 24 fps in NTSC, a.k.a. 23.976 fps.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="perFrame25">
	<h5><a href="#perFrame25">perFrame25</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.time.flicks.perFrame25</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The number of flicks in 1 frame at 25 fps.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="perFrame30">
	<h5><a href="#perFrame30">perFrame30</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.time.flicks.perFrame30</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The number of flicks in 1 frame at 30 fps.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="perFrame30NTSC">
	<h5><a href="#perFrame30NTSC">perFrame30NTSC</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.time.flicks.perFrame30NTSC</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>An approximate for flicks in 1 frame at 30 fps in NTSC, a.k.a. 29.97 fps.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="perFrame44100">
	<h5><a href="#perFrame44100">perFrame44100</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.time.flicks.perFrame44100</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The number of flicks in 1 frame at 44100 fps, a.k.a. 44.1 Hz.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="perFrame48">
	<h5><a href="#perFrame48">perFrame48</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.time.flicks.perFrame48</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The number of flicks in 1 frame at 48 fps.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="perFrame48000">
	<h5><a href="#perFrame48000">perFrame48000</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.time.flicks.perFrame48000</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The number of flicks in 1 frame at 44100 fps, a.k.a. 48 Hz.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="perFrame50">
	<h5><a href="#perFrame50">perFrame50</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.time.flicks.perFrame50</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The number of flicks in 1 frame at 50 fps.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="perFrame60">
	<h5><a href="#perFrame60">perFrame60</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.time.flicks.perFrame60</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The number of flicks in 1 frame at 60 fps.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="perFrame60NTSC">
	<h5><a href="#perFrame60NTSC">perFrame60NTSC</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.time.flicks.perFrame60NTSC</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>An approximate for flicks in 1 frame at 60 fps in NTSC, a.k.a. 59.94 fps.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="perFrame90">
	<h5><a href="#perFrame90">perFrame90</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.time.flicks.perFrame90</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The number of flicks in 1 frame at 90 fps.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="perHour">
	<h5><a href="#perHour">perHour</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.time.flicks.perHour</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The number of flicks in 1 hour.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="perMinutes">
	<h5><a href="#perMinutes">perMinutes</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.time.flicks.perMinutes</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The number of flicks in 1 minute.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="perSecond">
	<h5><a href="#perSecond">perSecond</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.time.flicks.perSecond</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The number of flicks in 1 second.</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Functions</h4>
  <section id="is">
	<h5><a href="#is">is</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.time.flicks.is(thing) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Checks if the <code>thing</code> is a <code>flicks</code> instance.</p>
<p>Parameters:</p>
<ul>
<li>thing - the thing to check</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the thingis a flicks instance, otherwise <code>false</code>.</li>
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
		<td><code>cp.time.flicks.new(value) -&gt; flicks</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constructor</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new <code>flicks</code> instance. By default, the unit is in flicks<code>, but can be set as a
different unit using the</code>flicks.perXXX` constants. For example:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">oneFlick</span> <span class="o">=</span> <span class="n">flicks</span><span class="p">.</span><span class="n">new</span><span class="p">(</span><span class="mi">1</span><span class="p">)</span>
<span class="kd">local</span> <span class="n">oneSecond</span> <span class="o">=</span> <span class="n">flicks</span><span class="p">.</span><span class="n">new</span><span class="p">(</span><span class="mi">1</span> <span class="o">*</span> <span class="n">flicks</span><span class="p">.</span><span class="n">perSecond</span><span class="p">)</span>
</pre></div>
<p>Parameters:</p>
<ul>
<li>value - the base value to set to</li>
</ul>
<p>Returns:</p>
<ul>
<li>the new <code>flicks</code> instance</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="parse">
	<h5><a href="#parse">parse</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.time.flicks.parse(timecodeString, framerate) -&gt; flicks</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constructor</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Attempts to parse the timecode string value with the specified framerate.
The timecode can match the folowing patterns:</p>
<ul>
<li><code>"HH:MM:SS:FF"</code></li>
<li><code>"HH:MM:SS;FF"</code></li>
<li><code>"HHMMSSFF"</code></li>
</ul>
<p>The characters above match to <code>H</code>ours, <code>M</code>inutes <code>S</code>econds and <code>F</code>rames, respectively. For example,
a timecode of 1 hour, 23 minutes, 45 seconds and 12 frames could be expressed as:</p>
<ul>
<li><code>"01:23:45:12"</code></li>
<li><code>"01:23:45;12"</code></li>
<li><code>"01234512"</code></li>
</ul>
<p>Times with a value of zero from left to right may be omitted. After the first non-zero value, all
other numbers including framesmust always be expressed, even if they are zero.
So, if your timecode is 1 minute 30 seconds, you could use:</p>
<ul>
<li><code>"1:30:00"</code></li>
<li><code>"1:30;00"</code></li>
<li><code>"13000"</code></li>
</ul>
<p>You can also put numbers up to <code>99</code> in each block. So, another way of expressing 1 minute 30 seconds is:</p>
<ul>
<li><code>"90:00"</code></li>
<li><code>"90;00"</code></li>
<li><code>"9000"</code></li>
</ul>
<p>Parameters:</p>
<ul>
<li>timecodeString   - The timecode as a string.</li>
<li>framerate        - The number of frames per second.</li>
</ul>
<p>Returns:</p>
<ul>
<li>a new <code>flicks</code> instance for the timecode.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Methods</h4>
  <section id="toFrames">
	<h5><a href="#toFrames">toFrames</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.time.flicks:toFrames(framerate) --&gt; number</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Converts the flicks into a number for the specific framerate.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="toSeconds">
	<h5><a href="#toSeconds">toSeconds</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.time.flicks:toSeconds() -&gt; number</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Converts the flicks into a decimal value of the number of seconds it represents.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>the number of seconds</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="toTimecode">
	<h5><a href="#toTimecode">toTimecode</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.time.flicks:toTimecode(framerate[, delimeter]) -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Converts the flicks into a string of the format "HH[:]MM[:]SS[:;]FF", with hours, minutes and frames listed respectively.
By default, there will be no delimiter. If you provide ":" then all delimiters will be colons. If you provide
";" then the final delimiter will be a semic-colon, all others will be colons.</p>
<p>Parameters:</p>
<ul>
<li>framerate    - the framerate to use when calculating frames per second.</li>
<li>delimeter    - either <code>nil</code> (default), ":", or ";".</li>
</ul>
<p>Returns:</p>
<ul>
<li>String of the timecode.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
