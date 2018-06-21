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
      <h1><a href="plugins.core.tangent.manager.mode.md">docs</a> &raquo; plugins.core.tangent.manager.mode</h1>
      <p>Represents a Tangent Mode</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#is">is</a></li>
          </ul>
        <li>Constructors - API calls which return an object, typically one that offers API methods</li>
          <ul>
            <li><a href="#new">new</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#activate">activate</a></li>
            <li><a href="#onActivate">onActivate</a></li>
            <li><a href="#onDeactivate">onDeactivate</a></li>
            <li><a href="#xml">xml</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Functions</h4>
          <section id="is">
            <a name="//apple_ref/cpp/Function/is" class="dashAnchor"></a>
            <h5><a href="#is">is</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.mode.is(other) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks to see if other is a mode or not.</p>
<p>Parameters:</p>
<ul>
<li>other - The item to check</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if is a mode otherwise <code>false</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Constructors</h4>
          <section id="new">
            <a name="//apple_ref/cpp/Constructor/new" class="dashAnchor"></a>
            <h5><a href="#new">new</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.mode.new(id, name)</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new <code>Mode</code> instance.</p>
<p>Parameters:</p>
<ul>
<li>id        - The ID number of the mode.</li>
<li>name      - The name of the mode.</li>
</ul>
<p>Returns:
 *</p>
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
                <td><code>plugins.core.tangent.manager.mode:activate() -&gt; nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Executes the <code>activate</code> function, if present.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>nil</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="onActivate">
            <a name="//apple_ref/cpp/Method/onActivate" class="dashAnchor"></a>
            <h5><a href="#onActivate">onActivate</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.mode:onActivate(activateFn) -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Sets the function that will be called when the Tangent sends a 'mode change' request.
This function should have this signature:</p>
<div class="highlight"><pre><span></span><span class="kr">function</span><span class="p">()</span> <span class="o">-&gt;</span> <span class="kc">nil</span>
</pre></div>
<p>Parameters:</p>
<ul>
<li>activateFn     - The function to call when the Tangent requests the mode change.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>parameter</code> instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="onDeactivate">
            <a name="//apple_ref/cpp/Method/onDeactivate" class="dashAnchor"></a>
            <h5><a href="#onDeactivate">onDeactivate</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.mode:onDeactivate(deactivateFn) -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Sets the function that will be called when the Tangent sends a 'mode change' request and switche to a different mode.
This function should have this signature:</p>
<p><code>function() -&gt; nil</code></p>
<p>Parameters:</p>
<ul>
<li>deactivateFn     - The function to call when the Tangent requests the mode change.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>parameter</code> instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="xml">
            <a name="//apple_ref/cpp/Method/xml" class="dashAnchor"></a>
            <h5><a href="#xml">xml</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.mode:xml() -&gt; cp.web.xml</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the <code>xml</code> configuration for the Mode.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>xml</code> for the Mode.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
