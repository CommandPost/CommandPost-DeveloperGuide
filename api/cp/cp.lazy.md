# [docs](index.md) » cp.lazy
---

Lazy Extension.

<style type="text/css">
	a { text-decoration: none; }
	a:hover { text-decoration: underline; }
	th { background-color: #DDDDDD; vertical-align: top; padding: 3px; }
	td { width: 100%; background-color: #EEEEEE; vertical-align: top; padding: 3px; }
	table { width: 100% ; border: 1px solid #0; text-align: left; }
	section > table table td { width: 0; }
</style>
<link rel="stylesheet" href="../../css/docs.css" type="text/css" media="screen" />
<h3>API Overview</h3>
<ul>
<li>Functions - API calls offered directly by the extension</li>
  <ul>
	<li><a href="#fn">fn</a></li>
	<li><a href="#value">value</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="fn">
	<h5><a href="#fn">fn</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.lazy.fn(target) -&gt; function</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Prepares the <code>target</code> to assign factory functions.
It returns a function which accepts a table of factory function definitions.
These factories will only ever be called once, when the 'surface' function is called the first time.</p>
<p>For example:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">o</span> <span class="o">=</span> <span class="p">{}</span>
<span class="kd">local</span> <span class="n">topId</span> <span class="o">=</span> <span class="mi">0</span>
<span class="n">lazy</span><span class="p">.</span><span class="n">fn</span><span class="p">(</span><span class="n">o</span><span class="p">)</span> <span class="p">{</span>
    <span class="n">id</span>     <span class="o">=</span> <span class="kr">function</span><span class="p">(</span><span class="n">self</span><span class="p">)</span> <span class="n">topId</span> <span class="o">=</span> <span class="n">topId</span> <span class="o">+</span> <span class="mi">1</span><span class="p">;</span> <span class="kr">return</span> <span class="n">topId</span> <span class="kr">end</span><span class="p">,</span>
<span class="p">}</span>
<span class="nb">print</span><span class="p">(</span><span class="n">o</span><span class="p">:</span><span class="n">id</span><span class="p">())</span>   <span class="c1">-- &quot;1&quot;</span>
<span class="nb">print</span><span class="p">(</span><span class="n">o</span><span class="p">:</span><span class="n">id</span><span class="p">())</span>   <span class="c1">-- still &quot;1&quot;</span>
</pre></div>
</td>
	  </tr>
	</table>
  </section>
  <section id="value">
	<h5><a href="#value">value</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.lazy.value(target) -&gt; function</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Prepares the <code>target</code> to assign factory functions.
It returns a function which accepts a table of factory function definitions.
These factories will only ever be called once, when the 'surface' function is called the first time.</p>
<p>For example:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">o</span> <span class="o">=</span> <span class="p">{}</span>
<span class="kd">local</span> <span class="n">topId</span> <span class="o">=</span> <span class="mi">0</span>
<span class="n">lazy</span><span class="p">.</span><span class="n">value</span><span class="p">(</span><span class="n">o</span><span class="p">)</span> <span class="p">{</span>
    <span class="n">id</span>     <span class="o">=</span> <span class="kr">function</span><span class="p">(</span><span class="n">self</span><span class="p">)</span> <span class="n">topId</span> <span class="o">=</span> <span class="n">topId</span> <span class="o">+</span> <span class="mi">1</span><span class="p">;</span> <span class="kr">return</span> <span class="n">topId</span> <span class="kr">end</span><span class="p">,</span>
<span class="p">}</span>
<span class="nb">print</span><span class="p">(</span><span class="n">o</span><span class="p">.</span><span class="n">id</span><span class="p">)</span>   <span class="c1">-- &quot;1&quot;</span>
<span class="nb">print</span><span class="p">(</span><span class="n">o</span><span class="p">.</span><span class="n">id</span><span class="p">)</span>   <span class="c1">-- still &quot;1&quot;</span>
</pre></div>
</td>
	  </tr>
	</table>
  </section>
