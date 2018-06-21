    <style type="text/css">
      a { text-decoration: none; }
      a:hover { text-decoration: underline; }
      th { background-color: #DDDDDD; vertical-align: top; padding: 3px; }
      td { width: 100%; background-color: #EEEEEE; vertical-align: top; padding: 3px; }
      table { width: 100% ; border: 1px solid #0; text-align: left; }
      section > table table td { width: 0; }
    </style>
    <link rel="stylesheet" href="../../css/docs.css" type="text/css" media="screen" />
    <header>
      <h1><a href="plugins.finalcutpro.pasteboard.manager.md">docs</a> &raquo; plugins.finalcutpro.pasteboard.manager</h1>
      <p>Pasteboard Manager.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Constants - Useful values which cannot be changed</li>
          <ul>
            <li><a href="#NUMBER_OF_PASTEBOARD_BUFFERS">NUMBER_OF_PASTEBOARD_BUFFERS</a></li>
            <li><a href="#RESTART_DELAY">RESTART_DELAY</a></li>
          </ul>
        <li>Variables - Configurable values</li>
          <ul>
            <li><a href="#excludedClassnames">excludedClassnames</a></li>
            <li><a href="#WATCHER_FREQUENCY">WATCHER_FREQUENCY</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#copyWithCustomClipName">copyWithCustomClipName</a></li>
            <li><a href="#getClassname">getClassname</a></li>
            <li><a href="#isClassnameSupported">isClassnameSupported</a></li>
            <li><a href="#isTimelineClip">isTimelineClip</a></li>
            <li><a href="#overrideNextClipName">overrideNextClipName</a></li>
            <li><a href="#processArray">processArray</a></li>
            <li><a href="#processContent">processContent</a></li>
            <li><a href="#processObject">processObject</a></li>
            <li><a href="#readFCPXData">readFCPXData</a></li>
            <li><a href="#restoreFromBuffer">restoreFromBuffer</a></li>
            <li><a href="#saveToBuffer">saveToBuffer</a></li>
            <li><a href="#startWatching">startWatching</a></li>
            <li><a href="#stopWatching">stopWatching</a></li>
            <li><a href="#supportsContainedItems">supportsContainedItems</a></li>
            <li><a href="#unarchiveFCPXData">unarchiveFCPXData</a></li>
            <li><a href="#unwatch">unwatch</a></li>
            <li><a href="#watch">watch</a></li>
            <li><a href="#writeFCPXData">writeFCPXData</a></li>
          </ul>
        <li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
          <ul>
            <li><a href="#buffer">buffer</a></li>
            <li><a href="#watching">watching</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Constants</h4>
          <section id="NUMBER_OF_PASTEBOARD_BUFFERS">
            <a name="//apple_ref/cpp/Constant/NUMBER_OF_PASTEBOARD_BUFFERS" class="dashAnchor"></a>
            <h5><a href="#NUMBER_OF_PASTEBOARD_BUFFERS">NUMBER_OF_PASTEBOARD_BUFFERS</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.pasteboard.manager.NUMBER_OF_PASTEBOARD_BUFFERS -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Number of Pasteboard Buffers.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="RESTART_DELAY">
            <a name="//apple_ref/cpp/Constant/RESTART_DELAY" class="dashAnchor"></a>
            <h5><a href="#RESTART_DELAY">RESTART_DELAY</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.pasteboard.manager.RESTART_DELAY -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>How long to wait until we restart any Pasteboard Watchers.</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Variables</h4>
          <section id="excludedClassnames">
            <a name="//apple_ref/cpp/Variable/excludedClassnames" class="dashAnchor"></a>
            <h5><a href="#excludedClassnames">excludedClassnames</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.pasteboard.manager.excludedClassnames -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Table of data we don't want to count when copying.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="WATCHER_FREQUENCY">
            <a name="//apple_ref/cpp/Variable/WATCHER_FREQUENCY" class="dashAnchor"></a>
            <h5><a href="#WATCHER_FREQUENCY">WATCHER_FREQUENCY</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.pasteboard.manager.WATCHER_FREQUENCY -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The Pasteboard Watcher Update frequency.</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Functions</h4>
          <section id="copyWithCustomClipName">
            <a name="//apple_ref/cpp/Function/copyWithCustomClipName" class="dashAnchor"></a>
            <h5><a href="#copyWithCustomClipName">copyWithCustomClipName</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.pasteboard.manager.copyWithCustomClipName() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Copy with custom label.</p>
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
          <section id="getClassname">
            <a name="//apple_ref/cpp/Function/getClassname" class="dashAnchor"></a>
            <h5><a href="#getClassname">getClassname</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.pasteboard.manager.getClassname(data) -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets a class anem from data</p>
<p>Parameters:</p>
<ul>
<li>data - The data object to process</li>
</ul>
<p>Returns:</p>
<ul>
<li>Class name as string</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="isClassnameSupported">
            <a name="//apple_ref/cpp/Function/isClassnameSupported" class="dashAnchor"></a>
            <h5><a href="#isClassnameSupported">isClassnameSupported</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.pasteboard.manager.isClassnameSupported(classname) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Is the class name supported?</p>
<p>Parameters:</p>
<ul>
<li>classname - The class name you want to check</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the class name is supported otherwise <code>false</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="isTimelineClip">
            <a name="//apple_ref/cpp/Function/isTimelineClip" class="dashAnchor"></a>
            <h5><a href="#isTimelineClip">isTimelineClip</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.pasteboard.manager.isTimelineClip(data) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Is the data a timeline clip.</p>
<p>Parameters:</p>
<ul>
<li>data - The pasteboard data you want to check.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if a timeline clip otherwise <code>false</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="overrideNextClipName">
            <a name="//apple_ref/cpp/Function/overrideNextClipName" class="dashAnchor"></a>
            <h5><a href="#overrideNextClipName">overrideNextClipName</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.pasteboard.manager.overrideNextClipName(overrideName) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Overrides the name for the next clip which is copied from FCPX to the specified
value. Once the override has been used, the standard clip name via
<code>mod.findClipName(...)</code> will be used for subsequent copy operations.</p>
<p>Parameters:</p>
<ul>
<li>overrideName - The override name.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="processArray">
            <a name="//apple_ref/cpp/Function/processArray" class="dashAnchor"></a>
            <h5><a href="#processArray">processArray</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.pasteboard.manager.processArray(data) -&gt; string, number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Processes an 'array' table.</p>
<p>Parameters:</p>
<ul>
<li>data - The data object to process</li>
</ul>
<p>Returns:</p>
<ul>
<li>The primary clip name as a string.</li>
<li>The number of clips as number.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="processContent">
            <a name="//apple_ref/cpp/Function/processContent" class="dashAnchor"></a>
            <h5><a href="#processContent">processContent</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.pasteboard.manager.processContent(fcpxData, default) -&gt; string, number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Searches the Pasteboard binary plist data for the first clip name, and returns it.</p>
<p>Parameters:</p>
<ul>
<li>fcpxData - The data object to process</li>
<li>default - The default value</li>
</ul>
<p>Returns:</p>
<ul>
<li>Returns the 'default' value if the pasteboard contains a media clip but we could not interpret it, otherwise <code>nil</code> if the data did not contain Final Cut Pro Clip data.</li>
</ul>
<p>Notes:</p>
<ul>
<li>Example usage: <code>local name = mod.findClipName(myFcpxData, "Unknown")</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="processObject">
            <a name="//apple_ref/cpp/Function/processObject" class="dashAnchor"></a>
            <h5><a href="#processObject">processObject</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.pasteboard.manager.processObject(data) -&gt; string, number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Processes the provided data object, which should have a '$class' property.</p>
<p>Parameters:</p>
<ul>
<li>data - The pasteboard data you want to check.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The primary clip name as a string.</li>
<li>The number of clips as number.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="readFCPXData">
            <a name="//apple_ref/cpp/Function/readFCPXData" class="dashAnchor"></a>
            <h5><a href="#readFCPXData">readFCPXData</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.pasteboard.manager.readFCPXData() -&gt; data | nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Reads Final Cut Pro Data from the Pasteboard as a binary Property List, if present.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The pasteboard data or <code>nil</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="restoreFromBuffer">
            <a name="//apple_ref/cpp/Function/restoreFromBuffer" class="dashAnchor"></a>
            <h5><a href="#restoreFromBuffer">restoreFromBuffer</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.pasteboard.manager.restoreFromBuffer(id) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Restore a Pasteboard item from the buffer.</p>
<p>Parameters:</p>
<ul>
<li>id - The ID of the buffer item.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="saveToBuffer">
            <a name="//apple_ref/cpp/Function/saveToBuffer" class="dashAnchor"></a>
            <h5><a href="#saveToBuffer">saveToBuffer</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.pasteboard.manager.saveToBuffer(id) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Save a Pasteboard item to the buffer.</p>
<p>Parameters:</p>
<ul>
<li>id - The ID of the buffer item.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="startWatching">
            <a name="//apple_ref/cpp/Function/startWatching" class="dashAnchor"></a>
            <h5><a href="#startWatching">startWatching</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.pasteboard.manager.startWatching() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Start Watching the Pasteboard.</p>
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
          <section id="stopWatching">
            <a name="//apple_ref/cpp/Function/stopWatching" class="dashAnchor"></a>
            <h5><a href="#stopWatching">stopWatching</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.pasteboard.manager.stopWatching() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Stop Watching the Pasteboard.</p>
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
          <section id="supportsContainedItems">
            <a name="//apple_ref/cpp/Function/supportsContainedItems" class="dashAnchor"></a>
            <h5><a href="#supportsContainedItems">supportsContainedItems</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.pasteboard.manager.supportsContainedItems(data) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets whether or not the data supports contained items.</p>
<p>Parameters:</p>
<ul>
<li>data - The data object to process</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if supported otherwise <code>false</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="unarchiveFCPXData">
            <a name="//apple_ref/cpp/Function/unarchiveFCPXData" class="dashAnchor"></a>
            <h5><a href="#unarchiveFCPXData">unarchiveFCPXData</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.pasteboard.manager.unarchiveFCPXData(fcpxData) -&gt; data | nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Unarchive Final Cut Pro data.</p>
<p>Parameters:</p>
<ul>
<li>fcpxData - The data object to process</li>
</ul>
<p>Returns:</p>
<ul>
<li>The unarchived Final Cut Pro Pasteboard data or <code>nil</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="unwatch">
            <a name="//apple_ref/cpp/Function/unwatch" class="dashAnchor"></a>
            <h5><a href="#unwatch">unwatch</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.pasteboard.manager.unwatch(id) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Stop a watcher.</p>
<p>Parameters:</p>
<ul>
<li>id - The ID of the watcher you want to stop.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successful otherwise <code>false</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="watch">
            <a name="//apple_ref/cpp/Function/watch" class="dashAnchor"></a>
            <h5><a href="#watch">watch</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.pasteboard.manager.watch(events) -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Watch events.</p>
<p>Parameters:</p>
<ul>
<li>events - Table of events</li>
</ul>
<p>Returns:</p>
<ul>
<li>Table of watchers.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="writeFCPXData">
            <a name="//apple_ref/cpp/Function/writeFCPXData" class="dashAnchor"></a>
            <h5><a href="#writeFCPXData">writeFCPXData</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.pasteboard.manager.writeFCPXData(fcpxData, quiet) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Write Final Cut Pro data to Pasteboard.</p>
<p>Parameters:</p>
<ul>
<li>fcpxData - The data to write</li>
<li>quiet - Whether or not we should stop/start the watcher.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the operation succeeded, otherwise <code>false</code> (which most likely means ownership of the pasteboard has changed).</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Fields</h4>
          <section id="buffer">
            <a name="//apple_ref/cpp/Field/buffer" class="dashAnchor"></a>
            <h5><a href="#buffer">buffer</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.pasteboard.manager.buffer &lt;cp.prop: table&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Contains the Pasteboard Buffer.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="watching">
            <a name="//apple_ref/cpp/Field/watching" class="dashAnchor"></a>
            <h5><a href="#watching">watching</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.pasteboard.manager.watching &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets whether or not we're watching the pasteboard as a boolean.</p>
</td>
              </tr>
            </table>
          </section>
