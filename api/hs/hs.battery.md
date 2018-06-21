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
 * [designCapacity](#designcapacity)
 * [getAll](#getall)
 * [health](#health)
 * [healthCondition](#healthcondition)
 * [isCharged](#ischarged)
 * [isCharging](#ischarging)
 * [isFinishingCharge](#isfinishingcharge)
 * [maxCapacity](#maxcapacity)
 * [name](#name)
 * [otherBatteryInfo](#otherbatteryinfo)
 * [percentage](#percentage)
 * [powerSource](#powersource)
 * [privateBluetoothBatteryInfo](#privatebluetoothbatteryinfo)
 * [psuSerial](#psuserial)
 * [timeRemaining](#timeremaining)
 * [timeToFullCharge](#timetofullcharge)
 * [voltage](#voltage)
 * [watts](#watts)

## API Documentation

### Functions

#### [amperage](#amperage)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.battery.amperage() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the amount of current flowing through the battery, in mAh                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A number containing the amount of current flowing through the battery. The value may be:</li></ul><ul><li>Less than zero if the battery is being discharged (i.e. the computer is running on battery power)</li></ul><ul><li>Zero if the battery is being neither charged nor discharged</li></ul><ul><li>Greater than zero if the battery is being charged</li></ul>            |

#### [capacity](#capacity)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.battery.capacity() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the current capacity of the battery in mAh                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A number containing the current capacity of the battery in mAh</li></ul>            |
| **Notes**                                            | <ul><li>This is the measure of how charged the battery is, vs the value of <code>hs.battery.maxCapacity()</code></li></ul>                 |

#### [cycles](#cycles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.battery.cycles() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the number of discharge cycles of the battery                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>The number of cycles</li></ul>            |
| **Notes**                                            | <ul><li>One cycle is a full discharge of the battery, followed by a full charge. This may also be an aggregate of many smaller discharge-then-charge cycles (e.g. 10 iterations of discharging the battery from 100% to 90% and then charging back to 100% each time, is considered to be one cycle)</li></ul>                 |

#### [designCapacity](#designcapacity)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.battery.designCapacity() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the design capacity of the battery in mAh.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A number containing the rated maximum capacity of the battery</li></ul>            |

#### [getAll](#getall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.battery.getAll() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Get all available battery information                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A table containing all the information provided by the separate functions in hs.battery</li></ul>            |
| **Notes**                                            | <ul><li>If you require multiple pieces of information about a battery, this function may be more efficient than calling several other functions separately</li></ul>                 |

#### [health](#health)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.battery.health() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the health status of the battery.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A string containing one of {Good, Fair, Poor}, as determined by the Apple Smart Battery controller</li></ul>            |

#### [healthCondition](#healthcondition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.battery.healthCondition() -> string or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the health condition status of the battery.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>Nil if there are no health conditions to report, or a string containing either:</li></ul><ul><li>"Check Battery"</li></ul><ul><li>"Permanent Battery Failure"</li></ul>            |

#### [isCharged](#ischarged)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.battery.isCharged() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the charged state of the battery                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>True if the battery is charged, false if not</li></ul>            |

#### [isCharging](#ischarging)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.battery.isCharging() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the charging state of the battery                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>True if the battery is being charged, false if not</li></ul>            |

#### [isFinishingCharge](#isfinishingcharge)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.battery.isFinishingCharge() -> boolean or string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns true if battery is finishing its charge                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>True if the battery is in its final charging state (i.e. trickle charging), false if not, or "n/a" if the battery is not charging at all</li></ul>            |

#### [maxCapacity](#maxcapacity)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.battery.maxCapacity() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the maximum capacity of the battery in mAh                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A number containing the observed maximum capacity of the battery in mAh</li></ul>            |
| **Notes**                                            | <ul><li>This may exceed the value of <code>hs.battery.designCapacity()</code> due to small variations in the production chemistry vs the design</li></ul>                 |

#### [name](#name)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.battery.name() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the name of the battery                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A string containing the name of the battery</li></ul>            |

#### [otherBatteryInfo](#otherbatteryinfo)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.battery.otherBatteryInfo() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns information about non-PSU batteries (e.g. bluetooth accessories)                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A table containing information about other batteries known to the system, or an empty table if no devices were found</li></ul>            |

#### [percentage](#percentage)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.battery.percentage() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the current percentage of battery charge                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A number containing the percentage of battery charge</li></ul>            |

#### [powerSource](#powersource)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.battery.powerSource() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns current source of power                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A string containing one of {AC Power, Battery Power, Off Line}.</li></ul>            |

#### [privateBluetoothBatteryInfo](#privatebluetoothbatteryinfo)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.battery.privateBluetoothBatteryInfo() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns information about Bluetooth devices using Apple Private APIs                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A table containing information about devices using private Apple APIs.</li></ul>            |
| **Notes**                                            | <ul><li>This function uses private Apple APIs - that means it can break without notice on any macOS version update. Please report breakage to us!</li></ul><ul><li>This function will return information for all connected Bluetooth devices, but much of it will be meaningless for most devices</li></ul><ul><li>The table contains the following keys:</li></ul><ul><li>vendorID - Numerical identifier for the vendor of the device (Apple's ID is 76)</li></ul><ul><li>productID - Numerical identifier for the device</li></ul><ul><li>address - The bluetooth address of the device</li></ul><ul><li>isApple - A string containing "YES" or "NO", depending on whether or not this is an Apple/Beats product, or a third party product</li></ul><ul><li>name - A human readable string containing the name of the device</li></ul><ul><li>batteryPercentSingle - For some devices this will contain the percentage of the battery (e.g. Beats headphones)</li></ul><ul><li>batteryPercentCombined - We do not currently understand what this field represents, please report if you find a non-zero value here</li></ul><ul><li>batteryPercentCase - Battery percentage of AirPods cases (note that this will often read 0 - the AirPod case sleeps aggressively)</li></ul><ul><li>batteryPercentLeft - Battery percentage of the left AirPod if it is out of the case</li></ul><ul><li>batteryPercentRight - Battery percentage of the right AirPod if it is out of the case</li></ul><ul><li>buttonMode - We do not currently understand what this field represents, please report if you find a value other than 1</li></ul><ul><li>micMode - For AirPods this corresponds to the microphone option in the device's Bluetooth options</li></ul><ul><li>leftDoubleTap - For AirPods this corresponds to the left double tap action in the device's Bluetooth options</li></ul><ul><li>rightDoubleTap - For AirPods this corresponds to the right double tap action in the device's Bluetooth options</li></ul><ul><li>primaryBud - For AirPods this is either "left" or "right" depending on which bud is currently considered the primary device</li></ul><ul><li>primaryInEar - For AirPods this is "YES" or "NO" depending on whether or not the primary bud is currently in an ear</li></ul><ul><li>secondaryInEar - For AirPods this is "YES" or "NO" depending on whether or not the secondary bud is currently in an ear</li></ul><ul><li>isInEarDetectionSupported - Whether or not this device can detect when it is currently in an ear</li></ul><ul><li>isEnhancedDoubleTapSupported - Whether or not this device supports double tapping</li></ul><ul><li>isANCSupported - We believe this likely indicates whether or not this device supports Active Noise Cancelling (e.g. Beats Solo)</li></ul><ul><li>Please report any crashes from this function - it's likely that there are Bluetooth devices we haven't tested which may return weird data</li></ul><ul><li>Many/Most/All non-Apple party products will likely return zeros for all of the battery related fields here, as will Apple HID devices. It seems that these private APIs mostly exist to support Apple/Beats headphones.</li></ul>                 |

#### [psuSerial](#psuserial)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.battery.psuSerial() -> integer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the serial number of the attached power supply, if present                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>An integer containing the power supply's serial number, or 0 if no serial can be found</li></ul>            |

#### [timeRemaining](#timeremaining)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.battery.timeRemaining() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the battery life remaining, in minutes                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A number containing the minutes of battery life remaining. The value may be:</li></ul><ul><li>Greater than zero to indicate the number of minutes remaining</li></ul><ul><li>-1 if the remaining battery life is still being calculated</li></ul><ul><li>-2 if there is unlimited time remaining (i.e. the system is on AC power)</li></ul>            |

#### [timeToFullCharge](#timetofullcharge)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.battery.timeToFullCharge() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the time remaining for the battery to be fully charged, in minutes                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A number containing the time (in minutes) remaining for the battery to be fully charged, or -1 if the remaining time is still being calculated</li></ul>            |

#### [voltage](#voltage)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.battery.voltage() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the current voltage of the battery in mV                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A number containing the current voltage of the battery</li></ul>            |

#### [watts](#watts)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.battery.watts() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the power entering or leaving the battery, in W                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>A number containing the rate of energy conversion in the battery. The value may be:</li></ul><ul><li>Less than zero if the battery is being discharged (i.e. the computer is running on battery power)</li></ul><ul><li>Zero if the battery is being neither charged nor discharged</li></ul><ul><li>Greater than zero if the battery is being charged</li></ul>            |

