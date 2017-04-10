# [docs](index.md) » hs.battery.watcher
---

Watch for battery/power state changes

This module is based primarily on code from the previous incarnation of Mjolnir by [Steven Degutis](https://github.com/sdegutis/).

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
** [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
** [start](#start)
** [stop](#stop)

## API Documentation

### Constructors

#### [new](#new)
| | |
|-|-|
| Signature   | hs.battery.watcher.new(fn) -> watcher  |
| Type        | Constructor |
| Description | Creates a battery watcher |
| Parameters |  * A function that will be called when the battery state changes. The function should accept no arguments. | | Returns |  * An `hs.battery.watcher` object | | Notes |  * Because the callback function accepts no arguments, tracking of state of changing battery attributes is the responsibility of the user (see https://github.com/Hammerspoon/hammerspoon/issues/166 for discussion) | 
### Methods

#### [start](#start)
| | |
|-|-|
| Signature   | hs.battery.watcher:start() -> self  |
| Type        | Method |
| Description | Starts the battery watcher |
| Parameters |  * None | | Returns |  * The `hs.battery.watcher` object | 
#### [stop](#stop)
| | |
|-|-|
| Signature   | hs.battery.watcher:stop() -> self  |
| Type        | Method |
| Description | Stops the battery watcher |
| Parameters |  * None | | Returns |  * The `hs.battery.watcher` object | 