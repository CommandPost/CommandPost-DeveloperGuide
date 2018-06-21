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
      <h1><a href="plugins.finalcutpro.browser.pasteboardtomarkers.md">docs</a> &raquo; plugins.finalcutpro.browser.pasteboardtomarkers</h1>
      <p>Take the contents of the Pasteboard and pastes it as clip markers on the
selected clip in the Final Cut Pro Browser. Only one clip can be selected.</p>
<p>Supported format:</p>

<pre><code>05:00:00: Test Keyword 1
#05:01:00:01: Test Keyword 2
*05:02:00: Test Keyword 3
05:02:15: Test Keyword 4
*05:03:00: Test Keyword 5
05:03:15: Test Keyword 6
#05:03:30: Test Keyword 7
*05:04:00: Test Keyword 8</code></pre>
<p>If a * is place before the timecode, it will make the clip as a favourite
between the current timecode value and the next timecode value.</p>
<p>If a # is place before the timecode, it will create a "To Do" marker.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#init">init</a></li>
            <li><a href="#process">process</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Functions</h4>
          <section id="init">
            <a name="//apple_ref/cpp/Function/init" class="dashAnchor"></a>
            <h5><a href="#init">init</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.browser.pasteboardtomarkers.init() -&gt; deps</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Initialise the module.</p>
<p>Parameters:</p>
<ul>
<li>deps - Plugin Dependencies</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="process">
            <a name="//apple_ref/cpp/Function/process" class="dashAnchor"></a>
            <h5><a href="#process">process</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.finalcutpro.browser.pasteboardtomarkers.process() -&gt; nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Processes Pasteboard to Markers</p>
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
