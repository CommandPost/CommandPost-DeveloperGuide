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
      <h1><a href="plugins.core.tangent.manager.named.md">docs</a> &raquo; plugins.core.tangent.manager.named</h1>
      <p>Provides common functions for 'named' Tangent nodes</p>
<p>Tables with <code>named</code> in it's metatable chain will have <code>name</code> methods added
as described below.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#is">is</a></li>
            <li><a href="#xml">xml</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#name">name</a></li>
            <li><a href="#nameX">nameX</a></li>
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
                <td><code>plugins.core.tangent.manager.named.is(thing) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Check if the <code>thing</code> is a <code>named</code> table.</p>
<p>Parameters:</p>
<ul>
<li>thing     - The thing to check.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if it is `named.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="xml">
            <a name="//apple_ref/cpp/Function/xml" class="dashAnchor"></a>
            <h5><a href="#xml">xml</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.named.xml(thing) -&gt; cp.web.xml</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the <code>xml</code> configuration for the Action.</p>
<p>Parameters:</p>
<ul>
<li>thing     - The thing to retrieve the names from.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>xml</code> for the Action.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Methods</h4>
          <section id="name">
            <a name="//apple_ref/cpp/Method/name" class="dashAnchor"></a>
            <h5><a href="#name">name</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.named:name(value) -&gt; string | self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets or sets the full name.</p>
<p>Parameters:</p>
<ul>
<li>value - The new name value.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>self</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="nameX">
            <a name="//apple_ref/cpp/Method/nameX" class="dashAnchor"></a>
            <h5><a href="#nameX">nameX</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.tangent.manager.named:nameX(value) -&gt; string | self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Sets the name <code>X</code>, where <code>X</code> is a number as defined when the <code>named</code> was creted.</p>
<p>Parameters:</p>
<ul>
<li>value - The new name value.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The current value, or <code>self</code> if a new value was provided.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
