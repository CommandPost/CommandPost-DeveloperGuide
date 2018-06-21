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
      <h1><a href="cp.text.matcher.md">docs</a> &raquo; cp.text.matcher</h1>
      <p>Adapted from 'utf8.lua' (<a href="https://github.com/Stepets/utf8.lua">https://github.com/Stepets/utf8.lua</a>)</p>
<p>Copyright (c) 2006-2007, Kyle Smith
All rights reserved.</p>
<p>Contributors:
    Alimov Stepan
    David Peterson</p>
<p>Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:</p>

<pre><code>* Redistributions of source code must retain the above copyright notice,
  this list of conditions and the following disclaimer.
* Redistributions in binary form must reproduce the above copyright
  notice, this list of conditions and the following disclaimer in the
  documentation and/or other materials provided with the distribution.
* Neither the name of the author nor the names of its contributors may be
  used to endorse or promote products derived from this software without
  specific prior written permission.

</code></pre>
<p>THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT OWNER OR CONTRIBUTORS BE LIABLE
FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY,
OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Constructors - API calls which return an object, typically one that offers API methods</li>
          <ul>
            <li><a href="#matcher">matcher</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#find">find</a></li>
            <li><a href="#gmatch">gmatch</a></li>
            <li><a href="#gsub">gsub</a></li>
            <li><a href="#match">match</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Constructors</h4>
          <section id="matcher">
            <a name="//apple_ref/cpp/Constructor/matcher" class="dashAnchor"></a>
            <h5><a href="#matcher">matcher</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.text.matcher(pattern[, plain]) -&gt; cp.text.matcher</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a matcher for the specified pattern. This follows the conventions of the standard <a href="https://www.lua.org/pil/20.2.html">LUA Patterns</a> API. This will return a reusable, compiled parser for the given pattern.</p>
<p>Parameters:</p>
<ul>
<li><code>pattern</code>    - The pattern to parse</li>
<li><code>plain</code>      - If <code>true</code>, the pattern is not parsed and the provided text must match exactly.
Returns:<ul>
<li>New <code>cp.text.matcher</code> for the pattern.</li>
</ul>
</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Methods</h4>
          <section id="find">
            <a name="//apple_ref/cpp/Method/find" class="dashAnchor"></a>
            <h5><a href="#find">find</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.text.matcher:find(value[, start]) -&gt; number, number, ...</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Processes the text, returning the start position, the end position, followed by any capture group values.</p>
<p>Parameters:</p>
<ul>
<li><code>value</code>      - The <code>cp.text</code> value to process.</li>
<li><code>start</code>      - If specified, indicates the starting position to process from. Defaults to <code>1</code>.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The start position for the match, end position, and the list of capture group values.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="gmatch">
            <a name="//apple_ref/cpp/Method/gmatch" class="dashAnchor"></a>
            <h5><a href="#gmatch">gmatch</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.text.matcher:gmatch(value) -&gt; function</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns an iterator function that, each time it is called, returns the next captures from pattern over string s. If pattern specifies no captures, then the whole match is produced in each call.</p>
<p>Parameters:</p>
<ul>
<li><code>value</code>      - The <code>cp.text</code> value to process.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The iterator function.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="gsub">
            <a name="//apple_ref/cpp/Method/gsub" class="dashAnchor"></a>
            <h5><a href="#gsub">gsub</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.text.matcher:gsub(value, repl, limit) -&gt; text, number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a copy of <code>value</code> in which all (or the first <code>n</code>, if given) occurrences of the pattern have been replaced by a replacement string specified by <code>repl</code>, which can be text, a string, a table, or a function. gsub also returns, as its second value, the total number of matches that occurred.</p>
<p>Parameters:</p>
<ul>
<li><code>value</code>  - The text or string value to process.</li>
<li><code>repl</code>   - The replacement text/string/table/function</li>
<li><code>limit</code>  - The maximum number of times to do the replacement. Defaults to unlimited.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>text</code>   - The text value with replacements.</li>
<li><code>number</code> - The number of matches that occurred.</li>
</ul>
<p>Notes:</p>
<ul>
<li>If repl is text or a string, then its value is used for replacement. The character <code>%</code> works as an escape character: any sequence in repl of the form <code>%n</code>, with <code>n</code> between <code>1</code> and <code>9</code>, stands for the value of the <code>n</code>-th captured substring (see below). The sequence <code>%0</code> stands for the whole match. The sequence <code>%%</code> stands for a single <code>%</code>.</li>
<li>If <code>repl</code> is a table, then the table is queried for every match, using the first capture as the key; if the pattern specifies no captures, then the whole match is used as the key.</li>
<li>If <code>repl</code> is a function, then this function is called every time a match occurs, with all captured substrings passed as arguments, in order; if the pattern specifies no captures, then the whole match is passed as a sole argument.</li>
<li>If the value returned by the table query or by the function call is a string or a number, then it is used as the replacement string; otherwise, if it is <code>false</code> or <code>nil</code>, then there is no replacement (that is, the original match is kept in the string).</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="match">
            <a name="//apple_ref/cpp/Method/match" class="dashAnchor"></a>
            <h5><a href="#match">match</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.text.matcher:match(value[, start]) -&gt; ...</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Looks for the first match of the pattern in the string <code>value</code>. If it finds one, then match returns the captures from the pattern; otherwise it returns <code>nil</code>. If pattern specifies no captures, then the whole match is returned. A third, optional numerical argument init specifies where to start the search; its default value is <code>1</code> and can be negative.</p>
<p>Parameters:</p>
<ul>
<li><code>value</code>      - The <code>cp.text</code> value to process.</li>
<li><code>start</code>      - If specified, indicates the starting position to process from. Defaults to <code>1</code>.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The capture results, the whole match, or <code>nil</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
