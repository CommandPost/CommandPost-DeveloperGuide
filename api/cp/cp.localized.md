# [docs](index.md) » cp.localized
---

Helps look up localized names for folders.

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
	<li><a href="#getLocalizedName">getLocalizedName</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="getLocalizedName">
	<h5><a href="#getLocalizedName">getLocalizedName</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>cp.localized.getLocalizedName(path[, locale]) -&gt; string, string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the localized name for the <code>path</code> in the specified <code>locale</code>. If all else fails, the
original folder name is returned. The 'unlocalized' folder name is returned as the second value, without <code>.localized</code> at the end, if it was present.</p>
<p>Parameters:</p>
<ul>
<li><code>path</code>           - The full path to the folder</li>
<li><code>locale</code>         - The locale to retrieve the name for.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The localized name, or <code>name</code> if not available.</li>
<li>The original name, minus <code>.localized</code></li>
</ul>
</td>
	  </tr>
	</table>
  </section>
