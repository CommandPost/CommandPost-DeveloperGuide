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
      <h1><a href="cp.commands.md">docs</a> &raquo; cp.commands</h1>
      <p>Commands Module.</p>

      </header>
        <h3>Submodules</h3>
        <ul>
        <li><a href="cp.commands.command.html">cp.commands.command</a></li>
        <li><a href="cp.commands.englishKeyCodes.html">cp.commands.englishKeyCodes</a></li>
        <li><a href="cp.commands.shortcut.html">cp.commands.shortcut</a></li>
        </ul>
      <h3>API Overview</h3>
      <ul>
        <li>Constants - Useful values which cannot be changed</li>
          <ul>
            <li><a href="#DEFAULT_EXTENSION">DEFAULT_EXTENSION</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#getShortcutsPath">getShortcutsPath</a></li>
            <li><a href="#group">group</a></li>
            <li><a href="#groupIds">groupIds</a></li>
            <li><a href="#groups">groups</a></li>
            <li><a href="#loadFromFile">loadFromFile</a></li>
            <li><a href="#new">new</a></li>
            <li><a href="#saveToFile">saveToFile</a></li>
          </ul>
        <li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
          <ul>
            <li><a href="#enabled">enabled</a></li>
            <li><a href="#isEditable">isEditable</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#activate">activate</a></li>
            <li><a href="#add">add</a></li>
            <li><a href="#clear">clear</a></li>
            <li><a href="#deleteShortcuts">deleteShortcuts</a></li>
            <li><a href="#disable">disable</a></li>
            <li><a href="#enable">enable</a></li>
            <li><a href="#get">get</a></li>
            <li><a href="#getAll">getAll</a></li>
            <li><a href="#id">id</a></li>
            <li><a href="#loadShortcuts">loadShortcuts</a></li>
            <li><a href="#saveShortcuts">saveShortcuts</a></li>
            <li><a href="#watch">watch</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Constants</h4>
          <section id="DEFAULT_EXTENSION">
            <a name="//apple_ref/cpp/Constant/DEFAULT_EXTENSION" class="dashAnchor"></a>
            <h5><a href="#DEFAULT_EXTENSION">DEFAULT_EXTENSION</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.commands.DEFAULT_EXTENSION -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The menubar position priority.</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Functions</h4>
          <section id="getShortcutsPath">
            <a name="//apple_ref/cpp/Function/getShortcutsPath" class="dashAnchor"></a>
            <h5><a href="#getShortcutsPath">getShortcutsPath</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.commands.getShortcutsPath(name) -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the path to the named shortcut set.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="group">
            <a name="//apple_ref/cpp/Function/group" class="dashAnchor"></a>
            <h5><a href="#group">group</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.commands.group(id) -&gt; cp.command or nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a collection of commands. These commands can be enabled or disabled as a group.</p>
<p>Parameters:</p>
<ul>
<li><code>id</code>      - The ID to retrieve</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>cp.commands</code> - The command group with the specified ID, or <code>nil</code> if none exists.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="groupIds">
            <a name="//apple_ref/cpp/Function/groupIds" class="dashAnchor"></a>
            <h5><a href="#groupIds">groupIds</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.commands.groupIds() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns an array of IDs of command groups which have been created.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>table</code> - The array of group IDs.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="groups">
            <a name="//apple_ref/cpp/Function/groups" class="dashAnchor"></a>
            <h5><a href="#groups">groups</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.commands.groups() -&gt; table of cp.commands</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a table with the set of commands.</p>
<p>Parameters:</p>
<ul>
<li><code>id</code>      - The ID to retrieve</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>cp.commands</code> - The command group with the specified ID, or <code>nil</code> if none exists.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="loadFromFile">
            <a name="//apple_ref/cpp/Function/loadFromFile" class="dashAnchor"></a>
            <h5><a href="#loadFromFile">loadFromFile</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.commands.loadFromFile(name) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Loads a shortcut set from the standard location with the specified name.</p>
<p>Parameters:</p>
<ul>
<li>name      - The name of the shortcut set. E.g. "My Custom Shortcuts"</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the file was found and loaded successfully.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="new">
            <a name="//apple_ref/cpp/Function/new" class="dashAnchor"></a>
            <h5><a href="#new">new</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.commands.new(id) -&gt; cp.commands</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a collection of commands. These commands can be enabled or disabled as a group.</p>
<p>Parameters:</p>
<ul>
<li><code>id</code>     - The unique ID for this command group.</li>
</ul>
<p>Returns:</p>
<ul>
<li>cp.commands - The command group that was created.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="saveToFile">
            <a name="//apple_ref/cpp/Function/saveToFile" class="dashAnchor"></a>
            <h5><a href="#saveToFile">saveToFile</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.commands.saveToFile(name) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Saves the current shortcuts for all groups to a file in the standard location with the provided name.</p>
<p>Parameters:</p>
<ul>
<li>name      - The name of the command set. E.g. "My Custom Commands"</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the shortcuts were saved successfully.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Fields</h4>
          <section id="enabled">
            <a name="//apple_ref/cpp/Field/enabled" class="dashAnchor"></a>
            <h5><a href="#enabled">enabled</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.commands.enabled &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>If enabled, the commands in the group will be active as well.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="isEditable">
            <a name="//apple_ref/cpp/Field/isEditable" class="dashAnchor"></a>
            <h5><a href="#isEditable">isEditable</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.commands.isEditable &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>If set to <code>false</code>, the command group is not user-editable.</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Methods</h4>
          <section id="activate">
            <a name="//apple_ref/cpp/Method/activate" class="dashAnchor"></a>
            <h5><a href="#activate">activate</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.commands:activate(successFn, failureFn) -&gt; nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Will trigger an 'activate' event, and then execute either the <code>successFn</code> or <code>failureFn</code> if the
command group is not enabled within 5 seconds.</p>
<p>Parameters:</p>
<ul>
<li>successFn     - the function to call if successfully activated.</li>
<li>failureFn     - the function to call if not activated after 5 seconds.</li>
</ul>
<p>Returns:</p>
<ul>
<li>Nothing.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="add">
            <a name="//apple_ref/cpp/Method/add" class="dashAnchor"></a>
            <h5><a href="#add">add</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.commands:add(commandId) -&gt; cp.commands.command</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Adds a new command with the specified ID to this group. Additional configuration
should be applied to the returned <code>command</code> instance. Eg:</p>
<div class="highlight"><pre><span></span><span class="n">myCommands</span><span class="p">:</span><span class="n">add</span><span class="p">(</span><span class="s2">&quot;fooBar&quot;</span><span class="p">):</span><span class="n">groupedBy</span><span class="p">(</span><span class="s2">&quot;foo&quot;</span><span class="p">):</span><span class="n">whenActivated</span><span class="p">(</span><span class="kr">function</span><span class="p">()</span> <span class="p">...</span> <span class="kr">end</span><span class="p">)</span><span class="err">`</span>
</pre></div>
<p>Parameters:</p>
<ul>
<li><code>commandId</code>   - The unique ID for the new command.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The new <code>cp.commands.command</code> instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="clear">
            <a name="//apple_ref/cpp/Method/clear" class="dashAnchor"></a>
            <h5><a href="#clear">clear</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.commands:clear() -&gt; cp.commands</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Clears all commands and their shortcuts.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The command group instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="deleteShortcuts">
            <a name="//apple_ref/cpp/Method/deleteShortcuts" class="dashAnchor"></a>
            <h5><a href="#deleteShortcuts">deleteShortcuts</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.commands:deleteShortcuts() -&gt; cp.commands</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Clears all shortcuts associated with commands in this command group.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The command group instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="disable">
            <a name="//apple_ref/cpp/Method/disable" class="dashAnchor"></a>
            <h5><a href="#disable">disable</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.commands:disable() -&gt; cp.commands</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Disables the command group.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The command group instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="enable">
            <a name="//apple_ref/cpp/Method/enable" class="dashAnchor"></a>
            <h5><a href="#enable">enable</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.commands:enable() -&gt; cp.commands</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Enables the command group.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The command group instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="get">
            <a name="//apple_ref/cpp/Method/get" class="dashAnchor"></a>
            <h5><a href="#get">get</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.commands:get(commandId) -&gt; cp.commands.command</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the command with the specified ID, or <code>nil</code> if none exists.</p>
<p>Parameters:</p>
<ul>
<li><code>commandId</code>   - The command ID to retrieve.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.commands.command</code>, or <code>nil</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="getAll">
            <a name="//apple_ref/cpp/Method/getAll" class="dashAnchor"></a>
            <h5><a href="#getAll">getAll</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.commands:getAll() -&gt; table of cp.commands.command</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the table of commands, with the key being the ID and the value being the command instance. Eg:</p>
<div class="highlight"><pre><span></span><span class="kr">for</span> <span class="n">id</span><span class="p">,</span><span class="n">cmd</span> <span class="kr">in</span> <span class="nb">pairs</span><span class="p">(</span><span class="n">myCommands</span><span class="p">:</span><span class="n">getAll</span><span class="p">())</span> <span class="kr">do</span>
    <span class="p">...</span>
<span class="kr">end</span>
</pre></div>
</td>
              </tr>
            </table>
          </section>
          <section id="id">
            <a name="//apple_ref/cpp/Method/id" class="dashAnchor"></a>
            <h5><a href="#id">id</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.commands:id() -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the unique ID of the command group.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The command group ID string.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="loadShortcuts">
            <a name="//apple_ref/cpp/Method/loadShortcuts" class="dashAnchor"></a>
            <h5><a href="#loadShortcuts">loadShortcuts</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.commands:loadShortcuts(data) -&gt; nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Loads the shortcut details in the data table and applies them to the commands in this group.
The data should probably come from the <code>saveShortcuts</code> method.</p>
<p>Parameters:</p>
<ul>
<li>data      - The data table containing shortcuts.</li>
</ul>
<p>Returns:</p>
<ul>
<li>Nothing</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="saveShortcuts">
            <a name="//apple_ref/cpp/Method/saveShortcuts" class="dashAnchor"></a>
            <h5><a href="#saveShortcuts">saveShortcuts</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.commands:saveShortcuts() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a table that is approprate to be saved to file that contains the shortuct
for all contained <code>cp.commands.command</code> instances.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The table of shortcuts for commands.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="watch">
            <a name="//apple_ref/cpp/Method/watch" class="dashAnchor"></a>
            <h5><a href="#watch">watch</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.commands:watch(events) -&gt; cp.commands</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Adds an event watcher to the command group.</p>
<p>Parameters:</p>
<ul>
<li>events    - The table of events to watch for (see Notes).</li>
</ul>
<p>Returns:</p>
<ul>
<li>The command group instance.</li>
</ul>
<p>Notes:</p>
<ul>
<li>The table can have properties with the following functions, which will be called for the specific event:
<strong> <code>add(command)</code>:      Called after the provided <code>cp.commands.command</code> instance has been added.</strong> <code>activate()</code>         Called when the command group is activated.
<strong> <code>enable()</code>:          Called when the command group is enabled.</strong> <code>disable()</code>:         Called when the command group is disabled.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
