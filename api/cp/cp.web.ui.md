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
      <h1><a href="cp.web.ui.md">docs</a> &raquo; cp.web.ui</h1>
      <p>This extension contains functions which simplify the creation of standard UI events
using <code>cp.web.html</code> as the basis. Most functions return a <code>html</code> element which is
potentially dynamically updatable. Most values can be set using a value or a function,
and if functions are provided, they are re-evaluated every time the element is generated.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#heading">heading</a></li>
            <li><a href="#img">img</a></li>
            <li><a href="#javascript">javascript</a></li>
            <li><a href="#password">password</a></li>
            <li><a href="#select">select</a></li>
            <li><a href="#style">style</a></li>
            <li><a href="#template">template</a></li>
            <li><a href="#textbox">textbox</a></li>
          </ul>
        <li>Constructors - API calls which return an object, typically one that offers API methods</li>
          <ul>
            <li><a href="#button">button</a></li>
            <li><a href="#checkbox">checkbox</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Functions</h4>
          <section id="heading">
            <a name="//apple_ref/cpp/Function/heading" class="dashAnchor"></a>
            <h5><a href="#heading">heading</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.web.ui.heading(params) -&gt; cp.web.html</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a <code>cp.web.html</code> element for a heading with a specific level</p>
<p>Parameters:</p>
<ul>
<li><code>params</code> - The parameters table. Details below.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>cp.web.html</code> element representing the heading.</li>
</ul>
<p>Notes:</p>
<ul>
<li>The <code>params</code> table has the following fields:
<strong> <code>text</code>      - The string (or function) containing the text of the heading.</strong> <code>level</code>         - The heading level (or function) (1-7). Defaults to 3.
** <code>class</code>     - The CSS class (or function) for the heading tag.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="img">
            <a name="//apple_ref/cpp/Function/img" class="dashAnchor"></a>
            <h5><a href="#img">img</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.web.ui.img(params) -&gt; cp.web.html</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Generates a <code>cp.web.html</code> <code>img</code> element.</p>
<p>Parameters:</p>
<ul>
<li><code>params</code>     - A table or function returning a table with the checkbox data.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A <code>cp.web.html</code> with the select defined.</li>
</ul>
<p>Notes:</p>
<ul>
<li>The <code>params</code> table has the following supported fields:
<strong> <code>src</code>       - The source of the image. If this points to a local file, it will be encoded as Base64.</strong> <code>class</code>     - A string, (or function returning a string) with the CSS class for the element.
<strong> <code>width</code>     - The width of the image.</strong> <code>height</code>    - The height of the image.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="javascript">
            <a name="//apple_ref/cpp/Function/javascript" class="dashAnchor"></a>
            <h5><a href="#javascript">javascript</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.web.ui.javascript(script[, context]) -&gt; cp.web.html</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Generates an HTML script element which will execute the provided
JavaScript immediately. The script is self-contained and only has
access to global variables. Any local <code>var</code> values will not be available
to other scripts.</p>
<p>The script will be evaluated as a <code>resty.template</code>, and variables can be
injected from the <code>context</code> table. For example, this will create a script
that will display an alert saying "Hello world!":</p>
<div class="highlight"><pre><span></span><span class="n">ui</span><span class="p">.</span><span class="n">javascript</span><span class="p">(</span><span class="s">[[ alert(&quot;{{ message }}&quot;) ]]</span><span class="p">,</span> <span class="p">{</span> <span class="n">message</span> <span class="o">=</span> <span class="s2">&quot;Hello world!&quot;</span><span class="p">})</span>
</pre></div>
<p>Parameters:</p>
<ul>
<li>script   - String containing the JavaScript to execute.</li>
<li>context  - (optional) Table containing any values to inject into the script.</li>
</ul>
<p>Returns:</p>
<ul>
<li>a <code>cp.web.html</code> element representing the JavaScript block.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="password">
            <a name="//apple_ref/cpp/Function/password" class="dashAnchor"></a>
            <h5><a href="#password">password</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.web.ui.password(params) -&gt; hs.web.html</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates an <code>html</code> element that will output a password text box.</p>
<p>Parameters:</p>
<ul>
<li><code>params</code> - The parameters table. Details below.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>cp.web.html</code> containing the textbox.</li>
</ul>
<p>Notes:</p>
<ul>
<li>The <code>params</code> table has the following supported fields:
<strong> <code>id</code>                - The unique ID for the textbox.</strong> <code>name</code>          - The name of the textbox field.
<strong> <code>class</code>         - The CSS classname.</strong> <code>placeholder</code>   - Placeholder text</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="select">
            <a name="//apple_ref/cpp/Function/select" class="dashAnchor"></a>
            <h5><a href="#select">select</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.web.ui.select(params) -&gt; cp.web.html</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Generates a <code>cp.web.html</code> <code>select</code> element. The <code>data</code> should be a table or a function returning a table
that matches the details in the notes below.</p>
<p>Parameters:</p>
<ul>
<li><code>params</code>     - A table or function returning a table with the checkbox data.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A <code>cp.web.html</code> with the select defined.</li>
</ul>
<p>Notes:</p>
<ul>
<li>The <code>params</code> table has the following supported fields:
<strong> <code>id</code>        - a string (or function) the unique ID for the select.</strong> <code>value</code>     - a string, number, or boolean (or function) with the value of the select. May be <code>nil</code>.
<strong> <code>options</code>   - an array (or function returning an array) of option tables, with the following keys:
*</strong> <code>value</code>    - the value of the option.
<strong><em> <code>label</code>    - (optional) the label for the option. If not set, the <code>value</code> is used.</em></strong> <code>disabled</code> - (optional) if the option is disabled.
<strong> <code>required</code>  - (optional) if <code>true</code>, there will not be a 'blank' option at the top of the list.</strong> <code>blankLabel</code>    - (optional) if specified, the value will be used for the 'blank' option label.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="style">
            <a name="//apple_ref/cpp/Function/style" class="dashAnchor"></a>
            <h5><a href="#style">style</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.web.ui.style(rules[, context]) -&gt; cp.web.html</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Generates an HTML <code>style</code> element which will contain the provided rules.</p>
<p>The <code>rules</code> will be evaluated as a <code>resty.template</code>, and variables can be
injected from the <code>context</code> table. For example, this will create a set of rules
that injects the provided color:</p>
<div class="highlight"><pre><span></span><span class="n">ui</span><span class="p">.</span><span class="n">style</span><span class="p">(</span><span class="s">[[ body { color: {{ bodyColor }}; } ]]</span><span class="p">,</span> <span class="p">{</span> <span class="n">bodyColor</span> <span class="o">=</span> <span class="s2">&quot;#FFFFFF&quot;</span><span class="p">})</span>
</pre></div>
<p>Parameters:</p>
<ul>
<li>rules    - String containing the CSS rules.</li>
<li>context  - (optional) Table containing any values to inject into the script.</li>
</ul>
<p>Returns:</p>
<ul>
<li>a <code>cp.web.html</code> element representing the JavaScript block.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="template">
            <a name="//apple_ref/cpp/Function/template" class="dashAnchor"></a>
            <h5><a href="#template">template</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.web.ui.template(params) -&gt; hs.web.html</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a <code>html</code> element that will execute a Resty Template.</p>
<p>Parameters:</p>
<ul>
<li><code>params</code> - The parameters table. Details below.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>cp.web.html</code> containing the template.</li>
</ul>
<p>Notes:</p>
<ul>
<li>The <code>params</code> table has the following supported fields:
<strong> <code>view</code>      - The file path to the template, or the template content itself. Required.</strong> <code>context</code>   - The table containing the context to execute the template in.
** <code>unescaped</code> - If true, the template will not be escaped before outputting.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="textbox">
            <a name="//apple_ref/cpp/Function/textbox" class="dashAnchor"></a>
            <h5><a href="#textbox">textbox</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.web.ui.textbox(params) -&gt; hs.web.html</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates an <code>html</code> element that will output a text box.</p>
<p>Parameters:</p>
<ul>
<li><code>params</code> - The parameters table. Details below.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>cp.web.html</code> containing the textbox.</li>
</ul>
<p>Notes:</p>
<ul>
<li>The <code>params</code> table has the following supported fields:
<strong> <code>id</code>                - The unique ID for the textbox.</strong> <code>name</code>          - The name of the textbox field.
<strong> <code>class</code>         - The CSS classname.</strong> <code>placeholder</code>   - Placeholder text.
** <code>value</code>         - The default value of the textbox.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Constructors</h4>
          <section id="button">
            <a name="//apple_ref/cpp/Constructor/button" class="dashAnchor"></a>
            <h5><a href="#button">button</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.web.ui.button(params) -&gt; cp.web.html</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Generates a HTML Button</p>
<p>Parameters:</p>
<ul>
<li><code>params</code>     - Table containing the data you want to display on the button.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A <code>cp.web.ui</code> representing the button.</li>
</ul>
<p>Notes:</p>
<ul>
<li>The <code>params</code> can contain the following fields:
<strong> <code>value</code>     - The value of the button.</strong> <code>label</code>     - The text label for the button. Defaults to the <code>value</code> if not provided.
** <code>width</code>     - The width of the button in pixels.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="checkbox">
            <a name="//apple_ref/cpp/Constructor/checkbox" class="dashAnchor"></a>
            <h5><a href="#checkbox">checkbox</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.web.ui.checkbox(params) -&gt; cp.web.html</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Generates a HTML Checkbox element.</p>
<p>Parameters:</p>
<ul>
<li>data         - A table or function returning a table with the checkbox data.</li>
</ul>
<p>Returns:</p>
<ul>
<li>The <code>cp.web.ui.element</code>.</li>
</ul>
<p>Notes:</p>
<ul>
<li>The <code>params</code> table has the following supported fields:
<strong> <code>value</code>     - a string (or function) with the value of the checkbox. If not specified, the title is used.</strong> <code>checked</code>   - a boolean (or function) set to <code>true</code> or <code>false</code>, depending on if the checkbox is checked.
<strong> <code>disabled</code>  - a boolean (or function) set to <code>true</code> or <code>false</code>, depending on if the checkbox is disabled.</strong> <code>id</code>        - (optional) a string (or function) with the unique ID for the checkbox.
<strong> <code>name</code>      - (optional) a unique name for the checkbox field.</strong> <code>class</code>     - (optional) the CSS class list.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
