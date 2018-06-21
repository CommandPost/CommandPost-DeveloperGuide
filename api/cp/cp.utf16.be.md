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
      <h1><a href="cp.utf16.be.md">docs</a> &raquo; cp.utf16.be</h1>
      <p>A pure-LUA implementation of UTF-16 decoding with big-endian ordering.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#char">char</a></li>
            <li><a href="#codepoint">codepoint</a></li>
            <li><a href="#codes">codes</a></li>
            <li><a href="#len">len</a></li>
            <li><a href="#offset">offset</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Functions</h4>
          <section id="char">
            <a name="//apple_ref/cpp/Function/char" class="dashAnchor"></a>
            <h5><a href="#char">char</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.utf16.be.char(...) -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Receives zero or more integers, converts each one to its corresponding UTF-16 byte sequence and returns a string with the concatenation of all these sequences.</p>
<p>Parameters:</p>
<ul>
<li><code>...</code>        - The list of UCL codepoint integers to convert.</li>
</ul>
<p>Returns:</p>
<ul>
<li>All the codepoints converted to UTF-16, concatonated into a string.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="codepoint">
            <a name="//apple_ref/cpp/Function/codepoint" class="dashAnchor"></a>
            <h5><a href="#codepoint">codepoint</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.utf16.be.codepoint(s [, i [, j]]) -&gt; integer...</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the codepoints (as integers) from all characters in <code>s</code> that start between byte position <code>i</code> and <code>j</code> (both included). The default for <code>i</code> is 1 and for <code>j</code> is <code>i</code>. It raises an error if it meets any invalid byte sequence.</p>
<p>Parameters:</p>
<ul>
<li><code>s</code>              - The string</li>
<li><code>i</code>              - The starting index. Defaults to <code>1</code>.</li>
<li><code>j</code>              - The ending index. Defaults to <code>i</code>.</li>
</ul>
<p>Returns:</p>
<ul>
<li>a list of codepoint integers for all characters in the matching range.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="codes">
            <a name="//apple_ref/cpp/Function/codes" class="dashAnchor"></a>
            <h5><a href="#codes">codes</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.utf16.be.codes(s) -&gt; iterator</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns values so that the construction</p>
<div class="highlight"><pre><span></span><span class="kr">for</span> <span class="n">p</span><span class="p">,</span> <span class="n">c</span> <span class="kr">in</span> <span class="n">utf16</span><span class="p">.</span><span class="n">codes</span><span class="p">(</span><span class="n">s</span><span class="p">)</span> <span class="kr">do</span> <span class="n">body</span> <span class="kr">end</span>
</pre></div>
<p>will iterate over all characters in string <code>s</code>, with <code>p</code> being the position (in bytes) and <code>c</code> the code point of each character. It raises an error if it meets any invalid byte sequence.</p>
<p>Parameters:</p>
<ul>
<li><code>s</code>              - The string to iterate through.</li>
</ul>
<p>Returns:</p>
<ul>
<li>An iterator</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="len">
            <a name="//apple_ref/cpp/Function/len" class="dashAnchor"></a>
            <h5><a href="#len">len</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.utf16.be.len (s [, i [, j]]) -&gt; number | boolean, number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the number of UTF-16 characters in string <code>s</code> that start between positions <code>i</code> and <code>j</code> (both inclusive). The default for <code>i</code> is 1 and for <code>j</code> is -1. If it finds any invalid byte sequence, returns a false value plus the position of the first invalid byte.</p>
<p>Parameters:</p>
<ul>
<li><code>s</code>              - The UTF-16 string</li>
<li><code>i</code>              - The starting index. Defaults to <code>1</code>.</li>
<li><code>j</code>              - The ending index. Defaults to <code>-1</code>.</li>
</ul>
<p>Returns:</p>
<ul>
<li>the length, or <code>false</code> and the first invalid byte index.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="offset">
            <a name="//apple_ref/cpp/Function/offset" class="dashAnchor"></a>
            <h5><a href="#offset">offset</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.utf16.be.offset (s, n [, i]) -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the position (in bytes) where the encoding of the <code>n</code>-th character of <code>s</code> (counting from position <code>i</code>) starts. A negative <code>n</code> gets characters before position <code>i</code>. The default for <code>i</code> is 1 when <code>n</code> is non-negative and <code>#s + 1</code> otherwise, so that <code>utf8.offset(s, -n)</code> gets the offset of the <code>n</code>-th character from the end of the string. If the specified character is neither in the subject nor right after its end, the function returns nil.</p>
<p>As a special case, when <code>n</code> is 0 the function returns the start of the encoding of the character that contains the <code>i</code>-th byte of <code>s</code>.</p>
<p>This function assumes that <code>s</code> is a valid UTF-16 string</p>
<p>Parameters:</p>
<ul>
<li><code>s</code>              - The string</li>
<li><code>n</code>              - The character number to find.</li>
<li><code>i</code>              - The initial position to start from.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The index</li>
</ul>
</td>
              </tr>
            </table>
          </section>
