# [docs](index.md) » hs.vox
---

Controls for VOX music player

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
	<li><a href="#addurl">addurl</a></li>
	<li><a href="#backward">backward</a></li>
	<li><a href="#decreaseVolume">decreaseVolume</a></li>
	<li><a href="#fastBackward">fastBackward</a></li>
	<li><a href="#fastForward">fastForward</a></li>
	<li><a href="#forward">forward</a></li>
	<li><a href="#getAlbumArtist">getAlbumArtist</a></li>
	<li><a href="#getCurrentAlbum">getCurrentAlbum</a></li>
	<li><a href="#getCurrentArtist">getCurrentArtist</a></li>
	<li><a href="#getPlayerState">getPlayerState</a></li>
	<li><a href="#getUniqueID">getUniqueID</a></li>
	<li><a href="#increaseVolume">increaseVolume</a></li>
	<li><a href="#isRunning">isRunning</a></li>
	<li><a href="#next">next</a></li>
	<li><a href="#pause">pause</a></li>
	<li><a href="#play">play</a></li>
	<li><a href="#playpause">playpause</a></li>
	<li><a href="#playurl">playurl</a></li>
	<li><a href="#previous">previous</a></li>
	<li><a href="#shuffle">shuffle</a></li>
	<li><a href="#togglePlaylist">togglePlaylist</a></li>
	<li><a href="#trackInfo">trackInfo</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="addurl">
	<h5><a href="#addurl">addurl</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.vox.addurl(url)</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Add media URL to current list</p>
<p>Parameters:</p>
<ul>
<li>url {string}</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="backward">
	<h5><a href="#backward">backward</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.vox.backward()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Skips the playback position backwards by about 7 seconds</p>
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
  <section id="decreaseVolume">
	<h5><a href="#decreaseVolume">decreaseVolume</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.vox.decreaseVolume()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Decreases the player volume</p>
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
  <section id="fastBackward">
	<h5><a href="#fastBackward">fastBackward</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.vox.fastBackward()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Skips the playback position backwards by about 14 seconds</p>
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
  <section id="fastForward">
	<h5><a href="#fastForward">fastForward</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.vox.fastForward()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Skips the playback position forwards by about 17 seconds</p>
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
  <section id="forward">
	<h5><a href="#forward">forward</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.vox.forward()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Skips the playback position forwards by about 7 seconds</p>
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
  <section id="getAlbumArtist">
	<h5><a href="#getAlbumArtist">getAlbumArtist</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.vox.getAlbumArtist()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets the artist of current Album</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A string containing the artist of current Album, or nil if an error occurred</li>
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
		<td><code>hs.vox.getCurrentAlbum()</code></td>
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
		<td><code>hs.vox.getCurrentArtist()</code></td>
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
  <section id="getPlayerState">
	<h5><a href="#getPlayerState">getPlayerState</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.vox.getPlayerState()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets the current playback state of vox</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>0 for paused</li>
<li>1 for playing</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getUniqueID">
	<h5><a href="#getUniqueID">getUniqueID</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.vox.getUniqueID()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets the uniqueID of the current track</p>
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
  <section id="increaseVolume">
	<h5><a href="#increaseVolume">increaseVolume</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.vox.increaseVolume()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Increases the palyer volume</p>
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
  <section id="isRunning">
	<h5><a href="#isRunning">isRunning</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.vox.isRunning()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns whether VOX is currently open</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A boolean value indicating whether the vox application is running</li>
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
		<td><code>hs.vox.next()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Skips to the next track</p>
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
		<td><code>hs.vox.pause()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Pauses the current vox track</p>
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
		<td><code>hs.vox.play()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Plays the current vox track</p>
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
		<td><code>hs.vox.playpause()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Toggles play/pause of current vox track</p>
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
  <section id="playurl">
	<h5><a href="#playurl">playurl</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.vox.playurl(url)</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Play media from the given URL</p>
<p>Parameters:</p>
<ul>
<li>url {string}</li>
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
		<td><code>hs.vox.previous()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Skips to previous track</p>
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
  <section id="shuffle">
	<h5><a href="#shuffle">shuffle</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.vox.shuffle()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Toggle shuffle state of current list</p>
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
  <section id="togglePlaylist">
	<h5><a href="#togglePlaylist">togglePlaylist</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.vox.togglePlaylist()</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Toggle playlist</p>
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
  <section id="trackInfo">
	<h5><a href="#trackInfo">trackInfo</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.vox.trackInfo()</code></td>
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
