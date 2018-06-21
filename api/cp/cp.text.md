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
      <h1><a href="cp.text.md">docs</a> &raquo; cp.text</h1>
      <p>This module provides support for loading, manipulating, and comparing unicode text data.
It works by storing characters with their Unicode 'codepoint<code>value. In practice, this means that every character is a 64-bit integer, so a</code>text<code>value will use substantially more memory than the equivalent encoded</code>string` value.</p>
<p>The advantages of <code>text</code> over <code>string</code> representations for Unicode are:</p>
<ul>
<li>comparisons, equality checks, etc. actually work for Unicode text and are not encoding-dependent.</li>
<li>direct access to codepoint values.</li>
</ul>
<p>The advantages of <code>string</code> representations for Unicode are:</p>
<ul>
<li>compactness.</li>
<li>reading/writing to files via the standard <code>io</code> library.</li>
</ul>
<h2>Strings and Unicode</h2>
<p>LUA has limited built-in support for Unicode text. <code>string</code> values are "8-bit clean", which means it is an array of 8-bit characters. This is also how binary data from files is usually loaded, as 8-bit 'bytes'. Unicode characters can be up to 32-bits, so there are several standard ways to represent Unicode characters using 8-bit characters. Without going into detail, the most common encodings are called 'UTF-8' and 'UTF-16'. There are two variations of 'UTF-16', depending on the hardware architecture, known as 'big-endian' and 'little-endian'.</p>
<p>The built-in functions for <code>string</code>, such as <code>match</code>, <code>gsub</code> and even <code>len</code> will not work as expected when a string contains Unicode text. As such, this library fills some of the gaps for common operations when working with Unicode text.</p>
<h2>Examples</h2>
<p>You can convert to and from <code>string</code> and <code>text</code> values like so:</p>
<div class="highlight"><pre><span></span><span class="kd">local</span> <span class="n">text</span> <span class="o">=</span> <span class="nb">require</span><span class="p">(</span><span class="s2">&quot;cp.text&quot;</span><span class="p">)</span>

<span class="kd">local</span> <span class="n">simpleString</span>      <span class="o">=</span> <span class="s2">&quot;foobar&quot;</span>
<span class="kd">local</span> <span class="n">simpleText</span>        <span class="o">=</span> <span class="n">text</span><span class="p">(</span><span class="n">stringValue</span><span class="p">)</span>
<span class="kd">local</span> <span class="n">utf8String</span>        <span class="o">=</span> <span class="s2">&quot;a丽𐐷&quot;</span>                <span class="c1">-- contains non-ascii characters, defaults to UTF-8.</span>
<span class="kd">local</span> <span class="n">unicodeText</span>       <span class="o">=</span> <span class="n">text</span> <span class="s2">&quot;a丽𐐷&quot;</span>           <span class="c1">-- contains non-ascii characters, converts from a UTF-8 string.</span>
<span class="kd">local</span> <span class="n">utf8String</span>        <span class="o">=</span> <span class="nb">tostring</span><span class="p">(</span><span class="n">unicodeText</span><span class="p">)</span> <span class="c1">-- `tostring` will default to UTF-8 encoding</span>
<span class="kd">local</span> <span class="n">utf16leString</span>     <span class="o">=</span> <span class="n">unicodeText</span><span class="p">:</span><span class="n">encode</span><span class="p">(</span><span class="n">text</span><span class="p">.</span><span class="n">encoding</span><span class="p">.</span><span class="n">utf16le</span><span class="p">)</span> <span class="c1">-- or you can be more specific</span>
</pre></div>
<p>Note that <code>text</code> values are not in any specific encoding, since they are stored as 64-bit integer <code>code-points</code> rather than 8-bit characers.</p>

      </header>
        <h3>Submodules</h3>
        <ul>
        <li><a href="cp.text.matcher.html">cp.text.matcher</a></li>
        </ul>
      <h3>API Overview</h3>
      <ul>
        <li>Constants - Useful values which cannot be changed</li>
          <ul>
            <li><a href="#encoding">encoding</a></li>
          </ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#is">is</a></li>
          </ul>
        <li>Constructors - API calls which return an object, typically one that offers API methods</li>
          <ul>
            <li><a href="#char">char</a></li>
            <li><a href="#fromCodepoints">fromCodepoints</a></li>
            <li><a href="#fromFile">fromFile</a></li>
            <li><a href="#fromString">fromString</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#encode">encode</a></li>
            <li><a href="#find">find</a></li>
            <li><a href="#len">len</a></li>
            <li><a href="#match">match</a></li>
            <li><a href="#sub">sub</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Constants</h4>
          <section id="encoding">
            <a name="//apple_ref/cpp/Constant/encoding" class="dashAnchor"></a>
            <h5><a href="#encoding">encoding</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.text.encoding</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constant</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The list of supported encoding formats:</p>
<ul>
<li><code>utf8</code>       - UTF-8. The most common format on the web, backwards compatible with ANSI/ASCII.</li>
<li><code>utf16le</code>    - UTF-16 (little-endian). Commonly used in Windows and Mac text files.</li>
<li><code>utf16be</code>    - UTF-16 (big-endian). Alternate 16-bit format, common on Linux and PowerPC-based architectures.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Functions</h4>
          <section id="is">
            <a name="//apple_ref/cpp/Function/is" class="dashAnchor"></a>
            <h5><a href="#is">is</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.text.is(value) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks if the provided value is a <code>text</code> instance.</p>
<p>Parameters:</p>
<ul>
<li><code>value</code>  - The value to check</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the value is a <code>text</code> instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Constructors</h4>
          <section id="char">
            <a name="//apple_ref/cpp/Constructor/char" class="dashAnchor"></a>
            <h5><a href="#char">char</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.text.char(...) -&gt; text</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the list of one or more codepoint items into a text value, concatenating the results.</p>
<p>Parameters:</p>
<ul>
<li><code>...</code>    - The list of codepoint integers.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.text</code> value for the list of codepoint values.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="fromCodepoints">
            <a name="//apple_ref/cpp/Constructor/fromCodepoints" class="dashAnchor"></a>
            <h5><a href="#fromCodepoints">fromCodepoints</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.text.fromCodepoints(codepoints[, i[, j]]) -&gt; text</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a new <code>text</code> instance representing the specified array of codepoints. Since <code>i</code> and <code>j</code> default to the first
and last indexes of the array, simply passing in the array will convert all codepoints in that array.</p>
<p>Parameters:</p>
<ul>
<li><code>codepoints</code> - The array of codepoint integers.</li>
<li><code>i</code>          - The starting index to read from codepoints. Defaults to <code>1</code>.</li>
<li><code>j</code>          - The ending index to read from codepoints. Default to <code>-1</code>.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A new <code>text</code> instance.</li>
</ul>
<p>Notes:</p>
<ul>
<li>You can use a <em>negative</em> value for <code>i</code> and <code>j</code>. If so, it will count back from then end of the <code>codepoints</code> array.</li>
<li>If the codepoint array begins with a Byte-Order Marker (BOM), the BOM is skipped in the resulting text.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="fromFile">
            <a name="//apple_ref/cpp/Constructor/fromFile" class="dashAnchor"></a>
            <h5><a href="#fromFile">fromFile</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.text.fromFile(path[, encoding]) -&gt; text</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a new <code>text</code> instance representing the text loaded from the specified path. If no encoding is specified,
it will attempt to determine the encoding from a leading Byte-Order Marker (BOM). If none is present, it defaults to UTF-8.</p>
<p>Parameters:</p>
<ul>
<li><code>value</code>      - The value to turn into a unicode text instance.</li>
<li><code>encoding</code>   - One of the falues from <code>text.encoding</code>: <code>utf8</code>, <code>utf16le</code>, or <code>utf16be</code>. Defaults to <code>utf8</code>.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A new <code>text</code> instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="fromString">
            <a name="//apple_ref/cpp/Constructor/fromString" class="dashAnchor"></a>
            <h5><a href="#fromString">fromString</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.text.fromString(value[, encoding]) -&gt; text</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a new <code>text</code> instance representing the string value of the specified value. If no encoding is specified,
it will attempt to determine the encoding from a leading Byte-Order Marker (BOM). If none is present, it defaults to UTF-8.</p>
<p>Parameters:</p>
<ul>
<li><code>value</code>      - The value to turn into a unicode text instance.</li>
<li><code>encoding</code>   - One of the falues from <code>text.encoding</code>: <code>utf8</code>, <code>utf16le</code>, or <code>utf16be</code>. Defaults to <code>utf8</code>.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A new <code>text</code> instance.</li>
</ul>
<p>Notes:</p>
<ul>
<li>Calling <code>text(value)</code> is the same as calling <code>text.fromString(value, text.encoding.utf8)</code>, so simple text can be initialized via <code>local x = text "foo"</code> when the <code>.lua</code> file's encoding is UTF-8.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Methods</h4>
          <section id="encode">
            <a name="//apple_ref/cpp/Method/encode" class="dashAnchor"></a>
            <h5><a href="#encode">encode</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.text:encode([encoding]) -&gt; string</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the text as an encoded <code>string</code> value.</p>
<p>Parameters:</p>
<ul>
<li><code>encoding</code>   - The encoding to use when converting. Defaults to <code>cp.text.encoding.utf8</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="find">
            <a name="//apple_ref/cpp/Method/find" class="dashAnchor"></a>
            <h5><a href="#find">find</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.text:find(pattern [, init [, plain]])</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Looks for the first match of pattern in the string <code>value</code>. If it finds a match, then find returns the indices of <code>value</code> where this occurrence starts and ends; otherwise, it returns <code>nil</code>. A third, optional numerical argument <code>init</code> specifies where to start the search; its default value is <code>1</code> and can be negative. A value of <code>true</code> as a fourth, optional argument plain turns off the pattern matching facilities, so the function does a plain "find substring" operation, with no characters in pattern being considered "magic". Note that if plain is given, then <code>init</code> must be given as well.</p>
<p>If the pattern has captures, then in a successful match the captured values are also returned, after the two indices.</p>
<p>Preferences:</p>
<ul>
<li><code>pattern</code>        - The pattern to find.</li>
<li><code>init</code>           - The index to start matching from. Defaults to <code>1</code>.</li>
<li><code>plain</code>          - If <code>true</code>, the pattern is treated as plain text.</li>
</ul>
<p>Returns:</p>
<ul>
<li>the start index, the end index, followed by any captures</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="len">
            <a name="//apple_ref/cpp/Method/len" class="dashAnchor"></a>
            <h5><a href="#len">len</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.text:len() -&gt; number</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the number of codepoints in the text.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The number of codepoints.</li>
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
                <td><code>cp.text:match(pattern[, start]) -&gt; ...</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Looks for the first match of the <code>pattern</code> in the text value. If it finds one, then match returns the captures from the pattern; otherwise it returns <code>nil</code>. If pattern specifies no captures, then the whole match is returned. A third, optional numerical argument <code>init</code> specifies where to start the search; its default value is <code>1</code> and can be negative.</p>
<p>Parameters:</p>
<ul>
<li><code>pattern</code>    - The text pattern to process.</li>
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
          <section id="sub">
            <a name="//apple_ref/cpp/Method/sub" class="dashAnchor"></a>
            <h5><a href="#sub">sub</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.text:sub(i [, j]) -&gt; cp.text</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the substring of this text that starts at <code>i</code> and continues until <code>j</code>; <code>i</code> and <code>j</code> can be negative.
If <code>j</code> is absent, then it is assumed to be equal to <code>-1</code> (which is the same as the string length).
In particular, the call <code>cp.text:sub(1,j)</code> returns a prefix of <code>s</code> with length <code>j</code>, and <code>cp.text:sub(-i)</code> (for a positive <code>i</code>) returns a suffix of s with length i.</p>
</td>
              </tr>
            </table>
          </section>
