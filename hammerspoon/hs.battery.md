# [docs](index.md) » hs.battery
---

Battery/power information
All functions here may return nil, if the information requested is not available.

This module is based primarily on code from the previous incarnation of Mjolnir by [Steven Degutis](https://github.com/sdegutis/).

## Submodules
 * [hs.battery.watcher](hs.battery.watcher.md)

## API Overview
* Functions - API calls offered directly by the extension
* [amperage](#amperage)
* [capacity](#capacity)
* [cycles](#cycles)
* [designCapacity](#designCapacity)
* [getAll](#getAll)
* [health](#health)
* [healthCondition](#healthCondition)
* [isCharged](#isCharged)
* [isCharging](#isCharging)
* [isFinishingCharge](#isFinishingCharge)
* [maxCapacity](#maxCapacity)
* [name](#name)
* [percentage](#percentage)
* [powerSource](#powerSource)
* [psuSerial](#psuSerial)
* [timeRemaining](#timeRemaining)
* [timeToFullCharge](#timeToFullCharge)
* [voltage](#voltage)
* [watts](#watts)

## API Documentation

### Functions

#### [amperage](#amperage)
| Signature   | hs.battery.amperage() -> number  |
| Type        | Function |
| Description | Returns the amount of current flowing through the battery, in mAh |
| Parameters |  * None | | Returns |  * A number containing the amount of current flowing through the battery. The value may be:  * Less than zero if the battery is being discharged (i.e. the computer is running on battery power)  * Zero if the battery is being neither charged nor discharged  * Greater than zero if the battery is being charged | 
#### [capacity](#capacity)
| Signature   | hs.battery.capacity() -> number  |
| Type        | Function |
| Description | Returns the current capacity of the battery in mAh |
| Parameters |  * None | | Returns |  * A number containing the current capacity of the battery in mAh | | Notes |  * This is the measure of how charged the battery is, vs the value of `hs.battery.maxCapacity()` | 
#### [cycles](#cycles)
| Signature   | hs.battery.cycles() -> number  |
| Type        | Function |
| Description | Returns the number of discharge cycles of the battery |
| Parameters |  * None | | Returns |  * The number of cycles | | Notes |  * One cycle is a full discharge of the battery, followed by a full charge. This may also be an aggregate of many smaller discharge-then-charge cycles (e.g. 10 iterations of discharging the battery from 100% to 90% and then charging back to 100% each time, is considered to be one cycle) | 
#### [designCapacity](#designCapacity)
| Signature   | hs.battery.designCapacity() -> number  |
| Type        | Function |
| Description | Returns the design capacity of the battery in mAh. |
| Parameters |  * None | | Returns |  * A number containing the rated maximum capacity of the battery | 
#### [getAll](#getAll)
| Signature   | hs.battery.getAll() -> table  |
| Type        | Function |
| Description | Get all available battery information |
| Parameters |  * None | | Returns |  * A table containing all the information provided by the separate functions in hs.battery | | Notes |  * If you require multiple pieces of information about a battery, this function may be more efficient than calling several other functions separately | 
#### [health](#health)
| Signature   | hs.battery.health() -> string  |
| Type        | Function |
| Description | Returns the health status of the battery. |
| Parameters |  * None | | Returns |  * A string containing one of {Good, Fair, Poor}, as determined by the Apple Smart Battery controller | 
#### [healthCondition](#healthCondition)
| Signature   | hs.battery.healthCondition() -> string or nil  |
| Type        | Function |
| Description | Returns the health condition status of the battery. |
| Parameters |  * None | | Returns |  * Nil if there are no health conditions to report, or a string containing either:  * "Check Battery"  * "Permanent Battery Failure" | 
#### [isCharged](#isCharged)
| Signature   | hs.battery.isCharged() -> boolean  |
| Type        | Function |
| Description | Returns the charged state of the battery |
| Parameters |  * None | | Returns |  * True if the battery is charged, false if not | 
#### [isCharging](#isCharging)
| Signature   | hs.battery.isCharging() -> boolean  |
| Type        | Function |
| Description | Returns the charging state of the battery |
| Parameters |  * None | | Returns |  * True if the battery is being charged, false if not | 
#### [isFinishingCharge](#isFinishingCharge)
| Signature   | hs.battery.isFinishingCharge() -> boolean or string  |
| Type        | Function |
| Description | Returns true if battery is finishing its charge |
| Parameters |  * None | | Returns |  * True if the battery is in its final charging state (i.e. trickle charging), false if not, or "n/a" if the battery is not charging at all | 
#### [maxCapacity](#maxCapacity)
| Signature   | hs.battery.maxCapacity() -> number  |
| Type        | Function |
| Description | Returns the maximum capacity of the battery in mAh |
| Parameters |  * None | | Returns |  * A number containing the observed maximum capacity of the battery in mAh | | Notes |  * This may exceed the value of `hs.battery.designCapacity()` due to small variations in the production chemistry vs the design | 
#### [name](#name)
| Signature   | hs.battery.name() -> string  |
| Type        | Function |
| Description | Returns the name of the battery |
| Parameters |  * None | | Returns |  * A string containing the name of the battery | 
#### [percentage](#percentage)
| Signature   | hs.battery.percentage() -> number  |
| Type        | Function |
| Description | Returns the current percentage of battery charge |
| Parameters |  * None | | Returns |  * A number containing the percentage of battery charge | 
#### [powerSource](#powerSource)
| Signature   | hs.battery.powerSource() -> string  |
| Type        | Function |
| Description | Returns current source of power |
| Parameters |  * None | | Returns |  * A string containing one of {AC Power, Battery Power, Off Line}. | 
#### [psuSerial](#psuSerial)
| Signature   | hs.battery.psuSerial() -> integer  |
| Type        | Function |
| Description | Returns the serial number of the attached power supply, if present |
| Parameters |  * None | | Returns |  * An integer containing the power supply's serial number, or 0 if no serial can be found | 
#### [timeRemaining](#timeRemaining)
| Signature   | hs.battery.timeRemaining() -> number  |
| Type        | Function |
| Description | Returns the battery life remaining, in minutes |
| Parameters |  * None | | Returns |  * A number containing the minutes of battery life remaining. The value may be:  * Greater than zero to indicate the number of minutes remaining  * -1 if the remaining battery life is still being calculated  * -2 if there is unlimited time remaining (i.e. the system is on AC power) | 
#### [timeToFullCharge](#timeToFullCharge)
| Signature   | hs.battery.timeToFullCharge() -> number  |
| Type        | Function |
| Description | Returns the time remaining for the battery to be fully charged, in minutes |
| Parameters |  * None | | Returns |  * A number containing the time (in minutes) remaining for the battery to be fully charged, or -1 if the remaining time is still being calculated | 
#### [voltage](#voltage)
| Signature   | hs.battery.voltage() -> number  |
| Type        | Function |
| Description | Returns the current voltage of the battery in mV |
| Parameters |  * None | | Returns |  * A number containing the current voltage of the battery | 
#### [watts](#watts)
| Signature   | hs.battery.watts() -> number  |
| Type        | Function |
| Description | Returns the power entering or leaving the battery, in W |
| Parameters |  * None | | Returns |  * A number containing the rate of energy conversion in the battery. The value may be:  * Less than zero if the battery is being discharged (i.e. the computer is running on battery power)  * Zero if the battery is being neither charged nor discharged  * Greater than zero if the battery is being charged | 