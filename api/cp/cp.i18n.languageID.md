# [docs](index.md) » cp.i18n.languageID
---

As per [Apple's documentation](https://developer.apple.com/library/content/documentation/MacOSX/Conceptual/BPInternational/LanguageandLocaleIDs/LanguageandLocaleIDs.html#//apple_ref/doc/uid/10000171i-CH15-SW6),
a `language ID` is a code which identifies either a language used across multiple regions,
a dialect from a specific region, or a script used in multiple regions. See the [parse](#parse) function for details.

When you parse a code with the [forCode](#forCode) function, it will result in a table that contains a
reference to the approprate `cp.i18n.language` table, and up to one of either the matching `cp.i18n.region`
or `cp.i18n.script` tables. These contain the full details for each language/regin/script, as appropriate.

You can also convert the resulting table back to the code via `tostring`, or the [code](#code) method.

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
	<li><a href="#is">is</a></li>
	<li><a href="#parse">parse</a></li>
  </ul>
<li>Constructors - API calls which return an object, typically one that offers API methods</li>
  <ul>
	<li><a href="#forCode">forCode</a></li>
	<li><a href="#forLocaleID">forLocaleID</a></li>
	<li><a href="#forParts">forParts</a></li>
  </ul>
<li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
  <ul>
	<li><a href="#code">code</a></li>
	<li><a href="#language">language</a></li>
	<li><a href="#region">region</a></li>
	<li><a href="#script">script</a></li>
  </ul>
<li>Methods - API calls which can only be made on an object returned by a constructor</li>
  <ul>
	<li><a href="#toLocaleID">toLocaleID</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="is">
	<h5><a href="#is">is</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.i18n.languageID.is(thing) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Checks if the <code>thing</code> is a languageID instance.</p>
<p>Parameters:</p>
<ul>
<li>thing     - the thing to check.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the <code>thing</code> is a <code>languageID</code>, otherwise <code>false</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="parse">
	<h5><a href="#parse">parse</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.i18n.languageID.parse(code) -&gt; string, string, string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Parses a <code>language ID</code> into three possible string components:</p>
<ol>
<li>The ISO 693-1 language code</li>
<li>The ISO 15924 script code</li>
<li>The ISO 3166-1 region code</li>
</ol>
<p>This is one of the following patterns:</p>
<ul>
<li><code>[language]</code> - eg. <code>"en"</code>, or <code>"fr"</code>. The covers the language across all languages and scripts.</li>
<li><code>[language]-[script]</code> - eg. "az-Arab" for Azerbaijani in Arabic script, "az-Latn" for Azerbaijani in Latin script.</li>
<li><code>[language]-[region]</code> - eg. "en-AU" for Australian English, "fr-CA" for Canadian French, etc.</li>
</ul>
<p>It will then return the matched component in three return values: language, region, script.
If a script is specified, the <code>region</code> will be <code>nil</code>. Eg.:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">lang</span><span class="p">,</span> <span class="n">scrpt</span><span class="p">,</span> <span class="n">rgn</span><span class="p">,</span> <span class="n">scrpt</span> <span class="o">=</span> <span class="n">languageID</span><span class="p">.</span><span class="n">parse</span><span class="p">(</span><span class="s2">&quot;en-AU&quot;</span><span class="p">)</span> <span class="c1">-- results in &quot;en&quot;, nil, &quot;AU&quot;</span>
</pre></div>
<p>Parameters:</p>
<ul>
<li>code      - The <code>language ID</code> code. Eg. "en-AU".</li>
</ul>
<p>Returns:</p>
<ul>
<li>language  - The two-character lower-case alpha language code.</li>
<li>script    - the four-character mixed-case alpha script code.</li>
<li>region    - The two-character upper-case alpha region code.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Constructors</h4>
  <section id="forCode">
	<h5><a href="#forCode">forCode</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.i18n.languageID.forCode(code) -&gt; cp.i18n.languageID, string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constructor</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates, or retrieves from the cache, a <code>languageID</code> instance for the specified <code>code</code>.</p>
<p>If the code can't be parsed, or if the actual language/region/script codes don't exist,
<code>nil</code> is returned.</p>
<p>Parameters:</p>
<ul>
<li>code      - The language ID code.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The matching <code>languageID</code>, or <code>nil</code> if the language ID couldn't be found.</li>
<li>The error message, or <code>nil</code> if there was no problem.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="forLocaleID">
	<h5><a href="#forLocaleID">forLocaleID</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.i18n.languageID.forLocaleID(code[, prioritiseScript]) -&gt; cp.i18n.languageID, string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constructor</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates, or retrieves from the cache, a <code>languageID</code> instance for the specified <code>cp.i18n.localeID</code>.
Language IDs can only have either a script or a region, so if the locale has both, this will
priortise the <code>region</code> by default. You can set <code>prioritiseScript</code> to <code>true</code> to use script instead.
If only one or the other is set in the locale, <code>prioritiseScript</code> is ignored.</p>
<p>Parameters:</p>
<ul>
<li>locale            - The <code>localeID</code> to convert</li>
<li>prioritiseScript  - If set to <code>true</code> and the locale has both a region and script then the script code will be used.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>languageID</code> for the <code>locale</code>, or <code>nil</code></li>
<li>The error message if there was a problem.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="forParts">
	<h5><a href="#forParts">forParts</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.i18n.languageID.forParts(languageCode[, scriptCode[, regionCode]]) -&gt; cp.i18n.languageID</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constructor</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns a <code>languageID</code> with the specified parts.</p>
<p>Parameters:</p>
<ul>
<li>languageCode - Language code</li>
<li>scriptCode - Optional Script code</li>
<li>regionCode - Optional Region Code</li>
</ul>
<p>Returns:</p>
<ul>
<li>A <code>cp.i18n.languageID</code> object.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Fields</h4>
  <section id="code">
	<h5><a href="#code">code</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.i18n.languageID.code <string></code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The language ID code.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="language">
	<h5><a href="#language">language</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.i18n.languageID.language &lt;cp.i18n.language&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The matching <code>language</code> details.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="region">
	<h5><a href="#region">region</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.i18n.languageID.region &lt;cp.i18n.region&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The matching <code>region</code> details, if appropriate. Will be <code>nil</code> if no region was specified in the <code>code</code>.</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="script">
	<h5><a href="#script">script</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.i18n.languageID.script &lt;cp.i18n.script&gt;</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The matching <code>script</code> details, if appropriate. Will be <code>nil</code> if no script was specified in the <code>code</code>.</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Methods</h4>
  <section id="toLocaleID">
	<h5><a href="#toLocaleID">toLocaleID</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.i18n.languageID:toLocaleID() -&gt; cp.i18n.localeID</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the <code>cp.i18n.localeID</code> equivalent for this <code>languageID</code>.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The matching <code>localeID</code>.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
