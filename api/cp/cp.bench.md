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
      <h1><a href="cp.bench.md">docs</a> &raquo; cp.bench</h1>
      <p>Benchmarking Tool.</p>
<p>TIME FUNCTION EXECUTION:
Use this to benchmark sections of code. Wrap them in a function inside this
function call. Eg:</p>
<p>local _bench = require("hs.bench")</p>
<p>local foo = _bench("Foo Test", function()
    return do.somethingHere()
end) --_bench</p>
<p>You can also benchmark all (or some) of the functions on a table in one hit
by using the 'bench.press' function:</p>
<p>local mod = { ... }
-- All functions are benchmarked
mod = _bench.press("mymod", mod)
-- Just the "foo" and "bar" functions are benchmarked.
mod = _bench.press("mymod", mod, {"foo", "bar"})</p>

      </header>
      <h3>API Overview</h3>
      <ul>
      </ul>
      <h3>API Documentation</h3>
