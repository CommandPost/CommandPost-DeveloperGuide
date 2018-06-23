# [docs](index.md) » hs.doc.markdown
---

Markdown to HTML and plaintext conversion support used by hs.doc

This module provides Github-Flavored-Markdown conversion support used by hs.doc.  This module is a Lua wrapper to the C code portion of the Ruby gem `github-markdown`, available at https://rubygems.org/gems/github-markdown/versions/0.6.9.

The Ruby gem `github-markdown` was chosen as the code base for this module because it is the tool used to generate the official Hammerspoon Dash docset.

The Lua wrapper portion is licensed under the MIT license by the Hammerspoon development team.  The C code portion of the Ruby gem is licensed under the MIT license by GitHub, Inc.

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
	<li><a href="#convert">convert</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Functions</h4>
  <section id="convert">
	<h5><a href="#convert">convert</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.doc.markdown.convert(markdown, [type]) -&gt; output</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Function</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Converts markdown encoded text to html or plaintext.</p>
<p>Parameters:</p>
<ul>
<li>markdown - a string containing the input text encoded using markdown tags</li>
<li>type     - an optional string specifying the conversion options and output type.  Defaults to "gfm".  The currently recognized types are:<ul>
<li>"markdown"  - specfies that the output should be HTML with the standard GitHub/Markdown extensions enabled.</li>
<li>"gfm"       - specifies that the output should be HTML with additional GitHub extensions enabled.</li>
<li>"plaintext" - specifies that the output should plain text with the standard GitHub/Markdown extensions enabled.</li>
</ul>
</li>
</ul>
<p>Returns:</p>
<ul>
<li>an HTML or plaintext representation of the markdown encoded text provided.</li>
</ul>
<p>Notes:</p>
<ul>
<li><p>The standard GitHub/Markdown extensions enabled for all conversions are:</p>
<ul>
<li>NO_INTRA_EMPHASIS -  disallow emphasis inside of words</li>
<li>LAX_SPACING       - supports spacing like in Markdown 1.0.0 (i.e. do not require an empty line between two different blocks in a paragraph)</li>
<li>STRIKETHROUGH     - support strikethrough with double tildes (~)</li>
<li>TABLES            - support Markdown tables</li>
<li>FENCED_CODE       - supports fenced code blocks surround by three back-ticks (`) or three tildes (~)</li>
<li>AUTOLINK          - HTTP URL's are treated as links, even if they aren't marked as such with Markdown tags</li>
</ul>
</li>
<li><p>The "gfm" type also includes the following extensions:</p>
<ul>
<li>HARD_WRAP     - line breaks are replaced with <br> entities</li>
<li>SPACE_HEADERS - require a space between the <code>#</code> and the name of a header (prevents collisions with the Issues filter)</li>
</ul>
</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
