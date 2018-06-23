# [docs](index.md) » cp.plist.plistParser
---

plistParser (https://codea.io/talk/discussion/1269/code-plist-parser)
version 1.01

based on an XML parser by Roberto Ierusalimschy at:
lua-users.org/wiki/LuaXml

Takes a string-ified .plist file as input, and outputs
a table. Nested dictionaries and arrays are parsed into
subtables. Table structure will match the structure of
the .plist file

Usage:
```lua
local plistStr = <string-ified plist file>
local plistTable = plistParse(plistStr)
```

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
