# [docs](index.md) » hs.pathwatcher
---

Watch paths recursively for changes

This simple example watches your Hammerspoon directory for changes, and when it sees a change, reloads your configs:

    local myWatcher = hs.pathwatcher.new(os.getenv("HOME") .. "/.hammerspoon/", hs.reload):start()

This module is based primarily on code from the previous incarnation of Mjolnir by [Steven Degutis](https://github.com/sdegutis/).

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
* [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
* [start](#start)
* [stop](#stop)

## API Documentation

### Constructors

#### [new](#new)
| Signature   | hs.pathwatcher.new(path, fn) -> watcher  |
| Type        | Constructor |
| Description | Creates a new path watcher object |
| Parameters |  * path - A string containing the path to be watched * fn - A function to be called when changes are detected. It should accept a single argument, a table containing a list of files that have changed | | Returns |  * An `hs.pathwatcher` object | 
### Methods

#### [start](#start)
| Signature   | hs.pathwatcher:start()  |
| Type        | Method |
| Description | Starts a path watcher |
| Parameters |  * None | | Returns |  * The `hs.pathwatcher` object | 
#### [stop](#stop)
| Signature   | hs.pathwatcher:stop()  |
| Type        | Method |
| Description | Stops a path watcher |
| Parameters |  * None | | Returns |  * None | 