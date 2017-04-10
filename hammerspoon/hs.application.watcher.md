# Hammerspoon docs: hs.application.watcher

Watch for application launch/terminate events

This module is based primarily on code from the previous incarnation of Mjolnir by [Markus Engelbrecht](https://github.com/mgee) and [Steven Degutis](https://github.com/sdegutis/).

## API Overview
* Constants - Useful values which cannot be changed</li>
  * activated
  * deactivated
  * hidden
  * launched
  * launching
  * terminated
  * unhidden
* Constructors - API calls which return an object, typically one that offers API methods</li>
  * new
* Methods - API calls which can only be made on an object returned by a constructor</li>
  * start
  * stop

## API Documentation

### Constants

#### activated
  * Signature: hs.application.watcher.activated
  * Type: Constant
  * Description: An application has been activated (i.e. given keyboard/mouse focus)

#### deactivated
  * Signature: hs.application.watcher.deactivated
  * Type: Constant
  * Description: An application has been deactivated (i.e. lost keyboard/mouse focus)

#### hidden
  * Signature: hs.application.watcher.hidden
  * Type: Constant
  * Description: An application has been hidden

#### launched
  * Signature: hs.application.watcher.launched
  * Type: Constant
  * Description: An application has been launched

#### launching
  * Signature: hs.application.watcher.launching
  * Type: Constant
  * Description: An application is in the process of being launched

#### terminated
  * Signature: hs.application.watcher.terminated
  * Type: Constant
  * Description: An application has been terminated

#### unhidden
  * Signature: hs.application.watcher.unhidden
  * Type: Constant
  * Description: An application has been unhidden

### Constructors

#### new
  * Signature: hs.application.watcher.new(fn) -> watcher
  * Type: Constructor
  * Description: Creates an application event watcher
  * Parameters:
     * fn - A function that will be called when application events happen. It should accept three parameters:
      * A string containing the name of the application
      * An event type (see the constants defined above)
      * An `hs.application` object representing the application, or nil if the application couldn't be found
  * Returns:
     * An `hs.application.watcher` object
  * Notes:
     * If the function is called with an event type of `hs.application.watcher.terminated` then the application name parameter will be `nil` and the `hs.application` parameter, will only be useful for getting the UNIX process ID (i.e. the PID) of the application

### Methods

#### start
  * Signature: hs.application.watcher:start()
  * Type: Method
  * Description: Starts the application watcher
  * Parameters:
     * None
  * Returns:
     * The `hs.application.watcher` object

#### stop
  * Signature: hs.application.watcher:stop()
  * Type: Method
  * Description: Stops the application watcher
  * Parameters:
     * None
  * Returns:
     * The `hs.application.watcher` object
