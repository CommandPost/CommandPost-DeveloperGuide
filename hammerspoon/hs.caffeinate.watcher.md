# Hammerspoon docs: hs.caffeinate.watcher

Watch for display and system sleep/wake/power events
and for fast user switching session events.

This module is based primarily on code from the previous incarnation of Mjolnir by [Steven Degutis](https://github.com/sdegutis/).

## API Overview
* Constants - Useful values which cannot be changed</li>
  * screensDidLock
  * screensDidSleep
  * screensDidUnlock
  * screensDidWake
  * screensaverDidStart
  * screensaverDidStop
  * screensaverWillStop
  * sessionDidBecomeActive
  * sessionDidResignActive
  * systemDidWake
  * systemWillPowerOff
  * systemWillSleep
* Constructors - API calls which return an object, typically one that offers API methods</li>
  * new
* Methods - API calls which can only be made on an object returned by a constructor</li>
  * start
  * stop

## API Documentation

### Constants

#### screensDidLock
  * Signature: hs.caffeinate.watcher.screensDidLock
  * Type: Constant
  * Description: The screen was locked

#### screensDidSleep
  * Signature: hs.caffeinate.watcher.screensDidSleep
  * Type: Constant
  * Description: The displays have gone to sleep

#### screensDidUnlock
  * Signature: hs.caffeinate.watcher.screensDidUnlock
  * Type: Constant
  * Description: The screen was unlocked

#### screensDidWake
  * Signature: hs.caffeinate.watcher.screensDidWake
  * Type: Constant
  * Description: The displays have woken from sleep

#### screensaverDidStart
  * Signature: hs.caffeinate.watcher.screensaverDidStart
  * Type: Constant
  * Description: The screensaver started

#### screensaverDidStop
  * Signature: hs.caffeinate.watcher.screensaverDidStop
  * Type: Constant
  * Description: The screensaver stopped

#### screensaverWillStop
  * Signature: hs.caffeinate.watcher.screensaverWillStop
  * Type: Constant
  * Description: The screensaver is about to stop

#### sessionDidBecomeActive
  * Signature: hs.caffeinate.watcher.sessionDidBecomeActive
  * Type: Constant
  * Description: The session became active, due to fast user switching

#### sessionDidResignActive
  * Signature: hs.caffeinate.watcher.sessionDidResignActive
  * Type: Constant
  * Description: The session is no longer active, due to fast user switching

#### systemDidWake
  * Signature: hs.caffeinate.watcher.systemDidWake
  * Type: Constant
  * Description: The system woke from sleep

#### systemWillPowerOff
  * Signature: hs.caffeinate.watcher.systemWillPowerOff
  * Type: Constant
  * Description: The user requested a logout or shutdown

#### systemWillSleep
  * Signature: hs.caffeinate.watcher.systemWillSleep
  * Type: Constant
  * Description: The system is preparing to sleep

### Constructors

#### new
  * Signature: hs.caffeinate.watcher.new(fn) -> watcher
  * Type: Constructor
  * Description: Creates a watcher object for system and display sleep/wake/power events
  * Parameters:
     * fn - A function that will be called when system/display events happen. It should accept one parameter:
      * An event type (see the constants defined above)
  * Returns:
     * An `hs.caffeinate.watcher` object

### Methods

#### start
  * Signature: hs.caffeinate.watcher:start()
  * Type: Method
  * Description: Starts the sleep/wake watcher
  * Parameters:
     * None
  * Returns:
     * An `hs.caffeinate.watcher` object

#### stop
  * Signature: hs.caffeinate.watcher:stop()
  * Type: Method
  * Description: Stops the sleep/wake watcher
  * Parameters:
     * None
  * Returns:
     * An `hs.caffeinate.watcher` object
