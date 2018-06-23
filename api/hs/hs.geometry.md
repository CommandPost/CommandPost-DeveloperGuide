# [docs](index.md) » hs.geometry
---

Utility object to represent points, sizes and rects in a bidimensional plane

An hs.geometry object can be:
 * a *point*, or vector2, with `x` and `y` fields for its coordinates
 * a *size* with `w` and `h` fields for width and height respectively
 * a *rect*, which has both a point component for one of its corners, and a size component - so it has all 4 fields
 * a *unit rect*, which is a rect with all fields between 0 and 1; it represents a "relative" rect within another (absolute) rect
   (e.g. a unit rect `x=0,y=0 , w=0.5,h=0.5` is the quarter portion closest to the origin); please note that hs.geometry
   makes no distinction internally between regular rects and unit rects; you can convert to and from as needed via the appropriate methods

You can create these objects in many different ways, via `my_obj=hs.geometry.new(...)` or simply `my_obj=hs.geometry(...)`
by passing any of the following:
 * 4 parameters `X,Y,W,H` for the respective fields - W and H, or X and Y, can be `nil`:
   * `hs.geometry(X,Y)` creates a point
   * `hs.geometry(nil,nil,W,H)` creates a size
   * `hs.geometry(X,Y,W,H)` creates a rect given its width and height from a corner
 * a table `{X,Y}` creates a point
 * a table `{X,Y,W,H}` creates a rect
 * a table `{x=X,y=Y,w=W,h=H}` creates a rect, or if you omit X and Y, or W and H, creates a size or a point respectively
 * a table `{x1=X1,y1=Y1,x2=X2,y2=Y2}` creates a rect, where X1,Y1 and X2,Y2 are the coordinates of opposite corners
 * a string:
   * `"X Y"` or `"X,Y"` creates a point
   * `"WxH"` or `"W*H"` creates a size
   * `"X Y/WxH"` or `"X,Y W*H"` (or variations thereof) creates a rect given its width and height from a corner
   * `"X1,Y1>X2,Y2"` or `"X1 Y1 X2 Y2"` (or variations thereof) creates a rect given two opposite corners
   * `"[X,Y WxH]"` or `"[X1,Y1 X2,Y2]"` or variations (note the square brackets) creates a unit rect where x=X/100, y=Y/100, w=W/100, h=H/100
 * a point and a size `"X Y","WxH"` or `{x=X,y=Y},{w=W,h=H}` create a rect

You can use any of these anywhere an hs.geometry object is expected in Hammerspoon; the constructor will be called for you.

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
<li>Constructors - API calls which return an object, typically one that offers API methods</li>
  <ul>
	<li><a href="#copy">copy</a></li>
	<li><a href="#new">new</a></li>
	<li><a href="#point">point</a></li>
	<li><a href="#rect">rect</a></li>
	<li><a href="#size">size</a></li>
  </ul>
<li>Fields - Variables which can only be accessed from an object returned by a constructor</li>
  <ul>
	<li><a href="#area">area</a></li>
	<li><a href="#aspect">aspect</a></li>
	<li><a href="#bottomright">bottomright</a></li>
	<li><a href="#center">center</a></li>
	<li><a href="#h">h</a></li>
	<li><a href="#length">length</a></li>
	<li><a href="#string">string</a></li>
	<li><a href="#table">table</a></li>
	<li><a href="#topleft">topleft</a></li>
	<li><a href="#w">w</a></li>
	<li><a href="#wh">wh</a></li>
	<li><a href="#x">x</a></li>
	<li><a href="#x1">x1</a></li>
	<li><a href="#x2">x2</a></li>
	<li><a href="#x2y2">x2y2</a></li>
	<li><a href="#xy">xy</a></li>
	<li><a href="#y">y</a></li>
	<li><a href="#y1">y1</a></li>
	<li><a href="#y2">y2</a></li>
  </ul>
<li>Methods - API calls which can only be made on an object returned by a constructor</li>
  <ul>
	<li><a href="#angle">angle</a></li>
	<li><a href="#angleTo">angleTo</a></li>
	<li><a href="#distance">distance</a></li>
	<li><a href="#equals">equals</a></li>
	<li><a href="#fit">fit</a></li>
	<li><a href="#floor">floor</a></li>
	<li><a href="#fromUnitRect">fromUnitRect</a></li>
	<li><a href="#inside">inside</a></li>
	<li><a href="#intersect">intersect</a></li>
	<li><a href="#move">move</a></li>
	<li><a href="#normalize">normalize</a></li>
	<li><a href="#rotateCCW">rotateCCW</a></li>
	<li><a href="#scale">scale</a></li>
	<li><a href="#toUnitRect">toUnitRect</a></li>
	<li><a href="#type">type</a></li>
	<li><a href="#union">union</a></li>
	<li><a href="#vector">vector</a></li>
  </ul>
</ul>
<h3>API Documentation</h3>
<h4 class="documentation-section">Constructors</h4>
  <section id="copy">
	<h5><a href="#copy">copy</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry.copy(geom) -&gt; hs.geometry object</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constructor</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a copy of an hs.geometry object</p>
<p>Parameters:</p>
<ul>
<li>geom - an hs.geometry object to copy</li>
</ul>
<p>Returns:</p>
<ul>
<li>a newly created copy of the hs.geometry object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="new">
	<h5><a href="#new">new</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry.new(...) -&gt; hs.geometry object</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constructor</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Creates a new hs.geometry object</p>
<p>Parameters: see the module description at the top</p>
<p>Returns:</p>
<ul>
<li>a newly created hs.geometry object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="point">
	<h5><a href="#point">point</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry.point(x, y) -&gt; hs.geometry point</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constructor</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Convenience function for creating a point object</p>
<p>Parameters:</p>
<ul>
<li>x - A number containing the horizontal co-ordinate of the point</li>
<li>y - A number containing the vertical co-ordinate of the point</li>
</ul>
<p>Returns:</p>
<ul>
<li>An hs.geometry point object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="rect">
	<h5><a href="#rect">rect</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry.rect(x, y, w, h) -&gt; hs.geometry rect</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constructor</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Convenience function for creating a rect-table</p>
<p>Parameters:</p>
<ul>
<li>x - A number containing the horizontal co-ordinate of the top-left point of the rect</li>
<li>y - A number containing the vertical co-ordinate of the top-left point of the rect</li>
<li>w - A number containing the width of the rect</li>
<li>h - A number containing the height of the rect</li>
</ul>
<p>Returns:</p>
<ul>
<li>An hs.geometry rect object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="size">
	<h5><a href="#size">size</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry.size(w, h) -&gt; hs.geometry size</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Constructor</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Convenience function for creating a size object</p>
<p>Parameters:</p>
<ul>
<li>w - A number containing a width</li>
<li>h - A number containing a height</li>
</ul>
<p>Returns:</p>
<ul>
<li>An hs.geometry size object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Fields</h4>
  <section id="area">
	<h5><a href="#area">area</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry.area</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>A number representing the area of this rect or size; changing it will scale the rect/size - see <code>hs.geometry:scale()</code></p>
</td>
	  </tr>
	</table>
  </section>
  <section id="aspect">
	<h5><a href="#aspect">aspect</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry.aspect</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>A number representing the aspect ratio of this rect or size; changing it will reshape the rect/size, keeping its area and center constant</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="bottomright">
	<h5><a href="#bottomright">bottomright</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry.bottomright</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Alias for <code>x2y2</code></p>
</td>
	  </tr>
	</table>
  </section>
  <section id="center">
	<h5><a href="#center">center</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry.center</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>A point representing the geometric center of this rect or the midpoint of this vector2; changing it will move the rect/vector accordingly</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="h">
	<h5><a href="#h">h</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry.h</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The height of this rect or size; changing it will keep the rect's x,y corner constant</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="length">
	<h5><a href="#length">length</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry.length</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>A number representing the length of the diagonal of this rect, or the length of this vector2; changing it will scale the rect/vector - see <code>hs.geometry:scale()</code></p>
</td>
	  </tr>
	</table>
  </section>
  <section id="string">
	<h5><a href="#string">string</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry.string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The <code>"X,Y/WxH"</code> string for this hs.geometry object (<em>reduced precision</em>); useful e.g. for logging</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="table">
	<h5><a href="#table">table</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry.table</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The <code>{x=X,y=Y,w=W,h=H}</code> table for this hs.geometry object; useful e.g. for serialization/deserialization</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="topleft">
	<h5><a href="#topleft">topleft</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry.topleft</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Alias for <code>xy</code></p>
</td>
	  </tr>
	</table>
  </section>
  <section id="w">
	<h5><a href="#w">w</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry.w</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The width of this rect or size; changing it will keep the rect's x,y corner constant</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="wh">
	<h5><a href="#wh">wh</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry.wh</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The size component for this hs.geometry object; setting this to a new size will keep the rect's x,y corner constant</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="x">
	<h5><a href="#x">x</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry.x</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The x coordinate for this point or rect's corner; changing it will move the rect but keep the same width and height</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="x1">
	<h5><a href="#x1">x1</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry.x1</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Alias for <code>x</code></p>
</td>
	  </tr>
	</table>
  </section>
  <section id="x2">
	<h5><a href="#x2">x2</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry.x2</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The x coordinate for the second corner of this rect; changing it will affect the rect's width</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="x2y2">
	<h5><a href="#x2y2">x2y2</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry.x2y2</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The point denoting the other corner of this hs.geometry object; setting this to a new point will change the rect's width and height</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="xy">
	<h5><a href="#xy">xy</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry.xy</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The point component for this hs.geometry object; setting this to a new point will move the rect but keep the same width and height</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="y">
	<h5><a href="#y">y</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry.y</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The y coordinate for this point or rect's corner; changing it will move the rect but keep the same width and height</p>
</td>
	  </tr>
	</table>
  </section>
  <section id="y1">
	<h5><a href="#y1">y1</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry.y1</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Alias for <code>y</code></p>
</td>
	  </tr>
	</table>
  </section>
  <section id="y2">
	<h5><a href="#y2">y2</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry.y2</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Field</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>The y coordinate for the second corner of this rect; changing it will affect the rect's height</p>
</td>
	  </tr>
	</table>
  </section>
<h4 class="documentation-section">Methods</h4>
  <section id="angle">
	<h5><a href="#angle">angle</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry:angle() -&gt; number</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the angle between the positive x axis and this vector2</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>a number represeting the angle in radians</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="angleTo">
	<h5><a href="#angleTo">angleTo</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry:angleTo(point) -&gt; number</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the angle between the positive x axis and the vector connecting this point or rect's center to another point or rect's center</p>
<p>Parameters:</p>
<ul>
<li>point - an hs.geometry object, or a table or string or parameter list to construct one; if a rect, uses the rect's center</li>
</ul>
<p>Returns:</p>
<ul>
<li>a number represeting the angle in radians</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="distance">
	<h5><a href="#distance">distance</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry:distance(point) -&gt; number</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Finds the distance between this point or rect's center and another point or rect's center</p>
<p>Parameters:</p>
<ul>
<li>point - an hs.geometry object, or a table or string or parameter list to construct one; if a rect, uses the rect's center</li>
</ul>
<p>Returns:</p>
<ul>
<li>a number indicating the distance</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="equals">
	<h5><a href="#equals">equals</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry:equals(other) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Checks if two geometry objects are equal</p>
<p>Parameters:</p>
<ul>
<li>other - another hs.geometry object, or a table or string or parameter list to construct one</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if this hs.geometry object perfectly overlaps other, <code>false</code> otherwise</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="fit">
	<h5><a href="#fit">fit</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry:fit(bounds) -&gt; hs.geometry object</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Ensure this rect is fully inside <code>bounds</code>, by scaling it down if it's larger (preserving its aspect ratio) and moving it if necessary</p>
<p>Parameters:</p>
<ul>
<li>bounds - an hs.geometry rect object, or a table or string or parameter list to construct one, indicating the rect that
must fully contain this rect</li>
</ul>
<p>Returns:</p>
<ul>
<li>this hs.geometry object for method chaining</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="floor">
	<h5><a href="#floor">floor</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry:floor() -&gt; hs.geometry object</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Truncates all coordinates in this object to integers</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>this hs.geometry point for method chaining</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="fromUnitRect">
	<h5><a href="#fromUnitRect">fromUnitRect</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry:fromUnitRect(frame) -&gt; hs.geometry rect</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Converts a unit rect within a given frame into a rect</p>
<p>Parameters:</p>
<ul>
<li>frame - an hs.geometry rect (with <code>w</code> and <code>h</code> &gt;0)</li>
</ul>
<p>Returns:</p>
<ul>
<li>An hs.geometry rect object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="inside">
	<h5><a href="#inside">inside</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry:inside(rect) -&gt; boolean</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Checks if this hs.geometry object lies fully inside a given rect</p>
<p>Parameters:</p>
<ul>
<li>rect - an hs.geometry rect, or a table or string or parameter list to construct one</li>
</ul>
<p>Returns:</p>
<ul>
<li><code>true</code> if this point/rect lies fully inside the given rect, <code>false</code> otherwise</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="intersect">
	<h5><a href="#intersect">intersect</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry:intersect(rect) -&gt; hs.geometry rect</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the intersection rect between this rect and another rect</p>
<p>Parameters:</p>
<ul>
<li>rect - an hs.geometry rect, or a table or string or parameter list to construct one</li>
</ul>
<p>Returns:</p>
<ul>
<li>a new hs.geometry rect</li>
</ul>
<p>Notes:</p>
<ul>
<li>If the two rects don't intersect, the result rect will be a "projection" of the second rect onto this rect's
closest edge or corner along the x or y axis; the <code>w</code> and/or <code>h</code> fields in the result rect will be 0.</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="move">
	<h5><a href="#move">move</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry:move(point) -&gt; hs.geometry object</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Moves this point/rect</p>
<p>Parameters:</p>
<ul>
<li>point - an hs.geometry object, or a table or string or parameter list to construct one, indicating the x and y displacement to apply</li>
</ul>
<p>Returns:</p>
<ul>
<li>this hs.geometry object for method chaining</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="normalize">
	<h5><a href="#normalize">normalize</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry:normalize() -&gt; point</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Normalizes this vector2</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>this hs.geometry point for method chaining</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="rotateCCW">
	<h5><a href="#rotateCCW">rotateCCW</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry:rotateCCW(aroundpoint, ntimes) -&gt; hs.geometry point</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Rotates a point around another point N times</p>
<p>Parameters:</p>
<ul>
<li>aroundpoint - an hs.geometry point to rotate this point around</li>
<li>ntimes - the number of times to rotate, defaults to 1</li>
</ul>
<p>Returns:</p>
<ul>
<li>A new hs.geometry point containing the location of the rotated point</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="scale">
	<h5><a href="#scale">scale</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry:scale(size) -&gt; hs.geometry object</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Scales this vector2/size, or this rect <em>keeping its center constant</em></p>
<p>Parameters:</p>
<ul>
<li>size - an hs.geometry object, or a table or string or parameter list to construct one, indicating the factors for scaling this rect's width and height;
if a number, the rect will be scaled by the same factor in both axes</li>
</ul>
<p>Returns:</p>
<ul>
<li>this hs.geometry object for method chaining</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="toUnitRect">
	<h5><a href="#toUnitRect">toUnitRect</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry:toUnitRect(frame) -&gt; hs.geometry unit rect</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Converts a rect into its unit rect within a given frame</p>
<p>Parameters:</p>
<ul>
<li>frame - an hs.geometry rect (with <code>w</code> and <code>h</code> &gt;0)</li>
</ul>
<p>Returns:</p>
<ul>
<li>An hs.geometry unit rect object</li>
</ul>
<p>Notes:</p>
<ul>
<li>The resulting unit rect is always clipped within <code>frame</code>'s bounds (via <code>hs.geometry:intersect()</code>); if <code>frame</code>
does not encompass this rect <em>no error will be thrown</em>, but the resulting unit rect won't be a direct match with this rect
(i.e. calling <code>:fromUnitRect(frame)</code> on it will return a different rect)</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="type">
	<h5><a href="#type">type</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry:type() -&gt; string</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the type of an hs.geometry object</p>
<p>Parameters:</p>
<ul>
<li>None</li>
</ul>
<p>Returns:</p>
<ul>
<li>a string describing the type of this hs.geometry object, i.e. 'point', 'size', 'rect' or 'unitrect'; <code>nil</code> if not a valid object</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="union">
	<h5><a href="#union">union</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry:union(rect) -&gt; hs.geometry rect</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the smallest rect that encloses both this rect and another rect</p>
<p>Parameters:</p>
<ul>
<li>rect - an hs.geometry rect, or a table or string or parameter list to construct one</li>
</ul>
<p>Returns:</p>
<ul>
<li>a new hs.geometry rect</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
  <section id="vector">
	<h5><a href="#vector">vector</a></h5>
	<table>
	  <tr>
		<th>Signature</th>
		<td><code>hs.geometry:vector(point) -&gt; point</code></td>
	  </tr>
	  <tr>
		<th>Type</th>
		<td>Method</td>
	  </tr>
	  <tr>
		<th>Description</th>
		<td><p>Returns the vector2 from this point or rect's center to another point or rect's center</p>
<p>Parameters:</p>
<ul>
<li>point - an hs.geometry object, or a table or string or parameter list to construct one; if a rect, uses the rect's center</li>
</ul>
<p>Returns:</p>
<ul>
<li>an hs.geometry point</li>
</ul>
</td>
	  </tr>
	</table>
  </section>
