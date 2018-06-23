# [docs](index.md) » hs.deezer
---


Controls for Deezer music player

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
	<li><a href="#state_paused">state_paused</a></li>
	<li><a href="#state_playing">state_playing</a></li>
	<li><a href="#state_stopped">state_stopped</a></li>
  </ul>
<li>Functions - API calls offered directly by the extension</li>
  <ul>
	<li><a href="#displayCurrentTrack">displayCurrentTrack</a></li>
	<li><a href="#ff">ff</a></li>
	<li><a href="#getCurrentAlbum">getCurrentAlbum</a></li>
	<li><a href="#getCurrentArtist">getCurrentArtist</a></li>
	<li><a href="#getCurrentTrack">getCurrentTrack</a></li>
	<li><a href="#getPlaybackState">getPlaybackState</a></li>
	<li><a href="#getPosition">getPosition</a></li>
	<li><a href="#getVolume">getVolume</a></li>
	<li><a href="#isPlaying">isPlaying</a></li>
	<li><a href="#isRunning">isRunning</a></li>
	<li><a href="#next">next</a></li>
	<li><a href="#pause">pause</a></li>
	<li><a href="#play">play</a></li>
	<li><a href="#playpause">playpause</a></li>
	<li><a href="#previous">previous</a></li>
	<li><a href="#rw">rw</a></li>
	<li><a href="#setPosition">setPosition</a></li>
	<li><a href="#setVolume">setVolume</a></li>
	<li><a href="#volumeDown">volumeDown</a></li>
	<li><a href="#volumeUp">volumeUp</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Constants</h4>
  <section id="state_paused">
	<h5><a href="#state_paused">state_paused</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.deezer.state_paused</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returned by <code>hs.deezer.getPlaybackState()</code> to indicates deezer is paused</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="state_playing">
	<h5><a href="#state_playing">state_playing</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.deezer.state_playing</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returned by <code>hs.deezer.getPlaybackState()</code> to indicates deezer is playing</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="state_stopped">
	<h5><a href="#state_stopped">state_stopped</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.deezer.state_stopped</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returned by <code>hs.deezer.getPlaybackState()</code> to indicates deezer is stopped</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Functions</h4>
  <section id="displayCurrentTrack">
	<h5><a href="#displayCurrentTrack">displayCurrentTrack</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.deezer.displayCurrentTrack()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Displays information for current track on screen</p>
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
  <section id="ff">
	<h5><a href="#ff">ff</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.deezer.ff()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Skips the playback position forwards by 5 seconds</p>
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
  <section id="getCurrentAlbum">
	<h5><a href="#getCurrentAlbum">getCurrentAlbum</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.deezer.getCurrentAlbum()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets the name of the album of the current track</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A string containing the Album of the current track, or nil if an error occurred</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getCurrentArtist">
	<h5><a href="#getCurrentArtist">getCurrentArtist</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.deezer.getCurrentArtist()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets the name of the artist of the current track</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A string containing the Artist of the current track, or nil if an error occurred</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getCurrentTrack">
	<h5><a href="#getCurrentTrack">getCurrentTrack</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.deezer.getCurrentTrack()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets the name of the current track</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A string containing the name of the current track, or nil if an error occurred</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getPlaybackState">
	<h5><a href="#getPlaybackState">getPlaybackState</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.deezer.getPlaybackState()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets the current playback state of deezer</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A string containing one of the following constants:<ul>
<li><code>hs.deezer.state_stopped</code></li>
<li><code>hs.deezer.state_paused</code></li>
<li><code>hs.deezer.state_playing</code></li>
</ul>
</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getPosition">
	<h5><a href="#getPosition">getPosition</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.deezer.getPosition()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets the playback position (in seconds) in the current song</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A number indicating the current position in the song</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getVolume">
	<h5><a href="#getVolume">getVolume</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.deezer.getVolume()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets the deezer volume setting</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A number containing the volume deezer is set to between 1 and 100</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="isPlaying">
	<h5><a href="#isPlaying">isPlaying</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.deezer.isPlaying()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns whether deezer is currently playing</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A boolean value indicating whether deezer is currently playing a track, or nil if an error occurred (unknown player state). Also returns false if the application is not running</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="isRunning">
	<h5><a href="#isRunning">isRunning</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.deezer.isRunning()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns whether deezer is currently open. Most other functions in hs.deezer will automatically start the application, so this function can be used to guard against that.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A boolean value indicating whether the deezer application is running.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="next">
	<h5><a href="#next">next</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.deezer.next()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Skips to the next deezer track</p>
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
  <section id="pause">
	<h5><a href="#pause">pause</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.deezer.pause()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Pauses the current deezer track</p>
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
  <section id="play">
	<h5><a href="#play">play</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.deezer.play()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Plays the current deezer track</p>
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
  <section id="playpause">
	<h5><a href="#playpause">playpause</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.deezer.playpause()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Toggles play/pause of current deezer track</p>
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
  <section id="previous">
	<h5><a href="#previous">previous</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.deezer.previous()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Skips to previous deezer track</p>
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
  <section id="rw">
	<h5><a href="#rw">rw</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.deezer.rw</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Skips the playback position backwards by 5 seconds</p>
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
  <section id="setPosition">
	<h5><a href="#setPosition">setPosition</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.deezer.setPosition(pos)</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Sets the playback position in the current song</p>
<p>Parameters:</p>
<ul>
<li>pos - A number containing the position (in seconds) to jump to in the current song</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="setVolume">
	<h5><a href="#setVolume">setVolume</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.deezer.setVolume(vol)</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Sets the deezer volume setting</p>
<p>Parameters:</p>
<ul>
<li>vol - A number between 1 and 100</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="volumeDown">
	<h5><a href="#volumeDown">volumeDown</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.deezer.volumeDown()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Reduces the volume by 5</p>
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
  <section id="volumeUp">
	<h5><a href="#volumeUp">volumeUp</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.deezer.volumeUp()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Increases the volume by 5</p>
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
