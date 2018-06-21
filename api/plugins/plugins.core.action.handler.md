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
      <h1><a href="plugins.core.action.handler.md">docs</a> &raquo; plugins.core.action.handler</h1>
      <p>A support class for handler handlers. It is not used directly, rather
it is a 'super class' that provides common functionality.</p>
<p>Instances of the class primarily need to provide functions for the following:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">handler</span> <span class="o">=</span> <span class="n">actionManager</span><span class="p">:</span><span class="n">addHandler</span><span class="p">(</span><span class="s2">&quot;foobar&quot;</span><span class="p">)</span>
<span class="p">:</span><span class="n">onChoices</span><span class="p">(</span><span class="kr">function</span><span class="p">(</span><span class="n">choices</span><span class="p">)</span> <span class="p">...</span> <span class="kr">end</span><span class="p">)</span>
<span class="p">:</span><span class="n">onExecute</span><span class="p">(</span><span class="kr">function</span><span class="p">(</span><span class="n">action</span><span class="p">)</span> <span class="p">...</span> <span class="kr">end</span><span class="p">)</span>
</pre></div>
<p>The choices added to the <code>choices</code> should have the <code>params</code> value set to a table
containing the details of the action to execute if the choice is selected.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Constructors - API calls which return an object, typically one that offers API methods</li>
          <ul>
            <li><a href="#new">new</a></li>
          </ul>
        <li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
          <ul>
            <li><a href="#cached">cached</a></li>
            <li><a href="#choices">choices</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#actionId">actionId</a></li>
            <li><a href="#execute">execute</a></li>
            <li><a href="#group">group</a></li>
            <li><a href="#id">id</a></li>
            <li><a href="#onActionId">onActionId</a></li>
            <li><a href="#onChoices">onChoices</a></li>
            <li><a href="#onExecute">onExecute</a></li>
            <li><a href="#reset">reset</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Constructors</h4>
          <section id="new">
            <a name="//apple_ref/cpp/Constructor/new" class="dashAnchor"></a>
            <h5><a href="#new">new</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.action.handler.new(id, group) -&gt; handler</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new handler with the specified ID.</p>
<p>Parameters:</p>
<ul>
<li><code>id</code>      - The unique ID of the action handler.</li>
<li><code>group</code>   - The group the handler belongs to.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The new action handler instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Fields</h4>
          <section id="cached">
            <a name="//apple_ref/cpp/Field/cached" class="dashAnchor"></a>
            <h5><a href="#cached">cached</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.action.handler.cached &lt;cp.prop: boolean&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>If set to <code>true</code> (the default), any choices created will be cached until [reset] is called.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="choices">
            <a name="//apple_ref/cpp/Field/choices" class="dashAnchor"></a>
            <h5><a href="#choices">choices</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.action.handler.choices &lt;cp.prop: cp.choices; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Field</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Provides <code>cp.choices</code> instance for the handler. May be watched/monitored/etc.
The contents of the choices will have a <code>params</code> field, which contains a unique set
of values that identify the choice. This can be passed to the <a href="#execute">execute</a>
method to trigger the choice.</p>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Methods</h4>
          <section id="actionId">
            <a name="//apple_ref/cpp/Method/actionId" class="dashAnchor"></a>
            <h5><a href="#actionId">actionId</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.action.handler:actionId(action) -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a string that can be used as a unique ID for the action details.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="execute">
            <a name="//apple_ref/cpp/Method/execute" class="dashAnchor"></a>
            <h5><a href="#execute">execute</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.action.handler:execute(action) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Executes the action, based on values in the table.</p>
<p>Parameters:</p>
<ul>
<li><code>action</code>      - A table of details about the action.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the execution succeeded.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="group">
            <a name="//apple_ref/cpp/Method/group" class="dashAnchor"></a>
            <h5><a href="#group">group</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.action.handler:group() -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the group for this handler.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>Group as string.</li>
</ul>
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
                <td><code>plugins.core.action.handler:id() -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the ID for this handler.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The ID string.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="onActionId">
            <a name="//apple_ref/cpp/Method/onActionId" class="dashAnchor"></a>
            <h5><a href="#onActionId">onActionId</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.action.handler:onActionId(actionFn) -&gt; handler</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Configures a function to handle converting an action to unique ID.
The function is passed the <code>action</code> table and should return a string.</p>
<p>Parameters:</p>
<ul>
<li><code>actionFn</code>    - The function with a signature of <code>function(action) -&gt; string</code></li>
</ul>
<p>Returns:</p>
<ul>
<li>This action handler.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="onChoices">
            <a name="//apple_ref/cpp/Method/onChoices" class="dashAnchor"></a>
            <h5><a href="#onChoices">onChoices</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.action.handler:onChoices(choicesFn) -&gt; handler</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Adds a callback function which will receive the <code>cp.choices</code> instance to add
choices to. This will only get called when required - the results will be cached
if the <a href="#cached">cached</a> property is set to <code>true</code>.</p>
<p>Parameters:</p>
<ul>
<li><code>choicesFn</code>       - The function with the signature of <code>function(choices) -&gt; nothing</code></li>
</ul>
<p>Returns:</p>
<ul>
<li>This action handler.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="onExecute">
            <a name="//apple_ref/cpp/Method/onExecute" class="dashAnchor"></a>
            <h5><a href="#onExecute">onExecute</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>plugins.core.action.handler:onExecute(executeFn) -&gt; handler</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Configures the function to call when a choice is executed. This will be passed
the choice parameters in a single table.</p>
<p>Parameters:</p>
<ul>
<li><code>executeFn</code>       - The function to call when executing.</li>
</ul>
<p>Returns:</p>
<ul>
<li>This action handler.</li>
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
                <td><code>plugins.core.action.handler:reset([updateNow]) -&gt; nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Resets the handler, clearing any cached result and requesting new ones.</p>
<p>Parameters:</p>
<ul>
<li><code>updateNow</code>   - (optional) If <code>true</code>, the choices will update immediately, otherwise they will update when the choices are next requested.</li>
</ul>
<p>Returns:</p>
<ul>
<li>Nothing</li>
</ul>
</td>
              </tr>
            </table>
          </section>
