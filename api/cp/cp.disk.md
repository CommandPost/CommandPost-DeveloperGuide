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
      <h1><a href="cp.disk.md">docs</a> &raquo; cp.disk</h1>
      <p>Provides provides details about disk devices attached to the system.
These may be mounted, unmounted, and may include devices which do not
mount, or appear in the user interface by default.</p>
<p>The various methods have <code>options</code> table parameters, which allow filtering
to be performed on the operations. These tables can have any combination of
the following:</p>
<ul>
<li><code>physical</code>        - only process physical drives.</li>
<li><code>virtual</code>         - only process virtual drives.</li>
<li><code>external</code>        - only external drives.</li>
<li><code>internal</code>        - only internal drives.</li>
<li><code>ejectable</code>       - only drives that can be ejected.</li>
<li><code>bootable</code>        - only bootable drives.</li>
<li><code>writable</code>        - only writeable drives.</li>
<li><code>root</code>            - only top-level drives (vs partitions)</li>
<li><code>hidden</code>          - by default, only 'unhidden' devices are returned.</li>
<li><code>mounted</code>         - only mounted drives.</li>
<li><code>unmounted</code>       - only unmounted drives.</li>
</ul>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">battery</span> <span class="o">=</span> <span class="nb">require</span><span class="p">(</span><span class="s2">&quot;cp.battery&quot;</span><span class="p">)</span>
<span class="kd">local</span> <span class="n">externalDrives</span> <span class="o">=</span> <span class="n">battery</span><span class="p">.</span><span class="n">devices</span><span class="p">({</span><span class="n">physical</span> <span class="o">=</span> <span class="kc">true</span><span class="p">,</span> <span class="n">ejectable</span> <span class="o">=</span> <span class="kc">true</span><span class="p">})</span>
</pre></div>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#eject">eject</a></li>
            <li><a href="#mount">mount</a></li>
            <li><a href="#unmount">unmount</a></li>
            <li><a href="#visit">visit</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Functions</h4>
          <section id="eject">
            <a name="//apple_ref/cpp/Function/eject" class="dashAnchor"></a>
            <h5><a href="#eject">eject</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.disk.eject(options) -&gt; nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Unmounts and ejects (where appropriate) all disks matching the provided <code>options</code>.</p>
<p>Parameters:</p>
<ul>
<li>options   - The table of filter options.</li>
</ul>
<p>Returns:</p>
<ul>
<li>Nothing.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="mount">
            <a name="//apple_ref/cpp/Function/mount" class="dashAnchor"></a>
            <h5><a href="#mount">mount</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.disk.mount(options) -&gt; nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Mounts all disks matching the provided <code>options</code>.</p>
<p>Parameters:</p>
<ul>
<li>options   - The table of filter options.</li>
</ul>
<p>Returns:</p>
<ul>
<li>Nothing.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="unmount">
            <a name="//apple_ref/cpp/Function/unmount" class="dashAnchor"></a>
            <h5><a href="#unmount">unmount</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.disk.unmount(options) -&gt; nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Unmounts all disks matching the provided <code>options</code>.</p>
<p>Parameters:</p>
<ul>
<li>options   - The table of filter options.</li>
</ul>
<p>Returns:</p>
<ul>
<li>Nothing.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="visit">
            <a name="//apple_ref/cpp/Function/visit" class="dashAnchor"></a>
            <h5><a href="#visit">visit</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.disk.visit(options, fn) -&gt; nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Visits all drives matching the <code>options</code> and executes the
<code>fn</code> function with the <code>deviceID</code> string (e.g. "disk0" or "disk2s1") and a table of additional data about the drive.</p>
<p>Parameters:</p>
<ul>
<li>options   - The table of filter options.</li>
<li>fn        - The function to execute.</li>
</ul>
<p>Returns:</p>
<ul>
<li>Nothing.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
