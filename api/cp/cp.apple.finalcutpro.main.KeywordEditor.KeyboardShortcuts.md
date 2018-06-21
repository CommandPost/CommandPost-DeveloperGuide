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
      <h1><a href="cp.apple.finalcutpro.main.KeywordEditor.KeyboardShortcuts.md">docs</a> &raquo; cp.apple.finalcutpro.main.KeywordEditor.KeyboardShortcuts</h1>
      <p>Keyboard Shortcuts</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Constructors - API calls which return an object, typically one that offers API methods</li>
          <ul>
            <li><a href="#new">new</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#apply">apply</a></li>
            <li><a href="#hide">hide</a></li>
            <li><a href="#isShowing">isShowing</a></li>
            <li><a href="#keyword">keyword</a></li>
            <li><a href="#parent">parent</a></li>
            <li><a href="#removeAllKeywords">removeAllKeywords</a></li>
            <li><a href="#show">show</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Constructors</h4>
          <section id="new">
            <a name="//apple_ref/cpp/Constructor/new" class="dashAnchor"></a>
            <h5><a href="#new">new</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.KeywordEditor.KeyboardShortcuts.new(parent) -&gt; KeyboardShortcuts</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new <code>KeyboardShortcuts</code> object</p>
<p>Parameters:</p>
<ul>
<li>parent - The parent object.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A <code>KeyboardShortcuts</code> object</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Methods</h4>
          <section id="apply">
            <a name="//apple_ref/cpp/Method/apply" class="dashAnchor"></a>
            <h5><a href="#apply">apply</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.KeywordEditor.KeyboardShortcuts:apply(item) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Applies a Keyword Shortcut.</p>
<p>Parameters:</p>
<ul>
<li>item - The textbox you want to update. This can be a number between 1 and 9.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successful otherwise <code>false</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="hide">
            <a name="//apple_ref/cpp/Method/hide" class="dashAnchor"></a>
            <h5><a href="#hide">hide</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.KeywordEditor.KeyboardShortcuts:hide() -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Hides the Keyword Editor's Keyboard Shortcuts section.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successful otherwise <code>false</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="isShowing">
            <a name="//apple_ref/cpp/Method/isShowing" class="dashAnchor"></a>
            <h5><a href="#isShowing">isShowing</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.KeywordEditor.KeyboardShortcuts:isShowing() -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Gets whether or not the Keyword Editor's Keyboard Shortcuts section is currently showing.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if showing otherwise <code>false</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="keyword">
            <a name="//apple_ref/cpp/Method/keyword" class="dashAnchor"></a>
            <h5><a href="#keyword">keyword</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.KeywordEditor.KeyboardShortcuts:keyword(item, value) -&gt; string | table | nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Sets or gets a specific Keyboard Shortcut Keyword Textbox value.</p>
<p>Parameters:</p>
<ul>
<li>item - The textbox you want to update. This can be a number between 1 and 9.</li>
<li>value - The value you want to set the keyword textbox to. This can either be a string, with the tags separated by a comma, or a table of tags.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>value</code> if successful otherwise <code>false</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="parent">
            <a name="//apple_ref/cpp/Method/parent" class="dashAnchor"></a>
            <h5><a href="#parent">parent</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.KeywordEditor.KeyboardShortcuts:parent() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the KeywordShortcuts's parent table</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The parent object as a table</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="removeAllKeywords">
            <a name="//apple_ref/cpp/Method/removeAllKeywords" class="dashAnchor"></a>
            <h5><a href="#removeAllKeywords">removeAllKeywords</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.KeywordEditor.KeyboardShortcuts:removeAllKeywords() -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Triggers the "Remove all Keywords" button.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successful otherwise <code>false</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="show">
            <a name="//apple_ref/cpp/Method/show" class="dashAnchor"></a>
            <h5><a href="#show">show</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.apple.finalcutpro.main.KeywordEditor.KeyboardShortcuts:show() -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Shows the Keyword Editor's Keyboard Shortcuts section.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if successful otherwise <code>false</code></li>
</ul>
</td>
              </tr>
            </table>
          </section>
