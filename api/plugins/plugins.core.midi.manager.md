# [docs](index.md) » plugins.core.midi.manager
---

MIDI Manager Plugin.

<style type="text/css">
	a { text-decoration: none; }
	a:hover { text-decoration: underline; }
	th { background-color: #DDDDDD; vertical-align: top; padding: 3px; }
	td { width: 100%; background-color: #EEEEEE; vertical-align: top; padding: 3px; }
	table { width: 100% ; border: 1px solid #0; text-align: left; }
	section > table table td { width: 0; }
</style>
<link rel="stylesheet" href="../../css/docs.css" type="text/css" media="screen" />
<h3>Submodules</h3>
<ul>
<li><a href="plugins.core.midi.manager.controls.md">plugins.core.midi.manager.controls</a></li>
</ul>
<h3>API Overview</h3>
<ul>
<li>Constants - Useful values which cannot be changed</li>
  <ul>
	<li><a href="#DEFAULT_GROUP">DEFAULT_GROUP</a></li>
	<li><a href="#DEFAULT_MIDI_CONTROLS">DEFAULT_MIDI_CONTROLS</a></li>
	<li><a href="#FILE_NAME">FILE_NAME</a></li>
	<li><a href="#FOLDER_NAME">FOLDER_NAME</a></li>
	<li><a href="#MMC_COMMAND_TYPE">MMC_COMMAND_TYPE</a></li>
	<li><a href="#MMC_TIMECODE_TYPE">MMC_TIMECODE_TYPE</a></li>
	<li><a href="#MTC_COMMAND_TYPE">MTC_COMMAND_TYPE</a></li>
	<li><a href="#MTC_MESSAGE_TYPE">MTC_MESSAGE_TYPE</a></li>
	<li><a href="#MTC_TIMECODE_TYPE">MTC_TIMECODE_TYPE</a></li>
  </ul>
<li>Variables - Configurable values</li>
  <ul>
	<li><a href="#learningMode">learningMode</a></li>
	<li><a href="#maxItems">maxItems</a></li>
	<li><a href="#numberOfSubGroups">numberOfSubGroups</a></li>
  </ul>
<li>Functions - API calls offered directly by the extension</li>
  <ul>
	<li><a href="#activeGroup">activeGroup</a></li>
	<li><a href="#activeSubGroup">activeSubGroup</a></li>
	<li><a href="#clear">clear</a></li>
	<li><a href="#devices">devices</a></li>
	<li><a href="#forcefullyWatchMIDIDevices">forcefullyWatchMIDIDevices</a></li>
	<li><a href="#forceGroupChange">forceGroupChange</a></li>
	<li><a href="#getDevice">getDevice</a></li>
	<li><a href="#getItem">getItem</a></li>
	<li><a href="#getItems">getItems</a></li>
	<li><a href="#gotoSubGroup">gotoSubGroup</a></li>
	<li><a href="#groupStatus">groupStatus</a></li>
	<li><a href="#init">init</a></li>
	<li><a href="#midiCallback">midiCallback</a></li>
	<li><a href="#nextSubGroup">nextSubGroup</a></li>
	<li><a href="#previousSubGroup">previousSubGroup</a></li>
	<li><a href="#processMMC">processMMC</a></li>
	<li><a href="#processMTC">processMTC</a></li>
	<li><a href="#registerCallback">registerCallback</a></li>
	<li><a href="#registerListenMMCFunction">registerListenMMCFunction</a></li>
	<li><a href="#registerListenMTCFunction">registerListenMTCFunction</a></li>
	<li><a href="#sendMMC">sendMMC</a></li>
	<li><a href="#setItem">setItem</a></li>
	<li><a href="#start">start</a></li>
	<li><a href="#update">update</a></li>
	<li><a href="#updateAction">updateAction</a></li>
	<li><a href="#virtualDevices">virtualDevices</a></li>
  </ul>
<li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
  <ul>
	<li><a href="#buttons">buttons</a></li>
	<li><a href="#enabled">enabled</a></li>
	<li><a href="#listenMMC">listenMMC</a></li>
	<li><a href="#listenMMCDevice">listenMMCDevice</a></li>
	<li><a href="#listenMTC">listenMTC</a></li>
	<li><a href="#listenMTCDevice">listenMTCDevice</a></li>
	<li><a href="#transmitMMC">transmitMMC</a></li>
	<li><a href="#transmitMMCDevice">transmitMMCDevice</a></li>
	<li><a href="#transmitMTC">transmitMTC</a></li>
	<li><a href="#transmitMTCDevice">transmitMTCDevice</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Constants</h4>
  <section id="DEFAULT_GROUP">
	<h5><a href="#DEFAULT_GROUP">DEFAULT_GROUP</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.DEFAULT_GROUP -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The default group.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="DEFAULT_MIDI_CONTROLS">
	<h5><a href="#DEFAULT_MIDI_CONTROLS">DEFAULT_MIDI_CONTROLS</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.DEFAULT_MIDI_CONTROLS -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The default MIDI controls, so that the user has a starting point.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="FILE_NAME">
	<h5><a href="#FILE_NAME">FILE_NAME</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.FILE_NAME -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>File name of settings file.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="FOLDER_NAME">
	<h5><a href="#FOLDER_NAME">FOLDER_NAME</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.FOLDER_NAME -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Folder Name where settings file is contained.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="MMC_COMMAND_TYPE">
	<h5><a href="#MMC_COMMAND_TYPE">MMC_COMMAND_TYPE</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.MMC_COMMAND_TYPE -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>MMC Command Types</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="MMC_TIMECODE_TYPE">
	<h5><a href="#MMC_TIMECODE_TYPE">MMC_TIMECODE_TYPE</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.MMC_TIMECODE_TYPE -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>MMC Timecode Type</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="MTC_COMMAND_TYPE">
	<h5><a href="#MTC_COMMAND_TYPE">MTC_COMMAND_TYPE</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.MTC_COMMAND_TYPE -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>MTC Command Type</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="MTC_MESSAGE_TYPE">
	<h5><a href="#MTC_MESSAGE_TYPE">MTC_MESSAGE_TYPE</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.MTC_MESSAGE_TYPE -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>MTC Message Types</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="MTC_TIMECODE_TYPE">
	<h5><a href="#MTC_TIMECODE_TYPE">MTC_TIMECODE_TYPE</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.MTC_TIMECODE_TYPE -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constant</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>MTC Timecode Type</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Variables</h4>
  <section id="learningMode">
	<h5><a href="#learningMode">learningMode</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.learningMode -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Whether or not the MIDI Manager is in learning mode.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="maxItems">
	<h5><a href="#maxItems">maxItems</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.maxItems -&gt; number</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The maximum number of MIDI items per group.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="numberOfSubGroups">
	<h5><a href="#numberOfSubGroups">numberOfSubGroups</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.numberOfSubGroups -&gt; number</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Variable</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The number of Sub Groups per Touch Bar Group.</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Functions</h4>
  <section id="activeGroup">
	<h5><a href="#activeGroup">activeGroup</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.activeGroup() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the active group.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>Returns the active group or <code>manager.defaultGroup</code> as a string.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="activeSubGroup">
	<h5><a href="#activeSubGroup">activeSubGroup</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.activeSubGroup() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the active sub-group.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>Returns the active sub group as string</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="clear">
	<h5><a href="#clear">clear</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.clear() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Clears the MIDI items.</p>
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
  <section id="devices">
	<h5><a href="#devices">devices</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.devices() -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets a table of Physical MIDI Device Names.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table of Physical MIDI Device Names.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="forcefullyWatchMIDIDevices">
	<h5><a href="#forcefullyWatchMIDIDevices">forcefullyWatchMIDIDevices</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.forcefullyWatchMIDIDevices(devices) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Forces CommandPost to watch a table of MIDI devices.</p>
<p>Parameters:</p>
<ul>
<li>devices - A table containing all the device names you want to always watch.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table of Virtual MIDI Source Names.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="forceGroupChange">
	<h5><a href="#forceGroupChange">forceGroupChange</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.forceGroupChange(combinedGroupAndSubGroupID) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Loads a specific sub-group.</p>
<p>Parameters:</p>
<ul>
<li>combinedGroupAndSubGroupID - The group and subgroup as a single string.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getDevice">
	<h5><a href="#getDevice">getDevice</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.getDevice(deviceName, virtual) -&gt; hs.midi object | nil</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets a MIDI Device.</p>
<p>Parameters:</p>
<ul>
<li>deviceName - The device name.</li>
<li>virtual - A boolean that defines whether or not the device is virtual.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A <code>hs.midi</code> object or nil if no MIDI device by that name exists.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getItem">
	<h5><a href="#getItem">getItem</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.getItem(item, button, group) -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets a MIDI item from Preferences.</p>
<p>Parameters:</p>
<ul>
<li>item - The item you want to get.</li>
<li>button - Button ID as string</li>
<li>group - Group ID as string</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table otherwise <code>nil</code></li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="getItems">
	<h5><a href="#getItems">getItems</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.getItems() -&gt; tables</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets all the MIDI items in a table.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="gotoSubGroup">
	<h5><a href="#gotoSubGroup">gotoSubGroup</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.gotoSubGroup() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Loads a specific sub-group.</p>
<p>Parameters:</p>
<ul>
<li>id - The ID of the sub-group.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="groupStatus">
	<h5><a href="#groupStatus">groupStatus</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.groupStatus(groupID, status) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Updates a group's visibility status.</p>
<p>Parameters:</p>
<ul>
<li>groupID - the group you want to update as a string.</li>
<li>status - the status of the group as a boolean.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="init">
	<h5><a href="#init">init</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.init(deps, env) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Initialises the MIDI Plugin</p>
<p>Parameters:</p>
<ul>
<li>deps - Dependencies Table</li>
<li>env - Environment Table</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="midiCallback">
	<h5><a href="#midiCallback">midiCallback</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.midiCallback(object, deviceName, commandType, description, metadata) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>MIDI Callback</p>
<p>Parameters:</p>
<ul>
<li>object - The <code>hs.midi</code> userdata object</li>
<li>deviceName - Device name as string</li>
<li>commandType - Command Type as string</li>
<li>description - Description as string</li>
<li>metadata - A table containing metadata for the MIDI command</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="nextSubGroup">
	<h5><a href="#nextSubGroup">nextSubGroup</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.nextSubGroup() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Goes to the next sub-group for the active group.</p>
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
  <section id="previousSubGroup">
	<h5><a href="#previousSubGroup">previousSubGroup</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.previousSubGroup() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Goes to the previous sub-group for the active group.</p>
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
  <section id="processMMC">
	<h5><a href="#processMMC">processMMC</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.processMMC(sysexData) -&gt; string, ...</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Process MMC Data</p>
<p>Parameters:</p>
<ul>
<li>sysexData - Sysex Data as Hex String</li>
</ul>
<p>Returns:</p>
<ul>
<li>A string with the MMC command, and any additional parameters as per below notes.</li>
</ul>
<p>Notes:</p>
<ul>
<li>The possible MMC commands are:<ul>
<li>STOP</li>
<li>PLAY</li>
<li>DEFERRED_PLAY</li>
<li>FAST_FORWARD</li>
<li>REWIND</li>
<li>RECORD_STROBE</li>
<li>RECORD_EXIT</li>
<li>RECORD_PAUSE</li>
<li>PAUSE</li>
<li>EJECT</li>
<li>CHASE</li>
<li>MMC_RESET</li>
<li>WRITE</li>
<li>GOTO<ul>
<li>timecode - Timecode as string, in the following format: "hh:mm:ss:fr" (i.e. "12:03:03:13").</li>
<li>frameRate - Frame Rate as string, possible options include: "24", "25", "30 DF" or "30 NDF".</li>
<li>subframe - Subframe as string.</li>
</ul>
</li>
<li>ERROR</li>
<li>SHUTTLE</li>
</ul>
</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="processMTC">
	<h5><a href="#processMTC">processMTC</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.processMTC(mtcData) -&gt; string, ...</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Process MTC Data</p>
<p>Parameters:</p>
<ul>
<li>mtcData - MTC Data as Hex String</li>
</ul>
<p>Returns:</p>
<ul>
<li>A string with the MTC command, and any additional parameters.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="registerCallback">
	<h5><a href="#registerCallback">registerCallback</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.registerCallback(id, fn) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Registers a MIDI Callback.</p>
<p>Parameters:</p>
<ul>
<li>id - The ID as a string.</li>
<li>fn - The function you want to trigger.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="registerListenMMCFunction">
	<h5><a href="#registerListenMMCFunction">registerListenMMCFunction</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.registerListenMMCFunction(id, fn) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Registers a MMC Listening Function</p>
<p>Parameters:</p>
<ul>
<li>id - The group ID as a string.</li>
<li>fn - The function you want to trigger.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="registerListenMTCFunction">
	<h5><a href="#registerListenMTCFunction">registerListenMTCFunction</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.registerListenMTCFunction(id, fn) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Registers a MTC Listening Function</p>
<p>Parameters:</p>
<ul>
<li>id - The group ID as a string.</li>
<li>fn - The function you want to trigger.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="sendMMC">
	<h5><a href="#sendMMC">sendMMC</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.sendMMC(deviceName, virtual, commandType, parameters) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Sends MMC Data to a MIDI Device.</p>
<p>Parameters:</p>
<ul>
<li>deviceName - The MIDI Device name.</li>
<li>virtual - Is this MIDI Device virtual as boolean?</li>
<li>channelNumber - "00" to "7F", where "7F" is all devices.</li>
<li>commandType - Command Type as string (see possible options in Notes below)</li>
<li>parameters - Optional parameters in a table.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successfully sent otherwise <code>false</code>.</li>
</ul>
<p>Notes:</p>
<ul>
<li>The possible MMC commands are:<ul>
<li>STOP</li>
<li>PLAY</li>
<li>DEFERRED_PLAY</li>
<li>FAST_FORWARD</li>
<li>REWIND</li>
<li>RECORD_STROBE</li>
<li>RECORD_EXIT</li>
<li>RECORD_PAUSE</li>
<li>PAUSE</li>
<li>EJECT</li>
<li>CHASE</li>
<li>MMC_RESET</li>
<li>WRITE</li>
<li>GOTO<ul>
<li>timecode - Timecode as string, in the following format: "hh:mm:ss:fr" (i.e. "12:03:03:13").</li>
<li>frameRate - Frame Rate as string, possible options include: "24", "25", "30 DF" or "30 NDF".</li>
<li>subFrame - Subframe as string.</li>
</ul>
</li>
<li>ERROR</li>
<li>SHUTTLE</li>
<li>Example Usage:<div class="highlight"><pre><span></span><span class="n">_plugins</span><span class="p">(</span><span class="s2">&quot;core.midi.manager&quot;</span><span class="p">).</span><span class="n">sendMMC</span><span class="p">(</span><span class="s2">&quot;CommandPost&quot;</span><span class="p">,</span> <span class="kc">false</span><span class="p">,</span> <span class="s2">&quot;7F&quot;</span><span class="p">,</span> <span class="s2">&quot;GOTO&quot;</span><span class="p">,</span> <span class="p">{</span><span class="n">timecode</span><span class="o">=</span><span class="s2">&quot;01:02:03:04&quot;</span><span class="p">,</span> <span class="n">frameRate</span><span class="o">=</span><span class="s2">&quot;25&quot;</span><span class="p">,</span> <span class="n">subFrame</span><span class="o">=</span><span class="s2">&quot;00&quot;</span><span class="p">})</span>
</pre></div>
</li>
</ul>
</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="setItem">
	<h5><a href="#setItem">setItem</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.setItem(item, button, group, value) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Stores a MIDI item in Preferences.</p>
<p>Parameters:</p>
<ul>
<li>item - The item you want to set.</li>
<li>button - Button ID as string</li>
<li>group - Group ID as string</li>
<li>value - The value of the item you want to set.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="start">
	<h5><a href="#start">start</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.start() -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Stops the MIDI Plugin</p>
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
  <section id="update">
	<h5><a href="#update">update</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.update() -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Updates the MIDI Watchers.</p>
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
  <section id="updateAction">
	<h5><a href="#updateAction">updateAction</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.updateAction(button, group, actionTitle, handlerID, action) -&gt; none</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Updates a MIDI action.</p>
<p>Parameters:</p>
<ul>
<li>button - Button ID as string</li>
<li>group - Group ID as string</li>
<li>actionTitle - Action Title as string</li>
<li>handlerID - Handler ID as string</li>
<li>action - Action in a table</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="virtualDevices">
	<h5><a href="#virtualDevices">virtualDevices</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.virtualDevices() -&gt; table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Gets a table of Virtual MIDI Source Names.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table of Virtual MIDI Source Names.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Fields</h4>
  <section id="buttons">
	<h5><a href="#buttons">buttons</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.buttons &lt;cp.prop: table&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Contains all the saved MIDI items</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="enabled">
	<h5><a href="#enabled">enabled</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.enabled &lt;cp.prop: boolean&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Enable or disable MIDI Support.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="listenMMC">
	<h5><a href="#listenMMC">listenMMC</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.listenMMC &lt;cp.prop: boolean&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Enable or disable Listen MMC Support.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="listenMMCDevice">
	<h5><a href="#listenMMCDevice">listenMMCDevice</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.listenMMCDevice &lt;cp.prop: string&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>MIDI Device</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="listenMTC">
	<h5><a href="#listenMTC">listenMTC</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.listenMTC &lt;cp.prop: boolean&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Enable or disable Listen MTC Support.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="listenMTCDevice">
	<h5><a href="#listenMTCDevice">listenMTCDevice</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.listenMTCDevice &lt;cp.prop: string&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>MIDI Device</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="transmitMMC">
	<h5><a href="#transmitMMC">transmitMMC</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.transmitMMC &lt;cp.prop: boolean&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Enable or disable Transmit MMC Support.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="transmitMMCDevice">
	<h5><a href="#transmitMMCDevice">transmitMMCDevice</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.transmitMMCDevice &lt;cp.prop: string&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>MIDI Device</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="transmitMTC">
	<h5><a href="#transmitMTC">transmitMTC</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.transmitMTC &lt;cp.prop: boolean&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Enable or disable Transmit MTC Support.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="transmitMTCDevice">
	<h5><a href="#transmitMTCDevice">transmitMTCDevice</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.core.midi.manager.transmitMTCDevice &lt;cp.prop: string&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>MIDI Device</p>
</td>
	  </tr>
	</table>
  </section>
