# lua-resty-template

**lua-resty-template** is a compiling (1) (HTML) templating engine for Lua and OpenResty.

(1) with compilation we mean that templates are translated to Lua functions that you may call or `string.dump` as a binary bytecode blobs to disk that can be later utilized with `lua-resty-template` or basic `load` and `loadfile` standard Lua functions (see also [Template Precompilation](#template-precompilation)). Although, generally you don't need to do that as `lua-resty-template` handles this behind the scenes.

## Hello World with lua-resty-template

```lua
local template = require "resty.template"
-- Using template.new
local view = template.new "view.html"
view.message = "Hello, World!"
view:render()
-- Using template.render
template.render("view.html", { message = "Hello, World!" })
```

##### view.html
```html
<!DOCTYPE html>
<html>
<body>
  <h1>{{message}}</h1>
</body>
</html>
```

##### Output
```html
<!DOCTYPE html>
<html>
<body>
  <h1>Hello, World!</h1>
</body>
</html>
```

The same can be done with inline template string:

```lua
-- Using template string
template.render([[
<!DOCTYPE html>
<html>
<body>
  <h1>{{message}}</h1>
</body>
</html>]], { message = "Hello, World!" })
```