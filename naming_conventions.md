# Naming Conventions

Both Lua and Objective-C portions of an extension should contain in-line documention of all of the functions they expose to users of the extension.

The format for docstrings should follow the standard described below. Note that for Lua files, the lines should begin with `---` and for Objective C files, the lines should begin with `///`.

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