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
      <h1><a href="cp.prop.md">docs</a> &raquo; cp.prop</h1>
      <p>This is a utility library for helping keep track of single-value property states. Each property provides access to a single value. Must be readable, but may be read-only. It works by creating a table which has a <code>get</code> and (optionally) a <code>set</code> function which are called when changing the state.</p>
<h2>Features</h2>
<h3>1. Callable</h3>
<p>A <code>prop</code> can be called like a function once created. Eg:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">value</span> <span class="o">=</span> <span class="kc">true</span>
<span class="kd">local</span> <span class="n">propValue</span> <span class="o">=</span> <span class="n">prop</span><span class="p">.</span><span class="n">new</span><span class="p">(</span><span class="kr">function</span><span class="p">()</span> <span class="kr">return</span> <span class="n">value</span> <span class="kr">end</span><span class="p">,</span> <span class="kr">function</span><span class="p">(</span><span class="n">newValue</span><span class="p">)</span> <span class="n">value</span> <span class="o">=</span> <span class="n">newValue</span> <span class="kr">end</span><span class="p">)</span>
<span class="n">propValue</span><span class="p">()</span> <span class="o">==</span> <span class="kc">true</span>     <span class="c1">-- `value` is still true</span>
<span class="n">propValue</span><span class="p">(</span><span class="kc">false</span><span class="p">)</span> <span class="o">==</span> <span class="kc">false</span>   <span class="c1">-- now `value` is false</span>
</pre></div>
<h3>2. Togglable</h3>
<p>A <code>prop</code> comes with toggling built in - as long as the it has a <code>set</code> function. Continuing from the last example:</p>
<div class="highlight"><pre><span></span><span class="n">propValue</span><span class="p">:</span><span class="n">toggle</span><span class="p">()</span>  <span class="c1">-- `value` went from `false` to `true`.</span>
</pre></div>
<p><strong>Note:</strong> Toggling a non-boolean value will flip it to <code>nil</code> and a subsequent toggle will make it <code>true</code>. See the <a href="#toggle">toggle method</a> for more details.</p>
<h3>3. Watchable</h3>
<p>Interested parties can 'watch' the <code>prop</code> value to be notified of changes. Again, continuing on:</p>
<div class="highlight"><pre><span></span><span class="n">propValue</span><span class="p">:</span><span class="n">watch</span><span class="p">(</span><span class="kr">function</span><span class="p">(</span><span class="n">newValue</span><span class="p">)</span> <span class="nb">print</span> <span class="s2">&quot;New Value: &quot;</span><span class="p">...</span><span class="n">newValue</span><span class="p">)</span> <span class="kr">end</span><span class="p">)</span> <span class="c1">-- prints &quot;New Value: true&quot; immediately</span>
<span class="n">propValue</span><span class="p">(</span><span class="kc">false</span><span class="p">)</span>    <span class="c1">-- prints &quot;New Value: false&quot;</span>
</pre></div>
<p>This will also work on <a href="#and">AND</a> and [OR][#or] properties. Any changes from component properties will trigger a notification.</p>
<h3>3. Observable</h3>
<p>Similarly, you can 'observe' a prop as a <code>cp.rx.Observer</code> by calling the <code>observe</code> method:</p>
<div class="highlight"><pre><span></span><span class="n">propValue</span><span class="p">:</span><span class="n">observe</span><span class="p">():</span><span class="n">subscribe</span><span class="p">(</span><span class="kr">function</span><span class="p">(</span><span class="n">value</span><span class="p">)</span> <span class="nb">print</span><span class="p">(</span><span class="nb">tostring</span><span class="p">(</span><span class="n">value</span><span class="p">)</span> <span class="kr">end</span><span class="p">))</span>
</pre></div>
<p>These will never emit an <code>onError</code> or <code>onComplete</code> message, just <code>onNext</code> with either <code>nil</code> or the current value as it changes.</p>
<h3>4. Combinable</h3>
<p>We can combine or modify properties with AND/OR and NOT operations. The resulting values will be a live combination of the underlying <code>prop</code> values. They can also be watched, and will be notified when the underlying <code>prop</code> values change. For example:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">watered</span>   <span class="o">=</span> <span class="n">prop</span><span class="p">.</span><span class="n">TRUE</span><span class="p">()</span>               <span class="c1">-- a simple `prop` which stores the current value internally, defaults to `true`</span>
<span class="kd">local</span> <span class="n">fed</span>       <span class="o">=</span> <span class="n">prop</span><span class="p">.</span><span class="n">FALSE</span><span class="p">()</span>              <span class="c1">-- same as above, defautls to `false`</span>
<span class="kd">local</span> <span class="n">rested</span>    <span class="o">=</span> <span class="n">prop</span><span class="p">.</span><span class="n">FALSE</span><span class="p">()</span>              <span class="c1">-- as above.</span>
<span class="kd">local</span> <span class="n">satisfied</span> <span class="o">=</span> <span class="n">watered</span><span class="p">:</span><span class="n">AND</span><span class="p">(</span><span class="n">fed</span><span class="p">)</span>        <span class="c1">-- will be true if both `watered` and `fed` are true.</span>
<span class="kd">local</span> <span class="n">happy</span>     <span class="o">=</span> <span class="n">satisfied</span><span class="p">:</span><span class="n">AND</span><span class="p">(</span><span class="n">rested</span><span class="p">)</span>   <span class="c1">-- will be true if both `satisfied` and `happy`.</span>
<span class="kd">local</span> <span class="n">sleepy</span>    <span class="o">=</span> <span class="n">fed</span><span class="p">:</span><span class="n">AND</span><span class="p">(</span><span class="n">prop</span><span class="p">.</span><span class="n">NOT</span><span class="p">(</span><span class="n">rested</span><span class="p">))</span> <span class="c1">-- will be sleepy if `fed`, but not `rested`.</span>

<span class="c1">-- These statements all evaluate to `true`</span>
<span class="n">satisfied</span><span class="p">()</span>     <span class="o">==</span> <span class="kc">false</span>
<span class="n">happy</span><span class="p">()</span>         <span class="o">==</span> <span class="kc">false</span>
<span class="n">sleepy</span><span class="p">()</span>        <span class="o">==</span> <span class="kc">false</span>

<span class="c1">-- Get fed</span>
<span class="n">fed</span><span class="p">(</span><span class="kc">true</span><span class="p">)</span>       <span class="o">==</span> <span class="kc">true</span>
<span class="n">satisfied</span><span class="p">()</span>     <span class="o">==</span> <span class="kc">true</span>
<span class="n">happy</span><span class="p">()</span>         <span class="o">==</span> <span class="kc">false</span>
<span class="n">sleepy</span><span class="p">()</span>        <span class="o">==</span> <span class="kc">true</span>

<span class="c1">-- Get rest</span>
<span class="n">rested</span><span class="p">:</span><span class="n">toggle</span><span class="p">()</span> <span class="o">==</span> <span class="kc">true</span>
<span class="n">satisfied</span><span class="p">()</span>     <span class="o">==</span> <span class="kc">true</span>
<span class="n">happy</span><span class="p">()</span>         <span class="o">==</span> <span class="kc">true</span>
<span class="n">sleepy</span><span class="p">()</span>        <span class="o">==</span> <span class="kc">false</span>

<span class="c1">-- These will produce an error, because you can&#39;t modify an AND or OR:</span>
<span class="n">happy</span><span class="p">(</span><span class="kc">true</span><span class="p">)</span>
<span class="n">happy</span><span class="p">:</span><span class="n">toggle</span><span class="p">()</span>
</pre></div>
<p>You can also use non-boolean properties. Any non-<code>nil</code> value is considered to be <code>true</code>.</p>
<h2>5. Immutable</h2>
<p>If appropriate, a <code>prop</code> may be immutable. Any <code>prop</code> with no <code>set</code> function defined is immutable. Examples are the <code>prop.AND</code> and <code>prop.OR</code> instances, since modifying combinations of values doesn't really make sense.</p>
<p>Additionally, an immutable wrapper can be made from any <code>prop</code> value via either <code>prop.IMMUTABLE(...)</code> or calling the <code>myValue:IMMUTABLE()</code> method.</p>
<p>Note that the underlying <code>prop</code> value(s) are still potentially modifiable, and any watchers on the immutable wrapper will be notified of changes. You just can't make any changes directly to the immutable property instance.</p>
<p>For example:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">isImmutable</span> <span class="o">=</span> <span class="n">propValue</span><span class="p">:</span><span class="n">IMMUTABLE</span><span class="p">()</span>
<span class="n">isImmutable</span><span class="p">:</span><span class="n">toggle</span><span class="p">()</span>    <span class="c1">-- results in an `error` being thrown</span>
<span class="n">isImmutable</span><span class="p">:</span><span class="n">watch</span><span class="p">(</span><span class="kr">function</span><span class="p">(</span><span class="n">newValue</span><span class="p">)</span> <span class="nb">print</span> <span class="s2">&quot;isImmutable changed to &quot;</span><span class="o">..</span><span class="n">newValue</span> <span class="kr">end</span><span class="p">)</span>
<span class="n">propValue</span><span class="p">:</span><span class="n">toggle</span><span class="p">()</span>      <span class="c1">-- prints &quot;isImmutable changed to false&quot;</span>
</pre></div>
<h2>6. Bindable</h2>
<p>A property can be bound to an 'owning' table. This table will be passed into the <code>get</code> and <code>set</code> functions for the property if present. This is mostly useful if your property depends on internal instance values of a table. For example, you might want to make a property work as a method instead of a function:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">owner</span> <span class="o">=</span> <span class="p">{</span>
   <span class="n">_value</span> <span class="o">=</span> <span class="kc">true</span>
<span class="p">}</span>
<span class="n">owner</span><span class="p">.</span><span class="n">value</span> <span class="o">=</span> <span class="n">prop</span><span class="p">(</span><span class="kr">function</span><span class="p">()</span> <span class="kr">return</span> <span class="n">owner</span><span class="p">.</span><span class="n">_value</span> <span class="kr">end</span><span class="p">)</span>
<span class="n">owner</span><span class="p">:</span><span class="n">isMethod</span><span class="p">()</span> <span class="c1">-- error!</span>
</pre></div>
<p>To use a <code>prop</code> as a method, you need to <code>attach</code> it to the owning table, like so:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">owner</span> <span class="o">=</span> <span class="p">{</span>
    <span class="n">_value</span> <span class="o">=</span> <span class="kc">true</span>
<span class="p">}</span>
<span class="n">owner</span><span class="p">.</span><span class="n">isMethod</span> <span class="o">=</span> <span class="n">prop</span><span class="p">(</span><span class="kr">function</span><span class="p">(</span><span class="n">self</span><span class="p">)</span> <span class="kr">return</span> <span class="n">self</span><span class="p">.</span><span class="n">_value</span> <span class="kr">end</span><span class="p">,</span> <span class="kr">function</span><span class="p">(</span><span class="n">value</span><span class="p">,</span> <span class="n">self</span><span class="p">)</span> <span class="n">self</span><span class="p">.</span><span class="n">_value</span> <span class="o">=</span> <span class="n">value</span> <span class="kr">end</span><span class="p">):</span><span class="n">bind</span><span class="p">(</span><span class="n">owner</span><span class="p">)</span>
<span class="n">owner</span><span class="p">:</span><span class="n">isMethod</span><span class="p">()</span>                <span class="c1">-- success!</span>
<span class="n">owner</span><span class="p">.</span><span class="n">isMethod</span><span class="p">()</span>                <span class="c1">-- also works - will still pass in the bound owner.</span>
<span class="n">owner</span><span class="p">.</span><span class="n">isMethod</span><span class="p">:</span><span class="n">owner</span><span class="p">()</span> <span class="o">==</span> <span class="n">owner</span> <span class="c1">-- is true~</span>
</pre></div>
<p>The bound <code>owner</code> is passed in as the last parameter of the <code>get</code> and <code>set</code> functions.</p>
<h2>7. Extendable</h2>
<p>A common use case is using metatables to provide shared fields and methods across multiple instances. A typical example might be:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">person</span> <span class="o">=</span> <span class="p">{}</span>
<span class="kr">function</span> <span class="nc">person</span><span class="p">:</span><span class="nf">name</span><span class="p">(</span><span class="n">newValue</span><span class="p">)</span>
    <span class="kr">if</span> <span class="n">newValue</span> <span class="kr">then</span>
        <span class="n">self</span><span class="p">.</span><span class="n">_name</span> <span class="o">=</span> <span class="n">newValue</span>
    <span class="kr">end</span>
    <span class="kr">return</span> <span class="n">self</span><span class="p">.</span><span class="n">_name</span>
<span class="kr">end</span>

<span class="kr">function</span> <span class="nc">person</span><span class="p">.</span><span class="nf">new</span><span class="p">(</span><span class="n">name</span><span class="p">)</span>
    <span class="kd">local</span> <span class="n">o</span> <span class="o">=</span> <span class="p">{</span> <span class="n">_name</span> <span class="o">=</span> <span class="n">name</span> <span class="p">}</span>
    <span class="kr">return</span> <span class="nb">setmetatable</span><span class="p">(</span><span class="n">o</span><span class="p">,</span> <span class="p">{</span> <span class="n">__index</span> <span class="o">=</span> <span class="n">person</span> <span class="p">})</span>
<span class="kr">end</span>

<span class="kd">local</span> <span class="n">johnDoe</span> <span class="o">=</span> <span class="n">person</span><span class="p">.</span><span class="n">new</span><span class="p">(</span><span class="s2">&quot;John Doe&quot;</span><span class="p">)</span>
<span class="n">johnDoe</span><span class="p">:</span><span class="n">name</span><span class="p">()</span> <span class="o">==</span> <span class="s2">&quot;John Doe&quot;</span>
</pre></div>
<p>If we want to make the <code>name</code> a property, we might try creating a bound property like this:</p>
<div class="highlight"><pre><span></span><span class="n">person</span><span class="p">.</span><span class="n">name</span> <span class="o">=</span> <span class="n">prop</span><span class="p">(</span><span class="kr">function</span><span class="p">(</span><span class="n">self</span><span class="p">)</span> <span class="kr">return</span> <span class="n">self</span><span class="p">.</span><span class="n">_name</span> <span class="kr">end</span><span class="p">,</span> <span class="kr">function</span><span class="p">(</span><span class="n">value</span><span class="p">,</span> <span class="n">self</span><span class="p">)</span> <span class="n">self</span><span class="p">.</span><span class="n">_name</span> <span class="o">=</span> <span class="n">value</span> <span class="kr">end</span><span class="p">):</span><span class="n">bind</span><span class="p">(</span><span class="n">person</span><span class="p">)</span>
</pre></div>
<p>Unfortunately, this doesn't work as expected:</p>
<div class="highlight"><pre><span></span><span class="n">johnDoe</span><span class="p">:</span><span class="n">name</span><span class="p">()</span>          <span class="c1">-- Throws an error because `person` is the owner, not `johnDoe`.</span>
<span class="n">johnDoe</span><span class="p">.</span><span class="n">name</span><span class="p">()</span> <span class="o">==</span> <span class="kc">nil</span>   <span class="c1">-- Works, but will return `nil` because &quot;John Doe&quot; is applied to the new table, not `person`</span>
</pre></div>
<p>The fix is to use <code>prop.extend</code> when creating the new person. Rewrite <code>person.new</code> like so:</p>
<div class="highlight"><pre><span></span><span class="n">person</span><span class="p">.</span><span class="n">new</span><span class="p">(</span><span class="n">name</span><span class="p">)</span>
    <span class="kd">local</span> <span class="n">o</span> <span class="o">=</span> <span class="p">{</span> <span class="n">_name</span> <span class="o">=</span> <span class="n">name</span> <span class="p">}</span>
    <span class="kr">return</span> <span class="n">prop</span><span class="p">.</span><span class="n">extend</span><span class="p">(</span><span class="n">o</span><span class="p">,</span> <span class="n">person</span><span class="p">)</span>
<span class="kr">end</span>
</pre></div>
<p>Now, this will work as expected:</p>
<div class="highlight"><pre><span></span><span class="n">johnDoe</span><span class="p">:</span><span class="n">name</span><span class="p">()</span> <span class="o">==</span> <span class="s2">&quot;John Doe&quot;</span>
<span class="n">johnDoe</span><span class="p">.</span><span class="n">name</span><span class="p">()</span> <span class="o">==</span> <span class="s2">&quot;John Doe&quot;</span>
</pre></div>
<p>The <code>prop.extend</code> function will set the <code>source</code> table as a metatable of the <code>target</code>, as well as binding any bound props that are in the <code>source</code> to <code>target</code>.</p>
<h1>Tables</h1>
<p>Because tables are copied by reference rather than by value, changes made inside a table will not necessarily trigger an update when setting a value with an updated table value. By default, tables are simply passed in and out without modification. You can nominate for a property to make copies of tables (not userdata) when getting or setting, which effectively isolates the value being stored from outside modification. This can be done with the <a href="#deepTable">deepTable</a> and<a href="#shallowTable">shallowTable</a> methods. Below is an example of them in action:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">value</span> <span class="o">=</span> <span class="p">{</span> <span class="n">a</span> <span class="o">=</span> <span class="mi">1</span><span class="p">,</span> <span class="n">b</span> <span class="o">=</span> <span class="p">{</span> <span class="n">c</span> <span class="o">=</span> <span class="mi">1</span> <span class="p">}</span> <span class="p">}</span>
<span class="kd">local</span> <span class="n">valueProp</span> <span class="o">=</span> <span class="n">prop</span><span class="p">.</span><span class="n">THIS</span><span class="p">(</span><span class="n">value</span><span class="p">)</span>
<span class="kd">local</span> <span class="n">deepProp</span> <span class="o">=</span> <span class="n">prop</span><span class="p">.</span><span class="n">THIS</span><span class="p">(</span><span class="n">value</span><span class="p">):</span><span class="n">deepTable</span><span class="p">()</span>
<span class="kd">local</span> <span class="n">shallowProp</span> <span class="o">=</span> <span class="n">prop</span><span class="p">.</span><span class="n">THIS</span><span class="p">(</span><span class="n">value</span><span class="p">):</span><span class="n">shallowTable</span><span class="p">()</span>

<span class="c1">-- print a message when the prop value is updated</span>
<span class="n">valueProp</span><span class="p">:</span><span class="n">watch</span><span class="p">(</span><span class="kr">function</span><span class="p">(</span><span class="n">v</span><span class="p">)</span> <span class="nb">print</span><span class="p">(</span><span class="s2">&quot;value: a = &quot;</span> <span class="o">..</span> <span class="n">v</span><span class="p">.</span><span class="n">a</span> <span class="o">..</span><span class="s2">&quot;, b.c = &quot;</span><span class="o">..</span> <span class="n">v</span><span class="p">.</span><span class="n">b</span><span class="p">.</span><span class="n">c</span> <span class="p">)</span> <span class="kr">end</span><span class="p">)</span>
<span class="n">deepProp</span><span class="p">:</span><span class="n">watch</span><span class="p">(</span><span class="kr">function</span><span class="p">(</span><span class="n">v</span><span class="p">)</span> <span class="nb">print</span><span class="p">(</span><span class="s2">&quot;deep: a = &quot;</span> <span class="o">..</span> <span class="n">v</span><span class="p">.</span><span class="n">a</span> <span class="o">..</span><span class="s2">&quot;, b.c = &quot;</span><span class="o">..</span> <span class="n">v</span><span class="p">.</span><span class="n">b</span><span class="p">.</span><span class="n">c</span> <span class="p">)</span> <span class="kr">end</span><span class="p">)</span>
<span class="n">shallowProp</span><span class="p">:</span><span class="n">watch</span><span class="p">(</span><span class="kr">function</span><span class="p">(</span><span class="n">v</span><span class="p">)</span> <span class="nb">print</span><span class="p">(</span><span class="s2">&quot;shallow: a = &quot;</span> <span class="o">..</span> <span class="n">v</span><span class="p">.</span><span class="n">a</span> <span class="o">..</span><span class="s2">&quot;, b.c = &quot;</span><span class="o">..</span> <span class="n">v</span><span class="p">.</span><span class="n">b</span><span class="p">.</span><span class="n">c</span> <span class="p">)</span> <span class="kr">end</span><span class="p">)</span>

<span class="c1">-- change the original table:</span>
<span class="n">value</span><span class="p">.</span><span class="n">a</span>             <span class="o">=</span> <span class="mi">2</span>
<span class="n">value</span><span class="p">.</span><span class="n">b</span><span class="p">.</span><span class="n">c</span>           <span class="o">=</span> <span class="mi">2</span>

<span class="n">valueProp</span><span class="p">().</span><span class="n">a</span>       <span class="o">==</span> <span class="mi">2</span>    <span class="c1">-- modified</span>
<span class="n">valueProp</span><span class="p">().</span><span class="n">b</span><span class="p">.</span><span class="n">c</span>     <span class="o">==</span> <span class="mi">2</span>    <span class="c1">-- modified</span>
<span class="n">shallowProp</span><span class="p">().</span><span class="n">a</span>     <span class="o">==</span> <span class="mi">1</span>    <span class="c1">-- top level is copied</span>
<span class="n">shallowProp</span><span class="p">().</span><span class="n">b</span><span class="p">.</span><span class="n">c</span>   <span class="o">==</span> <span class="mi">2</span>    <span class="c1">-- child tables are referenced</span>
<span class="n">deepProp</span><span class="p">().</span><span class="n">a</span>        <span class="o">==</span> <span class="mi">1</span>    <span class="c1">-- top level is copied</span>
<span class="n">deepProp</span><span class="p">().</span><span class="n">b</span><span class="p">.</span><span class="n">c</span>      <span class="o">==</span> <span class="mi">1</span>    <span class="c1">-- child tables are copied as well</span>

<span class="c1">-- get the &#39;value&#39; property</span>
<span class="n">value</span> <span class="o">=</span> <span class="n">valueProp</span><span class="p">()</span>         <span class="c1">-- returns the original value table</span>

<span class="n">value</span><span class="p">.</span><span class="n">a</span>             <span class="o">=</span> <span class="mi">3</span>     <span class="c1">-- updates the original value table `a` value</span>
<span class="n">value</span><span class="p">.</span><span class="n">b</span><span class="p">.</span><span class="n">c</span>           <span class="o">=</span> <span class="mi">3</span>     <span class="c1">-- updates the original `b` table&#39;s `c` value</span>

<span class="n">valueProp</span><span class="p">(</span><span class="n">value</span><span class="p">)</span>            <span class="c1">-- nothing is printed, since it&#39;s still the same table</span>

<span class="n">valueProp</span><span class="p">().</span><span class="n">a</span>       <span class="o">==</span> <span class="mi">3</span>    <span class="c1">-- still referencing the original table</span>
<span class="n">valueProp</span><span class="p">().</span><span class="n">b</span><span class="p">.</span><span class="n">c</span>     <span class="o">==</span> <span class="mi">3</span>    <span class="c1">-- the child is still referenced too</span>
<span class="n">shallowProp</span><span class="p">().</span><span class="n">a</span>     <span class="o">==</span> <span class="mi">1</span>    <span class="c1">-- still unmodified after the initial copy</span>
<span class="n">shallowProp</span><span class="p">().</span><span class="n">b</span><span class="p">.</span><span class="n">c</span>   <span class="o">==</span> <span class="mi">3</span>    <span class="c1">-- still updated, since `b` was copied by reference</span>
<span class="n">deepProp</span><span class="p">().</span><span class="n">a</span>        <span class="o">==</span> <span class="mi">1</span>    <span class="c1">-- still unmodified after initial copy</span>
<span class="n">deepProp</span><span class="p">().</span><span class="n">b</span><span class="p">.</span><span class="n">c</span>      <span class="o">==</span> <span class="mi">1</span>    <span class="c1">-- still unmodified after initial copy</span>

<span class="c1">-- get the &#39;deep copy&#39; property</span>
<span class="n">value</span> <span class="o">=</span> <span class="n">deepProp</span><span class="p">()</span>          <span class="c1">-- returns a new table, with all child tables also copied.</span>

<span class="n">value</span><span class="p">.</span><span class="n">a</span>             <span class="o">=</span> <span class="mi">4</span>     <span class="c1">-- updates the new table&#39;s `a` value</span>
<span class="n">value</span><span class="p">.</span><span class="n">b</span><span class="p">.</span><span class="n">c</span>           <span class="o">=</span> <span class="mi">4</span>     <span class="c1">-- updates the new `b` table&#39;s `c` value</span>

<span class="n">deepProp</span><span class="p">(</span><span class="n">value</span><span class="p">)</span>             <span class="c1">-- prints &quot;deep: a = 4, b.c = 4&quot;</span>

<span class="n">valueProp</span><span class="p">().</span><span class="n">a</span>       <span class="o">==</span> <span class="mi">3</span>    <span class="c1">-- still referencing the original table</span>
<span class="n">valueProp</span><span class="p">().</span><span class="n">b</span><span class="p">.</span><span class="n">c</span>     <span class="o">==</span> <span class="mi">3</span>    <span class="c1">-- the child is still referenced too</span>
<span class="n">shallowProp</span><span class="p">().</span><span class="n">a</span>     <span class="o">==</span> <span class="mi">1</span>    <span class="c1">-- still unmodified after the initial copy</span>
<span class="n">shallowProp</span><span class="p">().</span><span class="n">b</span><span class="p">.</span><span class="n">c</span>   <span class="o">==</span> <span class="mi">3</span>    <span class="c1">-- still referencing the original `b` table.</span>
<span class="n">deepProp</span><span class="p">().</span><span class="n">a</span>        <span class="o">==</span> <span class="mi">4</span>    <span class="c1">-- updated to the new value</span>
<span class="n">deepProp</span><span class="p">().</span><span class="n">b</span><span class="p">.</span><span class="n">c</span>      <span class="o">==</span> <span class="mi">4</span>    <span class="c1">-- updated to the new value</span>

<span class="c1">-- get the &#39;shallow&#39; property</span>
<span class="n">value</span> <span class="o">=</span> <span class="n">shallowProp</span><span class="p">()</span>       <span class="c1">-- returns a new table with top-level keys copied.</span>

<span class="n">value</span><span class="p">.</span><span class="n">a</span>             <span class="o">=</span> <span class="mi">5</span>     <span class="c1">-- updates the new table&#39;s `a` value</span>
<span class="n">value</span><span class="p">.</span><span class="n">b</span><span class="p">.</span><span class="n">c</span>           <span class="o">=</span> <span class="mi">5</span>     <span class="c1">-- updates the original `b` table&#39;s `c` value.</span>

<span class="n">shallowProp</span><span class="p">(</span><span class="n">value</span><span class="p">)</span>          <span class="c1">-- prints &quot;shallow: a = 5, b.c = 5&quot;</span>

<span class="n">valueProp</span><span class="p">().</span><span class="n">a</span>       <span class="o">==</span> <span class="mi">3</span>    <span class="c1">-- still referencing the original table</span>
<span class="n">valueProp</span><span class="p">().</span><span class="n">b</span><span class="p">.</span><span class="n">c</span>     <span class="o">==</span> <span class="mi">5</span>    <span class="c1">-- still referencing the original `b` table</span>
<span class="n">shallowProp</span><span class="p">().</span><span class="n">a</span>     <span class="o">==</span> <span class="mi">5</span>    <span class="c1">-- updated to the new value</span>
<span class="n">shallowProp</span><span class="p">().</span><span class="n">b</span><span class="p">.</span><span class="n">c</span>   <span class="o">==</span> <span class="mi">5</span>    <span class="c1">-- referencing the original `b` table, which was updated</span>
<span class="n">deepProp</span><span class="p">().</span><span class="n">a</span>        <span class="o">==</span> <span class="mi">4</span>    <span class="c1">-- unmodified after the last update</span>
<span class="n">deepProp</span><span class="p">().</span><span class="n">b</span><span class="p">.</span><span class="n">c</span>      <span class="o">==</span> <span class="mi">4</span>    <span class="c1">-- unmodified after the last update</span>
</pre></div>
<p>So, a little bit tricky. The general rule of thumb is:</p>
<ol>
<li>If working with immutable objects, use the default 'value' value copy, which preserves the original.</li>
<li>If working with an array of immutible objects, use the 'shallow' table copy.</li>
<li>In most other cases, use a 'deep' table copy.</li>
</ol>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Constants - Useful values which cannot be changed</li>
          <ul>
            <li><a href="#NIL">NIL</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#AND">AND</a></li>
            <li><a href="#bind">bind</a></li>
            <li><a href="#extend">extend</a></li>
            <li><a href="#FALSE">FALSE</a></li>
            <li><a href="#IMMUTABLE">IMMUTABLE</a></li>
            <li><a href="#is">is</a></li>
            <li><a href="#NOT">NOT</a></li>
            <li><a href="#OR">OR</a></li>
            <li><a href="#THIS">THIS</a></li>
            <li><a href="#TRUE">TRUE</a></li>
          </ul>
        <li>Constructors - API calls which return an object, typically one that offers API methods</li>
          <ul>
            <li><a href="#new">new</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#ABOVE">ABOVE</a></li>
            <li><a href="#AND">AND</a></li>
            <li><a href="#ATLEAST">ATLEAST</a></li>
            <li><a href="#ATMOST">ATMOST</a></li>
            <li><a href="#BELOW">BELOW</a></li>
            <li><a href="#bind">bind</a></li>
            <li><a href="#cached">cached</a></li>
            <li><a href="#clear">clear</a></li>
            <li><a href="#clone">clone</a></li>
            <li><a href="#deepTable">deepTable</a></li>
            <li><a href="#EQ">EQ</a></li>
            <li><a href="#get">get</a></li>
            <li><a href="#hasWatchers">hasWatchers</a></li>
            <li><a href="#id">id</a></li>
            <li><a href="#IMMUTABLE">IMMUTABLE</a></li>
            <li><a href="#IS">IS</a></li>
            <li><a href="#ISNOT">ISNOT</a></li>
            <li><a href="#label">label</a></li>
            <li><a href="#mirror">mirror</a></li>
            <li><a href="#monitor">monitor</a></li>
            <li><a href="#mutable">mutable</a></li>
            <li><a href="#mutate">mutate</a></li>
            <li><a href="#NEQ">NEQ</a></li>
            <li><a href="#NOT">NOT</a></li>
            <li><a href="#observe">observe</a></li>
            <li><a href="#OR">OR</a></li>
            <li><a href="#owner">owner</a></li>
            <li><a href="#preWatch">preWatch</a></li>
            <li><a href="#set">set</a></li>
            <li><a href="#shallowTable">shallowTable</a></li>
            <li><a href="#toggle">toggle</a></li>
            <li><a href="#unwatch">unwatch</a></li>
            <li><a href="#update">update</a></li>
            <li><a href="#value">value</a></li>
            <li><a href="#watch">watch</a></li>
            <li><a href="#wrap">wrap</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Constants</h4>
          <section id="NIL">
            <a name="//apple_ref/cpp/Constant/NIL" class="dashAnchor"></a>
            <h5><a href="#NIL">NIL</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop.NIL -&gt; cp.prop</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a <code>cp.prop</code> which will always be <code>nil</code>.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>a new <code>cp.prop</code> instance with a value of <code>nil</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Functions</h4>
          <section id="AND">
            <a name="//apple_ref/cpp/Function/AND" class="dashAnchor"></a>
            <h5><a href="#AND">AND</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop.AND(...) -&gt; cp.prop</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a new <code>cp.prop</code> which will be <code>true</code> if all <code>cp.prop</code> instances passed into the function return a <code>truthy</code> value.</p>
<p>Parameters:</p>
<ul>
<li><code>...</code>        - The list of <code>cp.prop</code> instances to 'AND' together.</li>
</ul>
<p>Returns:</p>
<ul>
<li>a <code>cp.prop</code> instance.</li>
</ul>
<p>Notes:</p>
<ul>
<li>The value of this instance will resolve by lazily checking the <code>value</code> of the contained <code>cp.prop</code> instances in the order provided. The first <code>falsy</code> value will be returned. Otherwise the last <code>truthy</code> value is returned.</li>
<li>The instance is <strong>immutable</strong>.</li>
<li>Once you have created an 'AND', you cannot 'OR' as a method. Eg, this will fail: <code>prop.TRUE():AND(prop:FALSE()):OR(prop.TRUE())</code>. This is to avoid ambiguity as to whether the 'AND' or 'OR' takes precedence. Is it <code>(true and false) or true</code> or <code>true and (false or true)</code>?.</li>
<li>To combine 'AND' and 'OR' values, group them together when combining. Eg:
<strong> <code>(true and false) or true</code>: <code>prop.OR( prop.TRUE():AND(prop.FALSE()), prop.TRUE() )</code></strong> <code>true and (false or true)</code>: <code>prop.TRUE():AND( prop.FALSE():OR(prop.TRUE()) )</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="bind">
            <a name="//apple_ref/cpp/Function/bind" class="dashAnchor"></a>
            <h5><a href="#bind">bind</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop.bind(owner[, relaxed]) -&gt; function</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>This provides a utility function for binding multiple properties to a single owner in
a simple way. To use, do something like this:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">o</span> <span class="o">=</span> <span class="p">{}</span>
<span class="n">prop</span><span class="p">.</span><span class="n">bind</span><span class="p">(</span><span class="n">o</span><span class="p">)</span> <span class="p">{</span>
    <span class="n">foo</span> <span class="o">=</span> <span class="n">prop</span><span class="p">.</span><span class="n">TRUE</span><span class="p">(),</span>
    <span class="n">bar</span> <span class="o">=</span> <span class="n">prop</span><span class="p">.</span><span class="n">THIS</span><span class="p">(</span><span class="s2">&quot;Hello world&quot;</span><span class="p">),</span>
<span class="p">}</span>
</pre></div>
<p>This is equivalent to the following:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">o</span> <span class="o">=</span> <span class="p">{}</span>
<span class="n">o</span><span class="p">.</span><span class="n">foo</span> <span class="o">=</span> <span class="n">prop</span><span class="p">.</span><span class="n">TRUE</span><span class="p">():</span><span class="n">bind</span><span class="p">(</span><span class="n">o</span><span class="p">):</span><span class="n">label</span><span class="p">(</span><span class="s2">&quot;foo&quot;</span><span class="p">)</span>
<span class="c1">-- alternately...</span>
<span class="n">prop</span><span class="p">.</span><span class="n">THIS</span><span class="p">(</span><span class="s2">&quot;Hello world&quot;</span><span class="p">):</span><span class="n">bind</span><span class="p">(</span><span class="n">o</span><span class="p">,</span> <span class="s2">&quot;bar&quot;</span><span class="p">)</span>
</pre></div>
<p>It has the added benefit of checking that the target properties ('foo' and 'bar' in this case)
have not already been assigned a value.</p>
<p>Parameters:</p>
<ul>
<li>owner     - The owner table to bind the properties to.</li>
<li>relaxed   - If <code>true</code>, then non-<code>cp.prop</code> fields will be ignored. Otherwise they generate an error.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A function which should be called, passing in a table of key/value pairs which are <code>string</code>/<code>cp.prop</code> value.</li>
</ul>
<p>Notes:</p>
<ul>
<li>If you are binding multiple <code>cp.prop</code> values that are dependent on other <code>cp.prop</code> values on the same owner (e.g. via <code>mutate</code> or a boolean join), you
will have to break it up into multiple <code>prop.bind(...) {...}</code> calls, so that the dependent property can access the bound property.</li>
<li>If a <code>cp.prop</code> provided as bindings already has a bound owner, it will be wrapped instead of bound directly.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="extend">
            <a name="//apple_ref/cpp/Function/extend" class="dashAnchor"></a>
            <h5><a href="#extend">extend</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop.extend(target, source) -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Makes the <code>target</code> extend the <code>source</code>. It will copy all bound properties on the source table into the target, rebinding it to the target table. Other keys are inherited via the metatable.</p>
<p>Parameters:</p>
<ul>
<li><code>target</code> - The target to extend</li>
<li><code>source</code> - The source to extend from</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>target</code>, now extending the <code>source</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="FALSE">
            <a name="//apple_ref/cpp/Function/FALSE" class="dashAnchor"></a>
            <h5><a href="#FALSE">FALSE</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop.FALSE() -&gt; cp.prop</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a new <code>cp.prop</code> which will cache internally, initially set to <code>false</code>.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>a <code>cp.prop</code> instance defaulting to <code>false</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="IMMUTABLE">
            <a name="//apple_ref/cpp/Function/IMMUTABLE" class="dashAnchor"></a>
            <h5><a href="#IMMUTABLE">IMMUTABLE</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop.IMMUTABLE(propValue) -- cp.prop</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a new <code>cp.prop</code> instance which will not allow the wrapped value to be modified.</p>
<p>Parameters:</p>
<ul>
<li><code>propValue</code>      - The <code>cp.prop</code> value to wrap.</li>
</ul>
<p>Returns:</p>
<ul>
<li>a new <code>cp.prop</code> instance which cannot be modified.</li>
</ul>
<p>Note:</p>
<ul>
<li>The original <code>propValue</code> can still be modified (if appropriate) and watchers of the immutable value will be notified when it changes.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="is">
            <a name="//apple_ref/cpp/Function/is" class="dashAnchor"></a>
            <h5><a href="#is">is</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop.is(value) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks if the <code>value</code> is an instance of a <code>cp.prop</code>.</p>
<p>Parameters:</p>
<ul>
<li><code>value</code>  - The value to check.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the value is an instance of <code>cp.prop</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="NOT">
            <a name="//apple_ref/cpp/Function/NOT" class="dashAnchor"></a>
            <h5><a href="#NOT">NOT</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop.NOT(propValue) -&gt; cp.prop</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a new <code>cp.prop</code> which negates the provided <code>propValue</code>. Values are negated as follows:</p>
<ul>
<li><code>boolean</code>    - Switch between <code>true</code> and <code>false</code></li>
<li><code>nil</code>        - Switches to <code>true</code></li>
<li><other>  - Switches to <code>nil</code>.</li>
</ul>
<p>Parameters:</p>
<ul>
<li><code>propValue</code>      - Another <code>cp.prop</code> instance.</li>
</ul>
<p>Returns:</p>
<ul>
<li>a <code>cp.prop</code> instance negating the <code>propValue</code>.</li>
</ul>
<p>Notes:</p>
<ul>
<li>If the <code>propValue</code> is mutable, you can set the <code>NOT</code> property value and the underlying value will be set to the negated value. Be aware that the same negation rules apply when setting as when getting.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="OR">
            <a name="//apple_ref/cpp/Function/OR" class="dashAnchor"></a>
            <h5><a href="#OR">OR</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop.OR(...) -&gt; cp.prop</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a new <code>cp.prop</code> which will return the first 'truthy' value provided by one of the provided properties. Otherwise, returns the last 'falsy' value.</p>
<p>Parameters:</p>
<ul>
<li><code>...</code>        - The list of <code>cp.prop</code> instances to 'OR' together.</li>
</ul>
<p>Returns:</p>
<ul>
<li>a <code>cp.prop</code> instance.</li>
</ul>
<p>Notes:</p>
<ul>
<li>The value of this instance will resolve by lazily checking the <code>value</code> of the contained <code>cp.prop</code> instances in the order provided. If any return <code>true</code>, no further instances will be checked.</li>
<li>The instance is immutable, since there is no realy way to flip the component values of an 'OR' in a way that makes sense.</li>
<li>Once you have created an 'OR', you cannot 'AND' as a method. Eg, this will fail: <code>prop.TRUE():OR(prop:FALSE()):AND(prop.TRUE())</code>. This is to avoid ambiguity as to whether the 'OR' or 'AND' takes precedence. Is it <code>(true or false) and true</code> or <code>true or (false and true)</code>?.</li>
<li>To combine 'AND' and 'OR' values, group them together when combining. Eg:
<strong> <code>(true or false) and true</code>: <code>prop.AND( prop.TRUE():OR(prop.FALSE()), prop.TRUE() )</code></strong> <code>true or (false and true)</code>: <code>prop.TRUE():OR( prop.FALSE():AND(prop.TRUE()) )</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="THIS">
            <a name="//apple_ref/cpp/Function/THIS" class="dashAnchor"></a>
            <h5><a href="#THIS">THIS</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop.THIS([initialValue]) -&gt; cp.prop</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a new <code>cp.prop</code> instance which will cache a value internally. It will default to the value of the <code>initialValue</code>, if provided.</p>
<p>Parameters:</p>
<ul>
<li><code>initialValue</code>   - The initial value to set it to (optional).</li>
</ul>
<p>Returns:</p>
<ul>
<li>a new <code>cp.prop</code> instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="TRUE">
            <a name="//apple_ref/cpp/Function/TRUE" class="dashAnchor"></a>
            <h5><a href="#TRUE">TRUE</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop.TRUE() -&gt; cp.prop</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a new <code>cp.prop</code> which will cache internally, initially set to <code>true</code>.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>a <code>cp.prop</code> instance defaulting to <code>true</code>.</li>
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
                <td><code>cp.prop.new(getFn, setFn, cloneFn) --&gt; cp.prop</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new <code>prop</code> value, with the provided <code>get</code> and <code>set</code> functions.</p>
<p>Parameters:</p>
<ul>
<li><code>getFn</code>      - The function that will get called to retrieve the current value.</li>
<li><code>setFn</code>      - (optional) The function that will get called to set the new value.</li>
<li><code>cloneFn</code>        - (optional) The function that will get called when cloning the property.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The new <code>cp.prop</code> instance.</li>
</ul>
<p>Notes:</p>
<ul>
<li><code>getFn</code> signature: <code>function([owner]) -&gt; anything</code>
** <code>owner</code>     - If this is attached as a method, the owner table is passed in.</li>
<li><code>setFn</code> signature: <code>function(newValue[, owner])</code>
<strong> <code>newValue</code>  - The new value to store.</strong> <code>owner</code>     - If this is attached as a method, the owner table is passed in.</li>
<li><code>cloneFn</code> signature: <code>function(prop) -&gt; new cp.prop</code></li>
<li>This can also be executed by calling the module directly. E.g. <code>require('cp.prop')(myGetFunction)</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Methods</h4>
          <section id="ABOVE">
            <a name="//apple_ref/cpp/Method/ABOVE" class="dashAnchor"></a>
            <h5><a href="#ABOVE">ABOVE</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop:ABOVE() -&gt; cp.prop &lt;boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a new property comparing this property to <code>something</code>.</p>
<p>Parameters:</p>
<ul>
<li><code>something</code>  - A value, a function or a <code>cp.prop</code> to compare to.</li>
</ul>
<p>Returns:</p>
<ul>
<li>New, read-only <code>cp.prop</code> which will be <code>true</code> if this property is greater than <code>something</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="AND">
            <a name="//apple_ref/cpp/Method/AND" class="dashAnchor"></a>
            <h5><a href="#AND">AND</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop:AND(...) -&gt; cp.prop</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a new <code>cp.prop</code> which will be <code>true</code> if this and all other <code>cp.prop</code> instances passed into the function return <code>true</code>.</p>
<p>Parameters:</p>
<ul>
<li><code>...</code>        - The list of <code>cp.prop</code> instances to 'AND' together.</li>
</ul>
<p>Returns:</p>
<ul>
<li>a <code>cp.prop</code> instance.</li>
</ul>
<p>Notes:</p>
<ul>
<li>See the <a href="#and">AND Function</a> for more details</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="ATLEAST">
            <a name="//apple_ref/cpp/Method/ATLEAST" class="dashAnchor"></a>
            <h5><a href="#ATLEAST">ATLEAST</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop:ATLEAST() -&gt; cp.prop &lt;boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a new property comparing this property to <code>something</code>.</p>
<p>Parameters:</p>
<ul>
<li><code>something</code>  - A value, a function or a <code>cp.prop</code> to compare to.</li>
</ul>
<p>Returns:</p>
<ul>
<li>New, read-only <code>cp.prop</code> which will be <code>true</code> if this property is less than or equal to <code>something</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="ATMOST">
            <a name="//apple_ref/cpp/Method/ATMOST" class="dashAnchor"></a>
            <h5><a href="#ATMOST">ATMOST</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop:ATMOST() -&gt; cp.prop &lt;boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a new property comparing this property to <code>something</code>.</p>
<p>Parameters:</p>
<ul>
<li><code>something</code>  - A value, a function or a <code>cp.prop</code> to compare to.</li>
</ul>
<p>Returns:</p>
<ul>
<li>New, read-only <code>cp.prop</code> which will be <code>true</code> if this property is less than or equal to <code>something</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="BELOW">
            <a name="//apple_ref/cpp/Method/BELOW" class="dashAnchor"></a>
            <h5><a href="#BELOW">BELOW</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop:BELOW() -&gt; cp.prop &lt;boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a new property comparing this property to <code>something</code>.</p>
<p>Parameters:</p>
<ul>
<li><code>something</code>  - A value, a function or a <code>cp.prop</code> to compare to.</li>
</ul>
<p>Returns:</p>
<ul>
<li>New, read-only <code>cp.prop</code> which will be <code>true</code> if this property is less than <code>something</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="bind">
            <a name="//apple_ref/cpp/Method/bind" class="dashAnchor"></a>
            <h5><a href="#bind">bind</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop:bind(owner, [key]) -&gt; cp.prop</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Binds the property to the specified owner. Once bound, it cannot be changed.
Optionally, a key can be provided which will assign the <code>cp.prop</code> to the owner using that key.
If the <code>cp.prop</code> does not have a label, the key will be used as the label.</p>
<p>Parameters:</p>
<ul>
<li><code>owner</code>  - The owner to attach to.</li>
<li><code>key</code>    - If provided, the property will be bound to the specified key.</li>
</ul>
<p>Returns:</p>
<ul>
<li>the <code>cp.prop</code></li>
</ul>
<p>Notes:</p>
<ul>
<li>Throws an <code>error</code> if the new owner is <code>nil</code>.</li>
<li>Throws an <code>error</code> if the owner already has a property with the name provided in <code>key</code>.</li>
<li>Throws an <code>error</code> if the <code>key</code> is not a string value.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="cached">
            <a name="//apple_ref/cpp/Method/cached" class="dashAnchor"></a>
            <h5><a href="#cached">cached</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop:cached() -&gt; prop</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>This can be called once to enable caching of the result inside the <code>prop</code>.
This can help with performance, but if there are other ways of modifying
the original value outside the prop, it will potentially return stale values.</p>
<p>You can force a reload via the <a href="#update">update</a> method.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.prop</code> instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="clear">
            <a name="//apple_ref/cpp/Method/clear" class="dashAnchor"></a>
            <h5><a href="#clear">clear</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop:clear() -&gt; nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Clears the property. Watchers will be notified if the value has changed.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>nil</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="clone">
            <a name="//apple_ref/cpp/Method/clone" class="dashAnchor"></a>
            <h5><a href="#clone">clone</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop:clone() -&gt; cp.prop</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a new copy of the property.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>New <code>cp.prop</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="deepTable">
            <a name="//apple_ref/cpp/Method/deepTable" class="dashAnchor"></a>
            <h5><a href="#deepTable">deepTable</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop:deepTable([skipMetatable]) -&gt; prop</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>This can be called once to enable deep copying of <code>table</code> values. By default,
<code>table</code>s are simply passed in and out. If a sub-key of a table changes, no change
will be registered when setting.</p>
<p>Parameters:</p>
<ul>
<li><code>skipMetatable</code>  - If set to <code>true</code>, copies will <em>not</em> copy the metatable into the new tables.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.prop</code> instance.</li>
</ul>
<p>Notes:</p>
<ul>
<li>See <a href="#shallowTable">shallowTable</a>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="EQ">
            <a name="//apple_ref/cpp/Method/EQ" class="dashAnchor"></a>
            <h5><a href="#EQ">EQ</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop:EQ(something) -&gt; cp.prop &lt;boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Synonym for <a href="#is">IS</a>.</p>
<p>Parameters:</p>
<ul>
<li><code>something</code>  - A value, a function or a <code>cp.prop</code> to compare to.</li>
</ul>
<p>Returns:</p>
<ul>
<li>New, read-only <code>cp.prop</code> which will be <code>true</code> if this property is equal to <code>something</code>.</li>
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
                <td><code>cp.prop:get() -&gt; value</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the current value of the property.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns</p>
<ul>
<li>The current value.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="hasWatchers">
            <a name="//apple_ref/cpp/Method/hasWatchers" class="dashAnchor"></a>
            <h5><a href="#hasWatchers">hasWatchers</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop:hasWatchers() -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns <code>true</code> if the property has any watchers.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if any watchers have been registered.</li>
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
                <td><code>cp.prop:id() -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the current ID.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The ID value.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="IMMUTABLE">
            <a name="//apple_ref/cpp/Method/IMMUTABLE" class="dashAnchor"></a>
            <h5><a href="#IMMUTABLE">IMMUTABLE</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop:IMMUTABLE() -- cp.prop</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a new <code>cp.prop</code> instance wrapping this property which will not allow it to be modified.</p>
<p>Parameters:</p>
<ul>
<li><code>propValue</code>      - The <code>cp.prop</code> value to wrap.</li>
</ul>
<p>Returns:</p>
<ul>
<li>a new <code>cp.prop</code> instance which cannot be modified.</li>
</ul>
<p>Note:</p>
<ul>
<li>The original property can still be modified (if appropriate) and watchers of the immutable value will be notified when it changes.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="IS">
            <a name="//apple_ref/cpp/Method/IS" class="dashAnchor"></a>
            <h5><a href="#IS">IS</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop:IS(something) -&gt; cp.prop &lt;boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a new property returning <code>true</code> if the value is equal to <code>something</code>.</p>
<p>Parameters:</p>
<ul>
<li><code>something</code>  - A value, a function or a <code>cp.prop</code> to compare to.</li>
</ul>
<p>Returns:</p>
<ul>
<li>New, read-only <code>cp.prop</code> which will be <code>true</code> if this property is equal to <code>something</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="ISNOT">
            <a name="//apple_ref/cpp/Method/ISNOT" class="dashAnchor"></a>
            <h5><a href="#ISNOT">ISNOT</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop:ISNOT(something) -&gt; cp.prop &lt;boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a new property returning <code>true</code> when this property is not equal to <code>something</code>.</p>
<p>Parameters:</p>
<ul>
<li><code>something</code>  - A value, a function or a <code>cp.prop</code> to compare to.</li>
</ul>
<p>Returns:</p>
<ul>
<li>New, read-only <code>cp.prop</code> which will be <code>true</code> if this property is NOT equal to <code>something</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="label">
            <a name="//apple_ref/cpp/Method/label" class="dashAnchor"></a>
            <h5><a href="#label">label</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop:label([newLabel]) -&gt; string | cp.prop</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets and sets the property label. This is human-readable text describing the <code>cp.prop</code>.
It is used when converting the prop to a string, for example.</p>
<p>Parameters:</p>
<ul>
<li>newLabel      - (optional) if provided, this will be the new label.</li>
</ul>
<p>Returns:</p>
<ul>
<li>Either the existing label, or the <code>cp.prop</code> itself if a new label was provided.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="mirror">
            <a name="//apple_ref/cpp/Method/mirror" class="dashAnchor"></a>
            <h5><a href="#mirror">mirror</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop:mirror(otherProp) -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Configures this prop and the other prop to mirror each other's values.
When one changes the other will change with it. Only one prop needs to mirror.</p>
<p>Parameters:</p>
<ul>
<li><code>otherProp</code>   - The other prop to mirror.</li>
</ul>
<p>Returns:
The same property.</p>
</td>
              </tr>
            </table>
          </section>
          <section id="monitor">
            <a name="//apple_ref/cpp/Method/monitor" class="dashAnchor"></a>
            <h5><a href="#monitor">monitor</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop:monitor(...) -&gt; cp.prop</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Adds an uncloned watch to the <code>otherProp</code> which will trigger an <a href="#update">update</a> check in this property.</p>
<p>Parameters:</p>
<ul>
<li><code>...</code>  - a list of other <code>cp.prop</code> values to monitor.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>cp.prop</code>    - This prop value.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="mutable">
            <a name="//apple_ref/cpp/Method/mutable" class="dashAnchor"></a>
            <h5><a href="#mutable">mutable</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop:mutable() -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks if the <code>cp.prop</code> can be modified.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the value can be modified.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="mutate">
            <a name="//apple_ref/cpp/Method/mutate" class="dashAnchor"></a>
            <h5><a href="#mutate">mutate</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop:mutate(getFn[, setFn]) -&gt; cp.prop &lt;anything; read-only&gt;, function</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a new property that is a mutation of the current one.
Watchers of the mutant will be if a change in the current prop causes
the mutation to be a new value.</p>
<p>The <code>getFn</code> is a function with the following signature:</p>
<div class="highlight"><pre><span></span><span class="kr">function</span><span class="p">(</span><span class="n">original</span><span class="p">,</span> <span class="n">owner</span><span class="p">,</span> <span class="n">prop</span><span class="p">)</span> <span class="c1">--&gt; mutantValue</span>
</pre></div>
<ul>
<li><code>originalProp</code>   - The original <code>cp.prop</code> being mutated.</li>
<li><code>owner</code>          - The owner of the mutator property, if it has been bound.</li>
<li><code>mutantProp</code>     - The mutant property.</li>
<li><code>mutantValue</code>    - The new value based off the original.</li>
</ul>
<p>You can ignore any parameters that you don't need. Most simply use the <code>original</code> prop.</p>
<p>The <code>setFn</code> is optional, and is a function with the following signature:</p>
<div class="highlight"><pre><span></span><span class="kr">function</span><span class="p">(</span><span class="n">mutantValue</span><span class="p">,</span> <span class="n">original</span><span class="p">,</span> <span class="n">owner</span><span class="p">,</span> <span class="n">prop</span><span class="p">)</span> <span class="c1">--&gt; nil</span>
</pre></div>
<ul>
<li><code>mutantValue</code>    - The new value being sent in.</li>
<li><code>originalProp</code>   - The original property being mutated.</li>
<li><code>owner</code>          - The owner of the mutant property, if it has been bound.</li>
<li><code>mutantProp</code>     - The mutant property.</li>
</ul>
<p>Again, you can ignore any parameters that you don't need.
If you want to set a new value to the <code>original</code> property, you can do so.
It's recommended that you use <code>original:set(...)</code>, which will allow setting <code>nil</code> values.</p>
<p>For example:</p>
<div class="highlight"><pre><span></span><span class="n">anyNumber</span>   <span class="o">=</span> <span class="n">prop</span><span class="p">.</span><span class="n">THIS</span><span class="p">(</span><span class="mi">1</span><span class="p">)</span>
<span class="n">isEven</span>      <span class="o">=</span> <span class="n">anyNumber</span><span class="p">:</span><span class="n">mutate</span><span class="p">(</span><span class="kr">function</span><span class="p">(</span><span class="n">original</span><span class="p">)</span> <span class="kr">return</span> <span class="n">original</span><span class="p">()</span> <span class="o">%</span> <span class="mi">2</span> <span class="o">==</span> <span class="mi">0</span> <span class="kr">end</span><span class="p">)</span>
    <span class="p">:</span><span class="n">watch</span><span class="p">(</span><span class="kr">function</span><span class="p">(</span><span class="n">even</span><span class="p">)</span>
        <span class="kr">if</span> <span class="n">even</span><span class="p">()</span> <span class="kr">then</span>
            <span class="nb">print</span> <span class="s2">&quot;even&quot;</span>
        <span class="kr">else</span>
            <span class="nb">print</span> <span class="s2">&quot;odd&quot;</span>
        <span class="kr">end</span>
    <span class="kr">end</span><span class="p">)</span>

<span class="n">isEven</span><span class="p">:</span><span class="n">update</span><span class="p">()</span>     <span class="c1">-- prints &quot;odd&quot;</span>
<span class="n">anyNumber</span><span class="p">(</span><span class="mi">10</span><span class="p">)</span>       <span class="c1">-- prints &quot;even&quot;</span>
<span class="n">isEven</span><span class="p">()</span> <span class="o">==</span> <span class="kc">true</span>    <span class="c1">-- no printing</span>
</pre></div>
<p>Parameters:</p>
<ul>
<li><code>mutateFn</code>   - The function which will mutate the value of the current property.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A new <code>cp.prop</code> which will return a mutation of the property value.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="NEQ">
            <a name="//apple_ref/cpp/Method/NEQ" class="dashAnchor"></a>
            <h5><a href="#NEQ">NEQ</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop:NEQ(something) -&gt; cp.prop &lt;boolean; read-only&gt;</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>A synonym for <a href="#isnot">ISNOT</a></p>
<p>Parameters:</p>
<ul>
<li><code>something</code>  - A value, a function or a <code>cp.prop</code> to compare to.</li>
</ul>
<p>Returns:</p>
<ul>
<li>New, read-only <code>cp.prop</code> which will be <code>true</code> if this property is NOT equal to <code>something</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="NOT">
            <a name="//apple_ref/cpp/Method/NOT" class="dashAnchor"></a>
            <h5><a href="#NOT">NOT</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop:NOT() -&gt; cp.prop</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a new <code>cp.prop</code> which negates the current value. Values are negated as follows:</p>
<ul>
<li><code>boolean</code>    - Switch between <code>true</code> and <code>false</code></li>
<li><code>nil</code>        - Switches to <code>true</code></li>
<li><other>  - Switches to <code>nil</code>.</li>
</ul>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>a <code>cp.prop</code> instance negating the current instance.</li>
</ul>
<p>Notes:</p>
<ul>
<li>If this property is mutable, you can set the <code>NOT</code> property value and this property will be set to the negated value. Be aware that the same negation rules apply when setting as when getting.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="observe">
            <a name="//apple_ref/cpp/Method/observe" class="dashAnchor"></a>
            <h5><a href="#observe">observe</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop:observe() -&gt; cp.rx.Observable</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the <code>cp.rx.Observable</code> for the property. This will emit
<code>onNext()</code> events with the current value whenever the <code>cp.prop</code> is updated.
Any new subscriptions will receive the most recent value immediately.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>Observable</code> instance for the property.</li>
</ul>
<p>Notes:</p>
<ul>
<li>It will only emit <code>onNext</code> events, never an <code>onError</code> or <code>onCompleted</code> event.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="OR">
            <a name="//apple_ref/cpp/Method/OR" class="dashAnchor"></a>
            <h5><a href="#OR">OR</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop:OR(...) -&gt; cp.prop</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a new <code>cp.prop</code> which will be <code>true</code> if this or any <code>cp.prop</code> instance passed into the function returns <code>true</code>.</p>
<p>Parameters:</p>
<ul>
<li><code>...</code>        - The list of <code>cp.prop</code> instances to 'OR' together.</li>
</ul>
<p>Returns:</p>
<ul>
<li>a <code>cp.prop</code> instance.</li>
</ul>
<p>Notes:</p>
<ul>
<li>See <a href="#or">OR Function</a> for more details.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="owner">
            <a name="//apple_ref/cpp/Method/owner" class="dashAnchor"></a>
            <h5><a href="#owner">owner</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop:owner() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>If this is a 'method', return the table instance the method is attached to.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The owner table, or <code>nil</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="preWatch">
            <a name="//apple_ref/cpp/Method/preWatch" class="dashAnchor"></a>
            <h5><a href="#preWatch">preWatch</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop:preWatch(preWatchFn) -&gt; cp.prop</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Adds a function which will be called once if any watchers are added to this prop.
This allows configuration, typically for watching other events, but only if
anything is actually watching this property value.</p>
<p>If the prop already has watchers, this function will be called imediately.</p>
<p>Parameters:</p>
<ul>
<li><code>preWatchFn</code>     - The function to call once when the prop is watched. Has the signature <code>function(owner, prop)</code>.</li>
</ul>
<p>Returns:</p>
<ul>
<li>Nothing</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="set">
            <a name="//apple_ref/cpp/Method/set" class="dashAnchor"></a>
            <h5><a href="#set">set</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop:set(newValue) -&gt; value</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Sets the property to the specified value. Watchers will be notified if the value has changed.</p>
<p>Parameters:</p>
<ul>
<li><code>newValue</code>   - The new value to set. May be <code>nil</code>.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The current value of the prop. May not be the same as <code>newValue</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="shallowTable">
            <a name="//apple_ref/cpp/Method/shallowTable" class="dashAnchor"></a>
            <h5><a href="#shallowTable">shallowTable</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop:shallowTable(skipMetatable) -&gt; prop</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>This can be called once to enable shallow cloning of <code>table</code> values. By default,
<code>table</code>s are simply passed in and out. If a sub-key of a table changes, no change
will be registered when setting.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.prop</code> instance.</li>
</ul>
<p>Notes:</p>
<ul>
<li>See <a href="#deepTable">deepTable</a>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="toggle">
            <a name="//apple_ref/cpp/Method/toggle" class="dashAnchor"></a>
            <h5><a href="#toggle">toggle</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop:toggle() -&gt; boolean | nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Toggles the current value. Values are modified as follows:</p>
<ul>
<li><code>boolean</code>    - Switch between <code>true</code> and <code>false</code></li>
<li><code>nil</code>        - Switches to <code>true</code></li>
<li><other>  - Switches to <code>nil</code>.</li>
</ul>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The new value.</li>
</ul>
<p>Notes:</p>
<ul>
<li>If the value is immutable, an error will be thrown.</li>
<li>If you toggle a non-boolean parameter twice, it will end up set to <code>true</code>.</li>
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
                <td><code>cp.prop:unwatch(watchFn) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Removes the specified watch method as a watcher, if present. An example of adding and removing a watch:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">prop</span><span class="p">,</span> <span class="n">watcher</span> <span class="o">=</span> <span class="n">prop</span><span class="p">.</span><span class="n">TRUE</span><span class="p">():</span><span class="n">watch</span><span class="p">(</span><span class="kr">function</span><span class="p">(</span><span class="n">value</span><span class="p">)</span> <span class="nb">print</span> <span class="nb">tostring</span><span class="p">(</span><span class="n">value</span><span class="p">)</span> <span class="kr">end</span><span class="p">)</span>
<span class="n">prop</span><span class="p">:</span><span class="n">unwatch</span><span class="p">(</span><span class="n">watcher</span><span class="p">)</span> <span class="o">==</span> <span class="kc">true</span>
</pre></div>
<p>Parameters:</p>
<ul>
<li><code>watchFn</code>        - The original watch function to remove. Must be the same instance that was added.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the function was watching and successfully removed, otherwise <code>false</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="update">
            <a name="//apple_ref/cpp/Method/update" class="dashAnchor"></a>
            <h5><a href="#update">update</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop:update() -&gt; value</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Forces an update of the property and notifies any watchers if it has changed.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns</p>
<ul>
<li>The current value of the property.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="value">
            <a name="//apple_ref/cpp/Method/value" class="dashAnchor"></a>
            <h5><a href="#value">value</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop:value([newValue]) -&gt; value</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the current value of the <code>cp.prop</code> instance. If a <code>newValue</code> is provided, and the instance is mutable, the value will be updated and the new value is returned. If it is not mutable, an error will be thrown.</p>
<p>This method can also be called directly on the property, like so:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">foo</span> <span class="o">=</span> <span class="n">prop</span><span class="p">.</span><span class="n">TRUE</span><span class="p">()</span>
<span class="n">foo</span><span class="p">()</span> <span class="o">==</span> <span class="n">foo</span><span class="p">:</span><span class="n">value</span><span class="p">()</span>
</pre></div>
<p>Parameters:</p>
<ul>
<li><code>newValue</code>   - The new value to set the instance to.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The current boolean value.</li>
</ul>
<p>Notes:</p>
<ul>
<li>If you need to set the property to <code>nil</code>, use the <a href="#set">set method</a>, otherwise it will be ignored.</li>
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
                <td><code>cp.prop:watch(watchFn[, notifyNow]) -&gt; cp.prop, function</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Adds the watch function to the value. When the value changes, watchers are notified by calling the function. The function should have the following signature:</p>
<div class="highlight"><pre><span></span><span class="kr">function</span><span class="p">(</span><span class="n">value</span><span class="p">,</span> <span class="n">owner</span><span class="p">,</span> <span class="n">prop</span><span class="p">)</span>
</pre></div>
<ul>
<li><code>value</code>  - The new value of the property</li>
<li><code>owner</code>  - The property owner. May be <code>nil</code>.</li>
<li><code>prop</code>   - The property itself.</li>
</ul>
<p>Parameters:</p>
<ul>
<li><code>watchFn</code>        - The watch function, with the signature <code>function(newValue, owner)</code>.</li>
<li><code>notifyNow</code>  - The function will be triggered immediately with the current state.  Defaults to <code>false</code>.</li>
<li><code>uncloned</code>   - If <code>true</code>, the watch function will not be attached to any clones of this prop.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>cp.prop</code>        - The same <code>cp.prop</code> instance</li>
<li><code>function</code>   - The watch function, which can be passed to <a href="#unwatch">unwatch</a> to stop watching.</li>
</ul>
<p>Notes:</p>
<ul>
<li>You can watch immutable values. Wrapped <code>cp.prop</code> instances may not be immutable, and any changes to them will cause watchers to be notified up the chain.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="wrap">
            <a name="//apple_ref/cpp/Method/wrap" class="dashAnchor"></a>
            <h5><a href="#wrap">wrap</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.prop:wrap([owner[, key]]) -&gt; cp.prop <anything></code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a new property that wraps this one. It will be able to get and set the same as this, and changes
to this property will trigger updates in the wrapper.</p>
<p>Parameters:</p>
<ul>
<li><code>owner</code>  -    (optional) If provided, the wrapper will be bound to the specified owner.</li>
<li><code>key</code>    -    (optional) If provided, the wrapper will be assigned to the owner with the specified key.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A new <code>cp.prop</code> which wraps this property.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
