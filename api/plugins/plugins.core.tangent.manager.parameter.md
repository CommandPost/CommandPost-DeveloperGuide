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
      <h1><a href="plugins.core.tangent.manager.parameter.md">docs</a> &raquo; plugins.core.tangent.manager.parameter</h1>
      <p>Represents a Tangent Parameter</p>

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
            <li><a href="#change">change</a></li>
            <li><a href="#controls">controls</a></li>
            <li><a href="#get">get</a></li>
            <li><a href="#maxValue">maxValue</a></li>
            <li><a href="#minValue">minValue</a></li>
            <li><a href="#onChange">onChange</a></li>
            <li><a href="#onGet">onGet</a></li>
            <li><a href="#onReset">onReset</a></li>
            <li><a href="#parent">parent</a></li>
            <li><a href="#press">press</a></li>
            <li><a href="#release">release</a></li>
            <li><a href="#reset">reset</a></li>
            <li><a href="#stepSize">stepSize</a></li>
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
                <td><code>plugins.core.tangent.manager.parameter.is(other) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks if the <code>other</code> is a <code>parameter</code> instance.</p>
<p>Parameters:</p>
<ul>
<li>other     - The other object to test.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if it is a <code>parameter</code>, <code>false</code> if not.</li>
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
                <td><code>plugins.core.tangent.manager.parameter.new(id[, name[, parent]) -&gt; parameter</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new <code>Parameter</code> instance.</p>
<p>Parameters:</p>
<ul>
<li>id        - The ID number of the parameter.</li>
<li>name      - The name of the parameter.</li>
<li>parent    - The parent of the parameter.</li>
</ul>
<p>Returns:</p>
<ul>
<li>the new <code>parameter</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Methods</h4>
          <section id="change">
            <a name="//apple_ref/cpp/Method/change" class="dashAnchor"></a>
            <h5><a href="#change">change</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.parameter:change(amount) -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Executes the <code>change</code> function if present, and returns the new result. If
none has been set, <code>nil</code> is returned.</p>
<p>Parameters:</p>
<ul>
<li>amount    - The amount to change the parameter.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The current value, or <code>nil</code> if it can't be accessed.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="controls">
            <a name="//apple_ref/cpp/Method/controls" class="dashAnchor"></a>
            <h5><a href="#controls">controls</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.parameter:controls()</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the <code>controls</code> the parameter belongs to.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>controls</code>, or <code>nil</code> if not specified.</li>
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
                <td><code>plugins.core.tangent.manager.parameter:get() -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Executes the <code>get</code> function if present, and returns the result. If
none has been set, <code>nil</code> is returned.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The current value, or <code>nil</code> if it can't be accessed.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="maxValue">
            <a name="//apple_ref/cpp/Method/maxValue" class="dashAnchor"></a>
            <h5><a href="#maxValue">maxValue</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.parameter:maxValue([value]) -&gt; number | self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets or sets the maximum value for the parameter.</p>
<p>Parameters:</p>
<ul>
<li>value     - The new value.</li>
</ul>
<p>Returns:</p>
<ul>
<li>If <code>value</code> is <code>nil</code>, the current value is returned, otherwise returns <code>self</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="minValue">
            <a name="//apple_ref/cpp/Method/minValue" class="dashAnchor"></a>
            <h5><a href="#minValue">minValue</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.parameter:minValue([value]) -&gt; number | self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets or sets the minimum value for the parameter.</p>
<p>Parameters:</p>
<ul>
<li>value     - The new value.</li>
</ul>
<p>Returns:</p>
<ul>
<li>If <code>value</code> is <code>nil</code>, the current value is returned, otherwise returns <code>self</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="onChange">
            <a name="//apple_ref/cpp/Method/onChange" class="dashAnchor"></a>
            <h5><a href="#onChange">onChange</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.parameter:onChange(changeFn) -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Sets the function that will be called when the Tangent sends a 'parameter change' request.
This function should have this signature:</p>
<p><code>function(amount) -&gt; number</code></p>
<p>The return value should be the new value of the parameter.</p>
<p>Parameters:</p>
<ul>
<li>getFn     - The function to call when the Tangent requests the parameter change.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>parameter</code> instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="onGet">
            <a name="//apple_ref/cpp/Method/onGet" class="dashAnchor"></a>
            <h5><a href="#onGet">onGet</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.parameter:onGet(getFn) -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Sets the function that will be called when the Tangent sends a 'parameter value' request.
This function should have this signature:</p>
<p><code>function() -&gt; number</code></p>
<p>Parameters:</p>
<ul>
<li>getFn     - The function to call when the Tangent requests the parameter value.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>parameter</code> instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="onReset">
            <a name="//apple_ref/cpp/Method/onReset" class="dashAnchor"></a>
            <h5><a href="#onReset">onReset</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.parameter:onReset(resetFn) -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Sets the function that will be called when the Tangent sends a 'parameter reset' request.
This function should have this signature:</p>
<p><code>function() -&gt; nil</code></p>
<p>Parameters:</p>
<ul>
<li>resetFn     - The function to call when the Tangent requests the parameter reset.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>parameter</code> instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="parent">
            <a name="//apple_ref/cpp/Method/parent" class="dashAnchor"></a>
            <h5><a href="#parent">parent</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.parameter:parent() -&gt; group | controls</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the <code>group</code> or <code>controls</code> that contains this parameter.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The parent.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="press">
            <a name="//apple_ref/cpp/Method/press" class="dashAnchor"></a>
            <h5><a href="#press">press</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.parameter:press() -&gt; nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Executes the <code>press</code> function, if present.</p>
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
          <section id="release">
            <a name="//apple_ref/cpp/Method/release" class="dashAnchor"></a>
            <h5><a href="#release">release</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.parameter:release() -&gt; nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Executes the <code>release</code> function, if present.</p>
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
          <section id="reset">
            <a name="//apple_ref/cpp/Method/reset" class="dashAnchor"></a>
            <h5><a href="#reset">reset</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.parameter:reset() -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Executes the <code>reset</code> function if present. Returns the current value of the parameter after reset.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The current value, or <code>nil</code> if it can't be accessed.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="stepSize">
            <a name="//apple_ref/cpp/Method/stepSize" class="dashAnchor"></a>
            <h5><a href="#stepSize">stepSize</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.parameter:stepSize([value]) -&gt; number | self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets or sets the step size for the parameter.</p>
<p>Parameters:</p>
<ul>
<li>value     - The new value.</li>
</ul>
<p>Returns:</p>
<ul>
<li>If <code>value</code> is <code>nil</code>, the current value is returned, otherwise returns <code>self</code>.</li>
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
                <td><code>plugins.core.tangent.manager.parameter:xml() -&gt; cp.web.xml</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the <code>xml</code> configuration for the Parameter.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>xml</code> for the Parameter.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
