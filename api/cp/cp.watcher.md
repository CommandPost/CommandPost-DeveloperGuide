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
      <h1><a href="cp.watcher.md">docs</a> &raquo; cp.watcher</h1>
      <p>This extension provides support for setting up 'event watchers'.</p>
<p>For example, if you want to allow interested parties to watch for 'update'
events, you might have something like this:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">thing</span> <span class="o">=</span> <span class="p">{}</span>

<span class="n">thing</span><span class="p">.</span><span class="n">watchers</span> <span class="o">=</span> <span class="n">watcher</span><span class="p">.</span><span class="n">new</span><span class="p">(</span><span class="s1">&#39;update&#39;</span><span class="p">)</span>

<span class="n">thing</span><span class="p">.</span><span class="n">watch</span><span class="p">(</span><span class="n">events</span><span class="p">)</span>
    <span class="kr">return</span> <span class="n">thing</span><span class="p">.</span><span class="n">watchers</span><span class="p">:</span><span class="n">watch</span><span class="p">(</span><span class="n">events</span><span class="p">)</span>
<span class="kr">end</span>

<span class="n">thing</span><span class="p">.</span><span class="n">update</span><span class="p">(</span><span class="n">value</span><span class="p">)</span>
    <span class="n">thing</span><span class="p">.</span><span class="n">value</span> <span class="o">=</span> <span class="n">value</span>
    <span class="n">thing</span><span class="p">.</span><span class="n">watchers</span><span class="p">:</span><span class="n">notify</span><span class="p">(</span><span class="s1">&#39;update&#39;</span><span class="p">,</span> <span class="n">value</span><span class="p">)</span>
<span class="kr">end</span>
</pre></div>
<p>Then, your other code could get notifications like so:</p>
<div class="highlight"><pre><span></span><span class="n">thing</span><span class="p">.</span><span class="n">watch</span><span class="p">({</span>
    <span class="n">update</span> <span class="o">=</span> <span class="kr">function</span><span class="p">(</span><span class="n">value</span><span class="p">)</span> <span class="nb">print</span> <span class="s2">&quot;New value is &quot;</span><span class="o">..</span><span class="n">value</span> <span class="kr">end</span>
<span class="p">})</span>
</pre></div>
<p>Then, whenever <code>thing.update(xxx)</code> is called, the watcher will output <code>"New value is xxx"</code>.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#new">new</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#events">events</a></li>
            <li><a href="#getCount">getCount</a></li>
            <li><a href="#notify">notify</a></li>
            <li><a href="#unwatch">unwatch</a></li>
            <li><a href="#watch">watch</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Functions</h4>
          <section id="new">
            <a name="//apple_ref/cpp/Function/new" class="dashAnchor"></a>
            <h5><a href="#new">new</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.watcher.new(...) -&gt; watcher</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Constructs a new watcher instance.</p>
<p>Parameters:</p>
<ul>
<li><code>...</code> - The list of event name strings supported by the watcher.</li>
</ul>
<p>Returns:</p>
<ul>
<li>a new watcher instance</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Methods</h4>
          <section id="events">
            <a name="//apple_ref/cpp/Method/events" class="dashAnchor"></a>
            <h5><a href="#events">events</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.watcher:events()</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a list of the event names supported by this watcher.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The table of event names.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="getCount">
            <a name="//apple_ref/cpp/Method/getCount" class="dashAnchor"></a>
            <h5><a href="#getCount">getCount</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.watcher:getCount()</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the number of watchers currently registered.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The number of watchers.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="notify">
            <a name="//apple_ref/cpp/Method/notify" class="dashAnchor"></a>
            <h5><a href="#notify">notify</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.watcher:notify(type, ...) -&gt; nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Notifies watchers of the specified event type.</p>
<p>Parameters:</p>
<ul>
<li><code>type</code>   - The event type to notify. Must be one of the supported events.</li>
<li><code>...</code>    - These parameters are passed directly to the event watcher functions.</li>
</ul>
<p>Returns:</p>
<ul>
<li>Nothing.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="unwatch">
            <a name="//apple_ref/cpp/Method/unwatch" class="dashAnchor"></a>
            <h5><a href="#unwatch">unwatch</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.watcher:unwatch(id) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Removes the watchers which were added with the specified ID.</p>
<p>Parameters:</p>
<ul>
<li><code>id</code>     - The unique ID returned from <code>watch</code>.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if a watcher with the specified ID exists and was successfully removed.</li>
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
                <td><code>cp.watcher:watch(events) -&gt; id</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Adds a watcher for the specified events.</p>
<p>Parameters:</p>
<ul>
<li><code>events</code>     - A table of functions, one for each event to watch.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A unique ID that can be passed to <code>unwatch</code> to stop watching.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
