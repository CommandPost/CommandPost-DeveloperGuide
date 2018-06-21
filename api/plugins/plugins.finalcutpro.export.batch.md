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
      <h1><a href="plugins.finalcutpro.export.batch.md">docs</a> &raquo; plugins.finalcutpro.export.batch</h1>
      <p>Batch Export Plugin</p>

      </header>
        <h3>Submodules</h3>
        <ul>
        <li><a href="plugins.finalcutpro.export.batch.manager.html">plugins.finalcutpro.export.batch.manager</a></li>
        </ul>
      <h3>API Overview</h3>
      <ul>
        <li>Constants - Useful values which cannot be changed</li>
          <ul>
            <li><a href="#DEFAULT_CUSTOM_FILENAME">DEFAULT_CUSTOM_FILENAME</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#batchExport">batchExport</a></li>
            <li><a href="#batchExportBrowserClips">batchExportBrowserClips</a></li>
            <li><a href="#batchExportTimelineClips">batchExportTimelineClips</a></li>
            <li><a href="#changeCustomFilename">changeCustomFilename</a></li>
            <li><a href="#changeExportDestinationFolder">changeExportDestinationFolder</a></li>
            <li><a href="#changeExportDestinationPreset">changeExportDestinationPreset</a></li>
            <li><a href="#getDestinationFolder">getDestinationFolder</a></li>
            <li><a href="#performBatchExport">performBatchExport</a></li>
            <li><a href="#sendBrowserClipsToCompressor">sendBrowserClipsToCompressor</a></li>
            <li><a href="#sendTimelineClipsToCompressor">sendTimelineClipsToCompressor</a></li>
          </ul>
        <li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
          <ul>
            <li><a href="#customFilename">customFilename</a></li>
            <li><a href="#ignoreMissingEffects">ignoreMissingEffects</a></li>
            <li><a href="#ignoreProxies">ignoreProxies</a></li>
            <li><a href="#replaceExistingFiles">replaceExistingFiles</a></li>
            <li><a href="#useCustomFilename">useCustomFilename</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Constants</h4>
          <section id="DEFAULT_CUSTOM_FILENAME">
            <a name="//apple_ref/cpp/Constant/DEFAULT_CUSTOM_FILENAME" class="dashAnchor"></a>
            <h5><a href="#DEFAULT_CUSTOM_FILENAME">DEFAULT_CUSTOM_FILENAME</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.export.batch.DEFAULT_CUSTOM_FILENAME -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Default Custom Filename</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Functions</h4>
          <section id="batchExport">
            <a name="//apple_ref/cpp/Function/batchExport" class="dashAnchor"></a>
            <h5><a href="#batchExport">batchExport</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.export.batch.batchExport() -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Opens the Batch Export popup.</p>
<p>Parameters:</p>
<ul>
<li>mode - "timeline" or "browser". If no mode is specified then we will determine
<pre><code>   the mode based off the mouse location.</code></pre>
</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successful otherwise <code>false</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="batchExportBrowserClips">
            <a name="//apple_ref/cpp/Function/batchExportBrowserClips" class="dashAnchor"></a>
            <h5><a href="#batchExportBrowserClips">batchExportBrowserClips</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.export.batch.batchExportBrowserClips(clips) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Batch Export Clips</p>
<p>Parameters:</p>
<ul>
<li>clips - table of selected Clips</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successful otherwise <code>false</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="batchExportTimelineClips">
            <a name="//apple_ref/cpp/Function/batchExportTimelineClips" class="dashAnchor"></a>
            <h5><a href="#batchExportTimelineClips">batchExportTimelineClips</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.export.batch.batchExportTimelineClips(clips) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Batch Export Timeline Clips</p>
<p>Parameters:</p>
<ul>
<li>clips - table of selected Clips</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successful otherwise <code>false</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="changeCustomFilename">
            <a name="//apple_ref/cpp/Function/changeCustomFilename" class="dashAnchor"></a>
            <h5><a href="#changeCustomFilename">changeCustomFilename</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.export.batch.changeCustomFilename() -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Change Custom Filename String.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successful otherwise <code>false</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="changeExportDestinationFolder">
            <a name="//apple_ref/cpp/Function/changeExportDestinationFolder" class="dashAnchor"></a>
            <h5><a href="#changeExportDestinationFolder">changeExportDestinationFolder</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.export.batch.changeExportDestinationFolder() -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Change Export Destination Folder.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successful otherwise <code>false</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="changeExportDestinationPreset">
            <a name="//apple_ref/cpp/Function/changeExportDestinationPreset" class="dashAnchor"></a>
            <h5><a href="#changeExportDestinationPreset">changeExportDestinationPreset</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.export.batch.changeExportDestinationPreset() -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Change Export Destination Preset.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successful otherwise <code>false</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="getDestinationFolder">
            <a name="//apple_ref/cpp/Function/getDestinationFolder" class="dashAnchor"></a>
            <h5><a href="#getDestinationFolder">getDestinationFolder</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.export.batch.getDestinationFolder() -&gt; string | nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets the destination preset.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The destination preset as a string, or <code>nil</code> if no preset is set.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="performBatchExport">
            <a name="//apple_ref/cpp/Function/performBatchExport" class="dashAnchor"></a>
            <h5><a href="#performBatchExport">performBatchExport</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.export.batch.performBatchExport() -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Performs the Browser Batch Export function.</p>
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
          <section id="sendBrowserClipsToCompressor">
            <a name="//apple_ref/cpp/Function/sendBrowserClipsToCompressor" class="dashAnchor"></a>
            <h5><a href="#sendBrowserClipsToCompressor">sendBrowserClipsToCompressor</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.export.batch.sendBrowserClipsToCompressor(clips) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Send Clips to Compressor</p>
<p>Parameters:</p>
<ul>
<li>clips - table of selected Clips</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successful otherwise <code>false</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="sendTimelineClipsToCompressor">
            <a name="//apple_ref/cpp/Function/sendTimelineClipsToCompressor" class="dashAnchor"></a>
            <h5><a href="#sendTimelineClipsToCompressor">sendTimelineClipsToCompressor</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.export.batch.sendTimelineClipsToCompressor(clips) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Send Timeline Clips to Compressor.</p>
<p>Parameters:</p>
<ul>
<li>clips - table of selected Clips</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successful otherwise <code>false</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Fields</h4>
          <section id="customFilename">
            <a name="//apple_ref/cpp/Field/customFilename" class="dashAnchor"></a>
            <h5><a href="#customFilename">customFilename</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.export.batch.customFilename &lt;cp.prop: string&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Custom Filename for Batch Export.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="ignoreMissingEffects">
            <a name="//apple_ref/cpp/Field/ignoreMissingEffects" class="dashAnchor"></a>
            <h5><a href="#ignoreMissingEffects">ignoreMissingEffects</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.export.batch.ignoreMissingEffects &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Defines whether or not a Batch Export should Ignore Missing Effects.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="ignoreProxies">
            <a name="//apple_ref/cpp/Field/ignoreProxies" class="dashAnchor"></a>
            <h5><a href="#ignoreProxies">ignoreProxies</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.export.batch.ignoreProxies &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Defines whether or not a Batch Export should Ignore Proxies.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="replaceExistingFiles">
            <a name="//apple_ref/cpp/Field/replaceExistingFiles" class="dashAnchor"></a>
            <h5><a href="#replaceExistingFiles">replaceExistingFiles</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.export.batch.replaceExistingFiles &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Defines whether or not a Batch Export should Replace Existing Files.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="useCustomFilename">
            <a name="//apple_ref/cpp/Field/useCustomFilename" class="dashAnchor"></a>
            <h5><a href="#useCustomFilename">useCustomFilename</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.export.batch.useCustomFilename &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Defines whether or not the Batch Export tool should override the clipname with a custom filename.</p>
</td>
              </tr>
            </table>
          </section>
