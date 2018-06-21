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
      <h1><a href="cp.choices.md">docs</a> &raquo; cp.choices</h1>
      <p>Choices Module.</p>

      </header>
        <h3>Submodules</h3>
        <ul>
        <li><a href="cp.choices.builder.html">cp.choices.builder</a></li>
        </ul>
      <h3>API Overview</h3>
      <ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#new">new</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#getChoices">getChoices</a></li>
            <li><a href="#new">new</a></li>
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
                <td><code>cp.choices.new(type) -&gt; choices</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new <code>cp.choices</code> instance for the specified type.</p>
<p>Parameters:</p>
<ul>
<li><code>type</code>    - The unique ID for the type.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The new <code>choices</code> instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Methods</h4>
          <section id="getChoices">
            <a name="//apple_ref/cpp/Method/getChoices" class="dashAnchor"></a>
            <h5><a href="#getChoices">getChoices</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.choices:getChoices() -&gt; array of choices</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the array of choices that have been added to this instance.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The array of choices.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="new">
            <a name="//apple_ref/cpp/Method/new" class="dashAnchor"></a>
            <h5><a href="#new">new</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.choices:new(choiceType) -&gt; choices.builder</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Adds a new choice with the specified. Additional settings
can be set using the returned builder instance. E.g.:</p>

<pre><code>choices:add("Do Something")
    :subText("Cool Actions")
        :params({
        one = "foo",
        two = "bar",
    })</code></pre>
<p>Parameters:</p>
<ul>
<li><code>text</code>   - The text title for the choice.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The choice builder, added to the choices set.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
