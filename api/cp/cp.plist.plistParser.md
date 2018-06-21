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
      <h1><a href="cp.plist.plistParser.md">docs</a> &raquo; cp.plist.plistParser</h1>
      <p>plistParser (<a href="https://codea.io/talk/discussion/1269/code-plist-parser">https://codea.io/talk/discussion/1269/code-plist-parser</a>)
version 1.01</p>
<p>based on an XML parser by Roberto Ierusalimschy at:
lua-users.org/wiki/LuaXml</p>
<p>Takes a string-ified .plist file as input, and outputs
a table. Nested dictionaries and arrays are parsed into
subtables. Table structure will match the structure of
the .plist file</p>
<p>Usage:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">plistStr</span> <span class="o">=</span> <span class="o">&lt;</span><span class="n">string</span><span class="o">-</span><span class="n">ified</span> <span class="n">plist</span> <span class="n">file</span><span class="o">&gt;</span>
<span class="kd">local</span> <span class="n">plistTable</span> <span class="o">=</span> <span class="n">plistParse</span><span class="p">(</span><span class="n">plistStr</span><span class="p">)</span>
</pre></div>

      </header>
      <h3>API Overview</h3>
      <ul>
      </ul>
      <h3>API Documentation</h3>
