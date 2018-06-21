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
      <h1><a href="cp.ui.Table.md">docs</a> &raquo; cp.ui.Table</h1>
      <p>Represents an AXTable in the Apple Accessibility UX API.</p>

      </header>
      <h3>API Overview</h3>
      <ul>
        <li>Functions - API calls offered directly by the extension</li>
          <ul>
            <li><a href="#cellTextValue">cellTextValue</a></li>
            <li><a href="#cellTextValueIs">cellTextValueIs</a></li>
            <li><a href="#discloseRow">discloseRow</a></li>
            <li><a href="#findRow">findRow</a></li>
            <li><a href="#is">is</a></li>
            <li><a href="#matches">matches</a></li>
            <li><a href="#matchesContent">matchesContent</a></li>
            <li><a href="#visitRow">visitRow</a></li>
          </ul>
        <li>Constructors - API calls which return an object, typically one that offers API methods</li>
          <ul>
            <li><a href="#new">new</a></li>
          </ul>
        <li>Methods - API calls which can only be made on an object returned by a constructor</li>
          <ul>
            <li><a href="#columnsUI">columnsUI</a></li>
            <li><a href="#deselectAll">deselectAll</a></li>
            <li><a href="#deselectRow">deselectRow</a></li>
            <li><a href="#deselectRowAt">deselectRowAt</a></li>
            <li><a href="#findCellUI">findCellUI</a></li>
            <li><a href="#findColumnIndex">findColumnIndex</a></li>
            <li><a href="#loadLayout">loadLayout</a></li>
            <li><a href="#parent">parent</a></li>
            <li><a href="#rowsUI">rowsUI</a></li>
            <li><a href="#saveLayout">saveLayout</a></li>
            <li><a href="#selectAll">selectAll</a></li>
            <li><a href="#selectedRowsUI">selectedRowsUI</a></li>
            <li><a href="#selectRow">selectRow</a></li>
            <li><a href="#selectRowAt">selectRowAt</a></li>
            <li><a href="#showRow">showRow</a></li>
            <li><a href="#showRowAt">showRowAt</a></li>
            <li><a href="#topRowsUI">topRowsUI</a></li>
            <li><a href="#uncached">uncached</a></li>
            <li><a href="#viewFrame">viewFrame</a></li>
          </ul>
      </ul>
      <h3>API Documentation</h3>
        <h4 class="documentation-section">Functions</h4>
          <section id="cellTextValue">
            <a name="//apple_ref/cpp/Function/cellTextValue" class="dashAnchor"></a>
            <h5><a href="#cellTextValue">cellTextValue</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Table.cellTextValue(cell) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the cell's text value.</p>
<p>Parameters:</p>
<ul>
<li><code>cell</code>   - The cell to check</li>
</ul>
<p>Returns:</p>
<ul>
<li>The combined text value of the cell.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="cellTextValueIs">
            <a name="//apple_ref/cpp/Function/cellTextValueIs" class="dashAnchor"></a>
            <h5><a href="#cellTextValueIs">cellTextValueIs</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Table.cellTextValueIs(cell, value) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks if the cell's text value equals <code>value</code>.</p>
<p>Parameters:</p>
<ul>
<li><code>cell</code>   - The cell to check</li>
<li><code>value</code>  - The text value to compare.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the cell text value equals the provided <code>value</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="discloseRow">
            <a name="//apple_ref/cpp/Function/discloseRow" class="dashAnchor"></a>
            <h5><a href="#discloseRow">discloseRow</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Table.discloseRow(row) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Discloses the row, if possible.</p>
<p>Parameters:</p>
<ul>
<li><code>row</code>        - The row to disclose</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the row is disclosable and is now expanded.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="findRow">
            <a name="//apple_ref/cpp/Function/findRow" class="dashAnchor"></a>
            <h5><a href="#findRow">findRow</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Table.findRow(rows, names) -&gt; axuielement</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Finds the row at the sub-level named in the <code>names</code> table and returns it.</p>
<p>Parameters:</p>
<ul>
<li><code>rows</code>       - The array of rows to process.</li>
<li><code>names</code>      - The array of names to navigate down</li>
</ul>
<p>Returns:</p>
<ul>
<li>The row that was visited, or <code>nil</code> if not.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="is">
            <a name="//apple_ref/cpp/Function/is" class="dashAnchor"></a>
            <h5><a href="#is">is</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Table.is(thing) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks if the <code>thing</code> is a <code>Table</code>.</p>
<p>Parameters:</p>
<ul>
<li><code>thing</code>      - The thing to check</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the thing is a <code>Table</code> instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="matches">
            <a name="//apple_ref/cpp/Function/matches" class="dashAnchor"></a>
            <h5><a href="#matches">matches</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Table.matches(element)</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks if the element is a valid table.</p>
<p>Parameters:</p>
<ul>
<li><code>element</code>    - The element to check.</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if it matches.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="matchesContent">
            <a name="//apple_ref/cpp/Function/matchesContent" class="dashAnchor"></a>
            <h5><a href="#matchesContent">matchesContent</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Table.matchesContent(element) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Checks if the <code>element</code> is a valid table content element.</p>
<p>Parameters:</p>
<ul>
<li><code>element</code>    - The element to check</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if the element is a valid content element.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="visitRow">
            <a name="//apple_ref/cpp/Function/visitRow" class="dashAnchor"></a>
            <h5><a href="#visitRow">visitRow</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Table.visitRow(rows, names) -&gt; axuielement</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Function</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Selects the row at the sub-level named in the <code>names</code> table.</p>
<p>Parameters:</p>
<ul>
<li><code>rows</code>       - The array of rows to process.</li>
<li><code>names</code>      - The array of names to navigate down</li>
</ul>
<p>Returns:</p>
<ul>
<li>The row that was visited, or <code>nil</code> if not.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Constructors</h4>
          <section id="new">
            <a name="//apple_ref/cpp/Constructor/new" class="dashAnchor"></a>
            <h5><a href="#new">new</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Table.new(parent, finder) -&gt; self</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Constructor</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Creates a new Table.</p>
<p>Parameters:</p>
<ul>
<li><code>parent</code>     - The parent object.</li>
<li><code>finder</code>     - A function which will return the <code>axuielement</code> that this table represents.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A new <code>Table</code> instance.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
        <h4 class="documentation-section">Methods</h4>
          <section id="columnsUI">
            <a name="//apple_ref/cpp/Method/columnsUI" class="dashAnchor"></a>
            <h5><a href="#columnsUI">columnsUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Table:columnsUI() -&gt; table of axuielements | nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Return a list of column headers, if present.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>Table of column headers. If the table is visible but no column headers are defined, an empty table is returned. If it's not visible, <code>nil</code> is returned.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="deselectAll">
            <a name="//apple_ref/cpp/Method/deselectAll" class="dashAnchor"></a>
            <h5><a href="#deselectAll">deselectAll</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Table:deselectAll(rowUI) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Deselects the specified rows. If <code>rowsUI</code> is <code>nil</code>, then all rows will be deselected.</p>
<p>Parameters:</p>
<ul>
<li>rowUI - A table of <code>hs._asm.axuielement</code> objects for the rows you want to deselect.</li>
</ul>
<p>Return:</p>
<ul>
<li><code>true</code> if successful, otherwise <code>false</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="deselectRow">
            <a name="//apple_ref/cpp/Method/deselectRow" class="dashAnchor"></a>
            <h5><a href="#deselectRow">deselectRow</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Table:deselectRow(rowUI) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Deselect a specific row.</p>
<p>Parameters:</p>
<ul>
<li>rowUI - The <code>hs._asm.axuielement</code> object of the row you want to deselect.</li>
</ul>
<p>Return:</p>
<ul>
<li><code>true</code> if successful, otherwise <code>false</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="deselectRowAt">
            <a name="//apple_ref/cpp/Method/deselectRowAt" class="dashAnchor"></a>
            <h5><a href="#deselectRowAt">deselectRowAt</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Table:deselectRowAt(index) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Deselects a row at a specific index.</p>
<p>Parameters:</p>
<ul>
<li>index - The index of the row you wish to deselect.</li>
</ul>
<p>Return:</p>
<ul>
<li><code>true</code> if successful, otherwise <code>false</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="findCellUI">
            <a name="//apple_ref/cpp/Method/findCellUI" class="dashAnchor"></a>
            <h5><a href="#findCellUI">findCellUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Table:findCellUI(rowNumber, columnId) -&gt; <code>hs._asm.axuielement</code> | nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Finds a specific Cell UI.</p>
<p>Parameters:</p>
<ul>
<li>rowNumber - The row number.</li>
<li>columnId - The Column ID.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A <code>hs._asm.axuielement</code> object for the cell, or <code>nil</code> if the cell cannot be found.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="findColumnIndex">
            <a name="//apple_ref/cpp/Method/findColumnIndex" class="dashAnchor"></a>
            <h5><a href="#findColumnIndex">findColumnIndex</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Table:findColumnIndex(id) -&gt; number | nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Finds the Column Index based on an <code>AXIdentifier</code> ID.</p>
<p>Parameters:</p>
<ul>
<li>id - The <code>AXIdentifier</code> of the column index you want to find.</li>
</ul>
<p>Returns:</p>
<ul>
<li>A column index as a number, or <code>nil</code> if no index can be found.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="loadLayout">
            <a name="//apple_ref/cpp/Method/loadLayout" class="dashAnchor"></a>
            <h5><a href="#loadLayout">loadLayout</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Table:loadLayout(layout) -&gt; none</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Loads a Table layout.</p>
<p>Parameters:</p>
<ul>
<li>layout - A table containing the Table layout settings - created using <code>cp.ui.Table:saveLayout()</code>.</li>
</ul>
<p>Returns:</p>
<ul>
<li>None</li>
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
                <td><code>cp.ui.Table:parent() -&gt; value</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>The table's parent, as provided in the constructor.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>The table's parent.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="rowsUI">
            <a name="//apple_ref/cpp/Method/rowsUI" class="dashAnchor"></a>
            <h5><a href="#rowsUI">rowsUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Table:rowsUI([filterFn]) -&gt; table of axuielements | nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the list of rows in the table. An optional filter function may be provided.
It will be passed a single <code>AXRow</code> element and should return <code>true</code> if the row should be included.</p>
<p>Parameters:</p>
<ul>
<li><code>filterFn</code>   - An optional function that will be called to check if individual rows should be included. If not provided, all rows are returned.</li>
</ul>
<p>Returns:</p>
<ul>
<li>Table of rows. If the table is visible but no rows match, it will be an empty table, otherwise it will be <code>nil</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="saveLayout">
            <a name="//apple_ref/cpp/Method/saveLayout" class="dashAnchor"></a>
            <h5><a href="#saveLayout">saveLayout</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Table:saveLayout() -&gt; table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Saves the current Table layout to a table.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>A table containing the current Table Layout.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="selectAll">
            <a name="//apple_ref/cpp/Method/selectAll" class="dashAnchor"></a>
            <h5><a href="#selectAll">selectAll</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Table:selectAll(rowUI) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Selects the specified rows. If <code>rowsUI</code> is <code>nil</code>, then all rows will be selected.</p>
<p>Parameters:</p>
<ul>
<li>rowUI - A table of <code>hs._asm.axuielement</code> objects for the rows you want to select.</li>
</ul>
<p>Return:</p>
<ul>
<li><code>true</code> if successful, otherwise <code>false</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="selectedRowsUI">
            <a name="//apple_ref/cpp/Method/selectedRowsUI" class="dashAnchor"></a>
            <h5><a href="#selectedRowsUI">selectedRowsUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Table:selectedRowsUI() -&gt; table of axuielements | nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Return a table of selected row UIs.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>Table of <code>hs._asm.axuielement</code> objects, or <code>nil</code> if none could be found.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="selectRow">
            <a name="//apple_ref/cpp/Method/selectRow" class="dashAnchor"></a>
            <h5><a href="#selectRow">selectRow</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Table:selectRow(rowUI) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Select a specific row.</p>
<p>Parameters:</p>
<ul>
<li>rowUI - The <code>hs._asm.axuielement</code> object of the row you want to select.</li>
</ul>
<p>Return:</p>
<ul>
<li><code>true</code> if successful, otherwise <code>false</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="selectRowAt">
            <a name="//apple_ref/cpp/Method/selectRowAt" class="dashAnchor"></a>
            <h5><a href="#selectRowAt">selectRowAt</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Table:selectRowAt(index) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Select a row at a specific index.</p>
<p>Parameters:</p>
<ul>
<li>index - The index of the row you wish to select.</li>
</ul>
<p>Return:</p>
<ul>
<li><code>true</code> if successful, otherwise <code>false</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="showRow">
            <a name="//apple_ref/cpp/Method/showRow" class="dashAnchor"></a>
            <h5><a href="#showRow">showRow</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Table:showRow(rowUI) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Shows a specific row.</p>
<p>Parameters:</p>
<ul>
<li>rowUI - The <code>hs._asm.axuielement</code> object of the row you want to show.</li>
</ul>
<p>Return:</p>
<ul>
<li><code>true</code> if successful, otherwise <code>false</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="showRowAt">
            <a name="//apple_ref/cpp/Method/showRowAt" class="dashAnchor"></a>
            <h5><a href="#showRowAt">showRowAt</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Table:showRowAt(index) -&gt; boolean</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Shows a row at a specific index.</p>
<p>Parameters:</p>
<ul>
<li>index - The index of the row you wish to show.</li>
</ul>
<p>Return:</p>
<ul>
<li><code>true</code> if successful, otherwise <code>false</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="topRowsUI">
            <a name="//apple_ref/cpp/Method/topRowsUI" class="dashAnchor"></a>
            <h5><a href="#topRowsUI">topRowsUI</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Table:topRowsUI(filterFn) -&gt; table of axuielements | nil</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns a list of top-level rows in the table. An optional filter function may be provided.
It will be passed a single <code>AXRow</code> element and should return <code>true</code> if the row should be included.</p>
<p>Parameters:</p>
<ul>
<li><code>filterFn</code>   - An optional function that will be called to check if individual rows should be included. If not provided, all rows are returned.</li>
</ul>
<p>Returns:</p>
<ul>
<li>Table of rows. If the table is visible but no rows match, it will be an empty table, otherwise it will be <code>nil</code>.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="uncached">
            <a name="//apple_ref/cpp/Method/uncached" class="dashAnchor"></a>
            <h5><a href="#uncached">uncached</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Table:uncached() -&gt; Table</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Calling this will force the table to look up the <code>axuielement</code> on demand, rather than caching the result.</p>
<p>Parameters:</p>
<ul>
<li><p>None</p>
</li>
<li><p>The same <code>Table</code>, now uncached..</p>
</li>
</ul>
</td>
              </tr>
            </table>
          </section>
          <section id="viewFrame">
            <a name="//apple_ref/cpp/Method/viewFrame" class="dashAnchor"></a>
            <h5><a href="#viewFrame">viewFrame</a></h5>
            <table>
              <tr>
                <th>Signature</th>
                <td><code>cp.ui.Table:viewFrame() -&gt; hs.geometry rect</code></td>
              </tr>
              <tr>
                <th>Type</th>
                <td>Method</td>
              </tr>
              <tr>
                <th>Description</th>
                <td><p>Returns the Table frame.</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Return:</p>
<ul>
<li>The frame in the form of a <code>hs.geometry</code> rect object.</li>
</ul>
</td>
              </tr>
            </table>
          </section>
