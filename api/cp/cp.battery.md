# [docs](index.md) » cp.battery
---

Provides access to various properties of the battery. Each of these properties
is a `cp.prop`, so it can be watched for changes. For example:

```lua
local battery = require("cp.battery")
battery.powerSupply:watch(function(value)
    print("Now using "..value)
end)
```

This will `print` "Now using AC Power" or "Now using Battery Power" whenever the
power supply changes.

## API Overview
* Constants - Useful values which cannot be changed
 * [amperage](#amperage)
 * [capacity](#capacity)
 * [cycles](#cycles)
 * [designCapacity](#designcapacity)
 * [health](#health)
 * [healthCondition](#healthcondition)
 * [isCharged](#ischarged)
 * [isCharging](#ischarging)
 * [isFinishingCharge](#isfinishingcharge)
 * [maxCapacity](#maxcapacity)
 * [otherBatteryInfo](#otherbatteryinfo)
 * [percentage](#percentage)
 * [psuSerial](#psuserial)
 * [timeRemaining](#timeremaining)
 * [timeToFullCharge](#timetofullcharge)
 * [voltage](#voltage)
 * [watts](#watts)

## API Documentation

### Constants

#### [amperage](#amperage)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.battery.amperage <cp.prop: number; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Returns the amount of current flowing through the battery, in mAh.                                                                                         |
| **Notes**                                            | <ul markdown="1"><li markdown="1">* A number containing the amount of current flowing through the battery. The value may be:</li><li markdown="1">** Less than zero if the battery is being discharged (i.e. the computer is running on battery power)</li><li markdown="1">** Zero if the battery is being neither charged nor discharded</li><li markdown="1">** Greater than zero if the bettery is being charged</li></ul>                |

#### [capacity](#capacity)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.battery.capacity <cp.prop: number; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Returns the current capacity of the battery in mAh.                                                                                         |
| **Notes**                                            | <ul markdown="1"><li markdown="1">* This is the measure of how charged the battery is, vs the value of `cp.battery.maxCapacity()`.</li></ul>                |

#### [cycles](#cycles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.battery.cycles <cp.prop: number; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Returns the number of discharge cycles of the battery.                                                                                         |
| **Notes**                                            | <ul markdown="1"><li markdown="1">* One cycle is a full discharge of the battery, followed by a full charge. This may also be an aggregate of many smaller discharge-then-charge cycles (e.g. 10 iterations of discharging the battery from 100% to 90% and then charging back to 100% each time, is considered to be one cycle).</li></ul>                |

#### [designCapacity](#designcapacity)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.battery.designCapacity <cp.prop: number; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Returns the design capacity of the battery in mAh.                                                                                         |

#### [health](#health)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.battery.health <cp.prop: string; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Returns the health status of the battery; either "Good", "Fair" or "Poor",                                                                                         |

#### [healthCondition](#healthcondition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.battery.healthCondition <cp.prop: string; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Returns the health condition status of the battery:                                                                                         |

#### [isCharged](#ischarged)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.battery.isCharged <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Checks if the battery is fully charged.                                                                                         |

#### [isCharging](#ischarging)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.battery.isCharging <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Checks if the battery is currently charging.                                                                                         |

#### [isFinishingCharge](#isfinishingcharge)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.battery.isFinishingCharge <cp.prop: boolean | string; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Checks if the battery is trickle charging;                                                                                         |

#### [maxCapacity](#maxcapacity)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.battery.maxCapacity <cp.prop; number; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Returns the maximum capacity of the battery in mAh.                                                                                         |
| **Notes**                                            | <ul markdown="1"><li markdown="1">* This may exceed the value of `cp.battery.designCapacity()` due to small variations in the production chemistry vs the design.</li></ul>                |

#### [otherBatteryInfo](#otherbatteryinfo)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.battery.otherBatteryInfo <cp.prop: table | nil; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Returns information about non-PSU batteries (e.g. bluetooth accessories). If none are found, `nil` is returned.                                                                                         |

#### [percentage](#percentage)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.battery.percentage <cp.prop; string; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Returns the current source of power; either `"AC Power"`, `"Battery Power"` or `"Off Line"`.                                                                                         |

#### [psuSerial](#psuserial)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.battery.psuSerial <cp.prop: number; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Returns the serial number of the attached power supply, or `0` if not present.                                                                                         |

#### [timeRemaining](#timeremaining)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.battery.timeRemaining <cp.prop: number; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The amount of battery life remaining, in minuges.                                                                                         |
| **Notes**                                            | <ul markdown="1"><li markdown="1">* The return value may be:</li><li markdown="1">** Greater than zero to indicate the number of minutes remaining.</li><li markdown="1">** `-1` if the remaining batttery life is being calculated.</li><li markdown="1">** `-2` if there is unlimited time remaining (i.e. the system is on AC power).</li></ul>                |

#### [timeToFullCharge](#timetofullcharge)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.battery.timeToFullCharge <cp.prop; number; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Returns the time remaining for the battery to be fully charged, in minutes, or `-`` if still being calculated.                                                                                         |

#### [voltage](#voltage)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.battery.voltage <cp.prop: number; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Returns the current voltage of the battery in mV.                                                                                         |

#### [watts](#watts)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.battery.watts <cp.prop: number; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Returns the power entering or leaving the battery, in W.                                                                                         |

