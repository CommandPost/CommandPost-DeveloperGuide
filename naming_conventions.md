# Naming Conventions

Both Lua and Objective-C portions of an extension/plugin should contain in-line documention of all of the functions they expose to users of the extension/plugin.

The format for docstrings should follow the standard described below.

---

## Documentation Rules

1. Any comment that starts with `---` or `///` is a doc-string (i.e. 3 comment-characters in a row)
2. Doc-strings continue on until a non-docstring line
3. Doc-strings for modules contain `=== my.modulename ===`, then any number of lines describing it
4. Doc-strings for items (functions, variables, etc.) go like this:
   1. The first line starts with `my.modulename.item` or `my.modulename:item` -- this is the item name
   2. Any non-alphanumeric character ends the item name and is ignored, i.e. parentheses or spaces:
      1. `my.modulename:foo()`
      2. `my.modulename:foo(bar) -> string`
      3. `my.modulename.foo(bar, fn(int) -> int)`
      4. `my.modulename.foo = {}`
   3. The second line is a single captitalized word, like "Variable" or "Function" or "Method" or "Constant" or "Field"
   4. The remaining lines describe the item
5. Any comment that starts with 4 comment-characters is ignored
7. Only files ending in `.lua` or `.m` are scanned

## Constants

```lua
--- cp.foo.someConstant
--- Constant
--- This defines the value of a thing
```

## Variables

```lua
--- cp.foo.someVariable
--- Variable
--- This lets you influence the behaviour of this extension
```

## Functions

Note that a function is any API function provided by an extension, which doesn't relate to an object created by the extension.

The `Parameters` and `Returns` sections should always be present. If there is nothing to describe there, simply list `* None`. The `Notes` section is optional and should only be present if there are useful notes.

```lua
--- cp.foo.someFunction(bar[, baz]) -> string or nil
--- Function
--- This is a one-line description of the function
---
--- Parameters:
---  * bar - A value for doing something
---  * baz - Some optional other value. Defaults to 'abc'
---
--- Returns:
---  * A string with some important result, or nil if an error occurred
---
--- Notes:
---  * An important first note
---  * Another important note
```

## Methods

Note that a method is any function provided by an extension which relates to an object created by that extension. They are still technically functions, but the signature is differentiated by the presence of a `:`

The `Parameters` and `Returns` sections should always be present. If there is nothing to describe there, simply list `* None`. The `Notes` section is optional and should only be present if there are useful notes.

```lua
--- cp.foo:someMethod() -> bool
--- Method
--- This is a one-line description of the method
---
--- Parameters:
---  * None
---
--- Returns:
---  * Boolean indicating whether the operation succeeded.
```