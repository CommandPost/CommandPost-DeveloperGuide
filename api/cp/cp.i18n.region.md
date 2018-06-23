# [docs](index.md) » cp.i18n.region
---

Provides the set of ISO 3166-1 region codes and names.
The return value can be iterated as a list, or you can find a
specific region by either its upper-case two-character code (`alpha2`), three-character numeric code (`numeric3`),
or English name (`name`).

For example:

```lua
local region = require("cp.i18n.region")
print(region[1])    -- table for "Afghanistan"
print(lang.FR)      -- table for "France"
print(lang.France)  -- same table for "France"
```

This will return a table containing the following:
* `alpha2`      - The 2-character region code, upper-case (eg. "AU", "FR").
* `name`        - The name in English (eg. "Australia", "France").

Note: This data was adapted from the [datahub.io list](https://datahub.io/core/country-list)
released under a Public Domain license.

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
</ul>
<h3>API Documentation</h3>
