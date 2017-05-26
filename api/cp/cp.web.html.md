# [docs](index.md) » cp.web.html
---

Functions for Generating HTML markup.

This library allows the creation of 'safe' HTML using via code.

Examples:

```lua
local html = require "cp.web.html"
print html.p "Hello world!"								-- "<p>Hello world!</p>"
print html.p { class = "custom" } "Hello world!"		-- "<p class='custom'>Hello world!</p>"
print html.p { class = "custom" } (
	html.b "Bold" .. " and " .. html.i "italic" .. "."
)
-- "<p class='custom'><b>Bold</b> and <i>italic</i>.</p>"
print html("1 < 2")										-- "1 &lt; 2" (escaped)
print html("1 < 2", true)								-- "1 < 2" (unescaped)
print html.p ("<b>bold</b>", true)						-- "<p><b>bold</b></p>"
```

Be aware that concatonating with ".." can behave unexpectedly in some cases. For example:

```lua
local name = "world!"
print html.p "Hello " .. name					-- "<p>Hello </p>world!"
```

The `"Hello"` gets inserted into the `p` tag, but the `name` gets concatonated after the closing tag.
To get the `name` inside the `p` tag, we need to put brackets around the content:

```lua
print html.p ("Hello " .. name)					-- "<p>Hello world!</p>"
```

Any tag name can be generated, along with any attribute. The results are correctly escaped.
There are two 'special' tag names:
 * `CDATA`	- will generate a `&lt;![CDATA[ ... ]]&gt;` section with the content contained.
 * `__`		- (double underscore) will generate a `&lt!-- ... --&gt` comment block.

## API Overview

## API Documentation

