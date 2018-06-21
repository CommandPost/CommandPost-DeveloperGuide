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
      <h1><a href="plugins.core.touchbar.manager.md">docs</a> &raquo; plugins.core.touchbar.manager</h1>
      <p>Touch Bar Manager Plugin.
This handles both the Virtual Touch Bar and adding items to the physical Touch Bar.</p>

      </header>
        <h3>Submodules</h3>
        <ul>
        <li><a href="plugins.core.touchbar.manager.virtual.html">plugins.core.touchbar.manager.virtual</a></li>
        <li><a href="plugins.core.touchbar.manager.widgets.html">plugins.core.touchbar.manager.widgets</a></li>
        </ul>
      <h3>API Overview</h3>
      <ul>
        <li>Constants - Useful values which cannot be changed</li>
          <ul>
            <li><a href="#DEFAULT_GROUP">DEFAULT_GROUP</a></li>
            <li><a href="#FILE_NAME">FILE_NAME</a></li>
            <li><a href="#FOLDER_NAME">FOLDER_NAME</a></li>
          </ul>
        <li>Variables - Configurable values</li>
          <ul>
            <li><a href="#closeBox">closeBox</a></li>
            <li><a href="#maxItems">maxItems</a></li>
            <li><a href="#numberOfSubGroups">numberOfSubGroups</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#activeGroup">activeGroup</a></li>
            <li><a href="#activeSubGroup">activeSubGroup</a></li>
            <li><a href="#clear">clear</a></li>
            <li><a href="#getAction">getAction</a></li>
            <li><a href="#getActionHandlerID">getActionHandlerID</a></li>
            <li><a href="#getActionTitle">getActionTitle</a></li>
            <li><a href="#getIcon">getIcon</a></li>
            <li><a href="#getLabel">getLabel</a></li>
            <li><a href="#groupStatus">groupStatus</a></li>
            <li><a href="#incrementActiveSubGroup">incrementActiveSubGroup</a></li>
            <li><a href="#start">start</a></li>
            <li><a href="#stop">stop</a></li>
            <li><a href="#toggle">toggle</a></li>
            <li><a href="#touchBar">touchBar</a></li>
            <li><a href="#update">update</a></li>
            <li><a href="#updateAction">updateAction</a></li>
            <li><a href="#updateIcon">updateIcon</a></li>
            <li><a href="#updateLabel">updateLabel</a></li>
          </ul>
        <li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
          <ul>
            <li><a href="#buttons">buttons</a></li>
            <li><a href="#enabled">enabled</a></li>
            <li><a href="#supported">supported</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Constants</h4>
          <section id="DEFAULT_GROUP">
            <a name="//apple_ref/cpp/Constant/DEFAULT_GROUP" class="dashAnchor"></a>
            <h5><a href="#DEFAULT_GROUP">DEFAULT_GROUP</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.touchbar.manager.DEFAULT_GROUP -&gt; string</code></td>
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
          <section id="FILE_NAME">
            <a name="//apple_ref/cpp/Constant/FILE_NAME" class="dashAnchor"></a>
            <h5><a href="#FILE_NAME">FILE_NAME</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.touchbar.manager.FILE_NAME -&gt; string</code></td>
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
            <a name="//apple_ref/cpp/Constant/FOLDER_NAME" class="dashAnchor"></a>
            <h5><a href="#FOLDER_NAME">FOLDER_NAME</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.touchbar.manager.FOLDER_NAME -&gt; string</code></td>
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
        <h4 class="documentation-section">Variables</h4>
          <section id="closeBox">
            <a name="//apple_ref/cpp/Variable/closeBox" class="dashAnchor"></a>
            <h5><a href="#closeBox">closeBox</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.touchbar.manager.closeBox -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>An optional boolean, specifying whether or not the system
escape (or its current replacement) button should be replaced by a button
to remove the modal bar from the touch bar display when pressed.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="maxItems">
            <a name="//apple_ref/cpp/Variable/maxItems" class="dashAnchor"></a>
            <h5><a href="#maxItems">maxItems</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.touchbar.manager.maxItems -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Variable</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The maximum number of Touch Bar items per group.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="numberOfSubGroups">
            <a name="//apple_ref/cpp/Variable/numberOfSubGroups" class="dashAnchor"></a>
            <h5><a href="#numberOfSubGroups">numberOfSubGroups</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.touchbar.manager.numberOfSubGroups -&gt; number</code></td>
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
            <a name="//apple_ref/cpp/Function/activeGroup" class="dashAnchor"></a>
            <h5><a href="#activeGroup">activeGroup</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.touchbar.manager.activeGroup() -&gt; string</code></td>
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
            <a name="//apple_ref/cpp/Function/activeSubGroup" class="dashAnchor"></a>
            <h5><a href="#activeSubGroup">activeSubGroup</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.touchbar.manager.activeSubGroup() -&gt; string</code></td>
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
            <a name="//apple_ref/cpp/Function/clear" class="dashAnchor"></a>
            <h5><a href="#clear">clear</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.touchbar.manager.clear() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Clears the Touch Bar items.</p>
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
          <section id="getAction">
            <a name="//apple_ref/cpp/Function/getAction" class="dashAnchor"></a>
            <h5><a href="#getAction">getAction</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.touchbar.manager.getAction(button, group) -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a specific Touch Bar Action.</p>
<p>Parameters:</p>
<ul>
<li>button - Button ID as string</li>
<li>group - Group ID as string</li>
</ul>
<p>Returns:</p>
<ul>
<li>Action as string</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="getActionHandlerID">
            <a name="//apple_ref/cpp/Function/getActionHandlerID" class="dashAnchor"></a>
            <h5><a href="#getActionHandlerID">getActionHandlerID</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.touchbar.manager.getActionHandlerID(button, group) -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a specific Touch Bar Action Handler ID.</p>
<p>Parameters:</p>
<ul>
<li>button - Button ID as string</li>
<li>group - Group ID as string</li>
</ul>
<p>Returns:</p>
<ul>
<li>Action as string</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="getActionTitle">
            <a name="//apple_ref/cpp/Function/getActionTitle" class="dashAnchor"></a>
            <h5><a href="#getActionTitle">getActionTitle</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.touchbar.manager.getActionTitle(button, group) -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a specific Touch Bar Action Title.</p>
<p>Parameters:</p>
<ul>
<li>button - Button ID as string</li>
<li>group - Group ID as string</li>
</ul>
<p>Returns:</p>
<ul>
<li>Action as string</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="getIcon">
            <a name="//apple_ref/cpp/Function/getIcon" class="dashAnchor"></a>
            <h5><a href="#getIcon">getIcon</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.touchbar.manager.getIcon(button, group) -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a specific Touch Bar Icon.</p>
<p>Parameters:</p>
<ul>
<li>button - Button ID as string</li>
<li>group - Group ID as string</li>
</ul>
<p>Returns:</p>
<ul>
<li>Icon data as string</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="getLabel">
            <a name="//apple_ref/cpp/Function/getLabel" class="dashAnchor"></a>
            <h5><a href="#getLabel">getLabel</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.touchbar.manager.getLabel(button, group) -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a specific Touch Bar Label.</p>
<p>Parameters:</p>
<ul>
<li>button - Button ID as string</li>
<li>group - Group ID as string</li>
</ul>
<p>Returns:</p>
<ul>
<li>Label as string</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="groupStatus">
            <a name="//apple_ref/cpp/Function/groupStatus" class="dashAnchor"></a>
            <h5><a href="#groupStatus">groupStatus</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.touchbar.manager.groupStatus(groupID, status) -&gt; none</code></td>
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
          <section id="incrementActiveSubGroup">
            <a name="//apple_ref/cpp/Function/incrementActiveSubGroup" class="dashAnchor"></a>
            <h5><a href="#incrementActiveSubGroup">incrementActiveSubGroup</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.touchbar.manager.incrementActiveSubGroup() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Increments the active sub-group</p>
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
          <section id="start">
            <a name="//apple_ref/cpp/Function/start" class="dashAnchor"></a>
            <h5><a href="#start">start</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.touchbar.manager.start() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Starts the CommandPost Touch Bar module.</p>
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
          <section id="stop">
            <a name="//apple_ref/cpp/Function/stop" class="dashAnchor"></a>
            <h5><a href="#stop">stop</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.touchbar.manager.stop() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Stops the CommandPost Touch Bar module.</p>
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
          <section id="toggle">
            <a name="//apple_ref/cpp/Function/toggle" class="dashAnchor"></a>
            <h5><a href="#toggle">toggle</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.touchbar.manager.toggle() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Toggles the CommandPost Touch Bar module.</p>
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
          <section id="touchBar">
            <a name="//apple_ref/cpp/Function/touchBar" class="dashAnchor"></a>
            <h5><a href="#touchBar">touchBar</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.touchbar.manager.touchBar() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the <code>hs._asm.undocumented.touchbar</code> object if it exists.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>hs._asm.undocumented.touchbar</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="update">
            <a name="//apple_ref/cpp/Function/update" class="dashAnchor"></a>
            <h5><a href="#update">update</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.touchbar.manager.update() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Updates the Touch Bar.</p>
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
            <a name="//apple_ref/cpp/Function/updateAction" class="dashAnchor"></a>
            <h5><a href="#updateAction">updateAction</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.touchbar.manager.updateAction(button, group, action) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Updates a Touch Bar action.</p>
<p>Parameters:</p>
<ul>
<li>button - Button ID as string</li>
<li>group - Group ID as string</li>
<li>action - Action as string</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="updateIcon">
            <a name="//apple_ref/cpp/Function/updateIcon" class="dashAnchor"></a>
            <h5><a href="#updateIcon">updateIcon</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.touchbar.manager.updateIcon(button, group, icon) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Updates a Touch Bar icon.</p>
<p>Parameters:</p>
<ul>
<li>button - Button ID as string</li>
<li>group - Group ID as string</li>
<li>icon - Icon Data as string</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="updateLabel">
            <a name="//apple_ref/cpp/Function/updateLabel" class="dashAnchor"></a>
            <h5><a href="#updateLabel">updateLabel</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.touchbar.manager.updateLabel(button, group, label) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Updates a Touch Bar action.</p>
<p>Parameters:</p>
<ul>
<li>button - Button ID as string</li>
<li>group - Group ID as string</li>
<li>label - Label as string</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Fields</h4>
          <section id="buttons">
            <a name="//apple_ref/cpp/Field/buttons" class="dashAnchor"></a>
            <h5><a href="#buttons">buttons</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.touchbar.manager.buttons &lt;cp.prop: table&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Contains all the saved Touch Bar Buttons</p>
</td>
              </tr>
            </table>
          </section>
          <section id="enabled">
            <a name="//apple_ref/cpp/Field/enabled" class="dashAnchor"></a>
            <h5><a href="#enabled">enabled</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.touchbar.manager.enabled &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Enable or disable Touch Bar Support.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="supported">
            <a name="//apple_ref/cpp/Field/supported" class="dashAnchor"></a>
            <h5><a href="#supported">supported</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.touchbar.manager.supported &lt;cp.prop: boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Is <code>true</code> if the Touch Bar is supported on this version of macOS.</p>
</td>
              </tr>
            </table>
          </section>
