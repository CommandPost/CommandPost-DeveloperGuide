# [docs](index.md) » plugins.finalcutpro.timeline.generators
---

Controls Final Cut Pro's Generators.

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
	<li><a href="#apply">apply</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="apply">
	<h5><a href="#apply">apply</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>plugins.finalcutpro.timeline.generators.apply(action) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Applies the specified action as a generator. Expects action to be a table with the following structure:</p>
<div class="highlight"><pre><span></span><span class="p">{</span> <span class="n">name</span> <span class="o">=</span> <span class="s2">&quot;XXX&quot;</span><span class="p">,</span> <span class="n">category</span> <span class="o">=</span> <span class="s2">&quot;YYY&quot;</span><span class="p">,</span> <span class="n">theme</span> <span class="o">=</span> <span class="s2">&quot;ZZZ&quot;</span> <span class="p">}</span>
</pre></div>
<p>...where <code>"XXX"</code>, <code>"YYY"</code> and <code>"ZZZ"</code> are in the current FCPX language. The <code>category</code> and <code>theme</code> are optional,
but if they are known it's recommended to use them, or it will simply execute the first matching generator with that name.</p>
<p>Alternatively, you can also supply a string with just the name.</p>
<p>Actions will be cached each session, so that if the user applies the effect multiple times, only the first time will require
GUI scripting - subsequent uses will just use the Pasteboard.</p>
<p>Parameters:</p>
<ul>
<li><code>action</code>     - A table with the name/category/theme for the generator to apply, or a string with just the name.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if a matching generator was found and applied to the timeline.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
