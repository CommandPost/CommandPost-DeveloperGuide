# [docs](../hammerspoon/index.md) » hs.battery
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

| [amperage](#amperage)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.battery.amperage() -> number`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the amount of current flowing through the battery, in mAh                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A number containing the amount of current flowing through the battery. The value may be:</li><li> Less than zero if the battery is being discharged (i.e. the computer is running on battery power)</li><li> Zero if the battery is being neither charged nor discharged</li><li> Greater than zero if the battery is being charged</li></ul>          |

| [capacity](#capacity)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.battery.capacity() -> number`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the current capacity of the battery in mAh                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A number containing the current capacity of the battery in mAh</li></ul>          |
| **Notes**                                   | <ul><li>This is the measure of how charged the battery is, vs the value of `hs.battery.maxCapacity()`</li></ul>                |

| [cycles](#cycles)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.battery.cycles() -> number`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the number of discharge cycles of the battery                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The number of cycles</li></ul>          |
| **Notes**                                   | <ul><li>One cycle is a full discharge of the battery, followed by a full charge. This may also be an aggregate of many smaller discharge-then-charge cycles (e.g. 10 iterations of discharging the battery from 100% to 90% and then charging back to 100% each time, is considered to be one cycle)</li></ul>                |

| [designCapacity](#designCapacity)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.battery.designCapacity() -> number`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the design capacity of the battery in mAh.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A number containing the rated maximum capacity of the battery</li></ul>          |

| [getAll](#getAll)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.battery.getAll() -> table`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Get all available battery information                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A table containing all the information provided by the separate functions in hs.battery</li></ul>          |
| **Notes**                                   | <ul><li>If you require multiple pieces of information about a battery, this function may be more efficient than calling several other functions separately</li></ul>                |

| [health](#health)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.battery.health() -> string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the health status of the battery.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A string containing one of {Good, Fair, Poor}, as determined by the Apple Smart Battery controller</li></ul>          |

| [healthCondition](#healthCondition)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.battery.healthCondition() -> string or nil`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the health condition status of the battery.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>Nil if there are no health conditions to report, or a string containing either:</li><li> "Check Battery"</li><li> "Permanent Battery Failure"</li></ul>          |

| [isCharged](#isCharged)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.battery.isCharged() -> boolean`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the charged state of the battery                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>True if the battery is charged, false if not</li></ul>          |

| [isCharging](#isCharging)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.battery.isCharging() -> boolean`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the charging state of the battery                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>True if the battery is being charged, false if not</li></ul>          |

| [isFinishingCharge](#isFinishingCharge)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.battery.isFinishingCharge() -> boolean or string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns true if battery is finishing its charge                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>True if the battery is in its final charging state (i.e. trickle charging), false if not, or "n/a" if the battery is not charging at all</li></ul>          |

| [maxCapacity](#maxCapacity)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.battery.maxCapacity() -> number`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the maximum capacity of the battery in mAh                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A number containing the observed maximum capacity of the battery in mAh</li></ul>          |
| **Notes**                                   | <ul><li>This may exceed the value of `hs.battery.designCapacity()` due to small variations in the production chemistry vs the design</li></ul>                |

| [name](#name)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.battery.name() -> string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the name of the battery                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A string containing the name of the battery</li></ul>          |

| [percentage](#percentage)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.battery.percentage() -> number`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the current percentage of battery charge                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A number containing the percentage of battery charge</li></ul>          |

| [powerSource](#powerSource)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.battery.powerSource() -> string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns current source of power                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A string containing one of {AC Power, Battery Power, Off Line}.</li></ul>          |

| [psuSerial](#psuSerial)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.battery.psuSerial() -> integer`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the serial number of the attached power supply, if present                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>An integer containing the power supply's serial number, or 0 if no serial can be found</li></ul>          |

| [timeRemaining](#timeRemaining)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.battery.timeRemaining() -> number`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the battery life remaining, in minutes                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A number containing the minutes of battery life remaining. The value may be:</li><li> Greater than zero to indicate the number of minutes remaining</li><li> -1 if the remaining battery life is still being calculated</li><li> -2 if there is unlimited time remaining (i.e. the system is on AC power)</li></ul>          |

| [timeToFullCharge](#timeToFullCharge)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.battery.timeToFullCharge() -> number`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the time remaining for the battery to be fully charged, in minutes                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A number containing the time (in minutes) remaining for the battery to be fully charged, or -1 if the remaining time is still being calculated</li></ul>          |

| [voltage](#voltage)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.battery.voltage() -> number`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the current voltage of the battery in mV                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A number containing the current voltage of the battery</li></ul>          |

| [watts](#watts)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.battery.watts() -> number`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the power entering or leaving the battery, in W                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A number containing the rate of energy conversion in the battery. The value may be:</li><li> Less than zero if the battery is being discharged (i.e. the computer is running on battery power)</li><li> Zero if the battery is being neither charged nor discharged</li><li> Greater than zero if the battery is being charged</li></ul>          |

