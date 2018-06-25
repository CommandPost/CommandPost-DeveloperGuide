# [docs](index.md) » cp.time.flicks
---

Provides support for measuring time in `flicks`, a base unit of time useful for
working with media, such as video or audio files.

From the [Flicks GitHub project]():


A flick (frame-tick) is a very small unit of time. It is 1/705600000 of a second, exactly.

`1 flick = 1/705600000 second`

This unit of time is the smallest time unit which is LARGER than a nanosecond, and can in integer quantities exactly
represent a single frame duration for 24 Hz, 25 Hz, 30 Hz, 48 Hz, 50 Hz, 60 Hz, 90 Hz, 100 Hz, 120 Hz, and
also 1/1000 divisions of each, as well as a single sample duration for 8 kHz, 16 kHz, 22.05 kHz, 24 kHz, 32 kHz,
44.1 kHz, 48 kHz, 88.2 kHz, 96 kHz, and 192kHz, as well as the NTSC frame durations for 24 * (1000/1001) Hz,
30 * (1000/1001) Hz, 60 * (1000/1001) Hz, and 120 * (1000/1001) Hz.

That above was one hell of a run-on sentence, but it's strictly and completely correct in its description of
the unit.

This makes flicks suitable for use via std::chrono::duration and std::ratio for doing timing work against the
system high resolution clock, which is in nanoseconds, but doesn't get slightly out of sync when doing
common frame rates.

We also support some common audio sample rates as well. This list is not exhaustive, but covers the majority
of digital audio formats. They are 8kHz, 16kHz, 22.05kHz, 24kHz, 32kHz, 44.1kHz, 48kHz, 88.2kHz, 96kHz, and 192kHz.

Though it is not part of the design criteria, 144 Hz, which some newer monitors refresh at, does work
correctly with flicks.

NTSC IS NOT EXPLICITLY SUPPORTED IN ALL OF ITS SUBTLE NUANCES, BUT: The NTSC variations (~23.976, ~29.97, etc)
are approximately defined as 24 * 1000/1001 and 30 * 1000/1001, etc. These can be represented exactly in flicks,
but 1/1000 divisions are not available.

Many folks online have pointed out that NTSC technically has a variable frame rate, and that this is handled
correctly in other media playback libraries such as QuickTime. The goal of flicks is to provide a simple,
convenient std::chrono::duration to work with when writing code that works with simulation and time in media,
but not explicitly to handle complex variable-rate playback scenarios. So we'll stick with the 1000/1001
approximations, and leave it at that!

# Details

* 24 fps frame: 29400000 flicks
* 25 fps frame: 28224000 flicks
* 30 fps frame: 23520000 flicks
* 48 fps frame: 14700000 flicks
* 50 fps frame: 14112000 flicks
* 60 fps frame: 11760000 flicks
* 90 fps frame: 7840000 flicks
* 100 fps frame: 7056000 flicks
* 120 fps frame: 5880000 flicks
* 8000 fps frame: 88200 flicks
* 16000 fps frame: 44100 flicks
* 22050 fps frame: 32000 flicks
* 24000 fps frame: 29400 flicks
* 32000 fps frame: 22050 flicks
* 44100 fps frame: 16000 flicks
* 48000 fps frame: 14700 flicks
* 88200 fps frame: 8000 flicks
* 96000 fps frame: 7350 flicks
* 192000 fps frame: 3675 flicks

# NTSC:

* 24 * 1000/1001 (~23.976) fps frame: 29429400 flicks
* 30 * 1000/1001 (~29.97) fps frame: 23543520 flicks
* 60 * 1000/1001 (~59.94) fps frame: 11771760 flicks
* 120 * 1000/1001 (~119.88) fps frame: 5885880 flicks

## API Overview
* Constants - Useful values which cannot be changed
 * [perFrame100](#perframe100)
 * [perFrame120](#perframe120)
 * [perFrame120NTSC](#perframe120ntsc)
 * [perFrame24](#perframe24)
 * [perFrame24NTSC](#perframe24ntsc)
 * [perFrame25](#perframe25)
 * [perFrame30](#perframe30)
 * [perFrame30NTSC](#perframe30ntsc)
 * [perFrame44100](#perframe44100)
 * [perFrame48](#perframe48)
 * [perFrame48000](#perframe48000)
 * [perFrame50](#perframe50)
 * [perFrame60](#perframe60)
 * [perFrame60NTSC](#perframe60ntsc)
 * [perFrame90](#perframe90)
 * [perHour](#perhour)
 * [perMinutes](#perminutes)
 * [perSecond](#persecond)
* Functions - API calls offered directly by the extension
 * [is](#is)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
 * [parse](#parse)
* Methods - API calls which can only be made on an object returned by a constructor
 * [toFrames](#toframes)
 * [toSeconds](#toseconds)
 * [toTimecode](#totimecode)

## API Documentation

### Constants

#### [perFrame100](#perframe100)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.time.flicks.perFrame100` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The number of flicks in 1 frame at 100 fps. |

#### [perFrame120](#perframe120)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.time.flicks.perFrame120` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The number of flicks in 1 frame at 120 fps. |

#### [perFrame120NTSC](#perframe120ntsc)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.time.flicks.perFrame120NTSC` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | An approximate for flicks in 1 frame at 120 fps in NTSC, a.k.a. ~119.88 fps. |

#### [perFrame24](#perframe24)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.time.flicks.perFrame24` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The number of flicks in 1 frame at 24 fps. |

#### [perFrame24NTSC](#perframe24ntsc)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.time.flicks.perFrame24NTSC` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | An approximate for flicks in 1 frame at 24 fps in NTSC, a.k.a. 23.976 fps. |

#### [perFrame25](#perframe25)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.time.flicks.perFrame25` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The number of flicks in 1 frame at 25 fps. |

#### [perFrame30](#perframe30)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.time.flicks.perFrame30` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The number of flicks in 1 frame at 30 fps. |

#### [perFrame30NTSC](#perframe30ntsc)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.time.flicks.perFrame30NTSC` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | An approximate for flicks in 1 frame at 30 fps in NTSC, a.k.a. 29.97 fps. |

#### [perFrame44100](#perframe44100)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.time.flicks.perFrame44100` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The number of flicks in 1 frame at 44100 fps, a.k.a. 44.1 Hz. |

#### [perFrame48](#perframe48)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.time.flicks.perFrame48` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The number of flicks in 1 frame at 48 fps. |

#### [perFrame48000](#perframe48000)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.time.flicks.perFrame48000` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The number of flicks in 1 frame at 44100 fps, a.k.a. 48 Hz. |

#### [perFrame50](#perframe50)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.time.flicks.perFrame50` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The number of flicks in 1 frame at 50 fps. |

#### [perFrame60](#perframe60)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.time.flicks.perFrame60` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The number of flicks in 1 frame at 60 fps. |

#### [perFrame60NTSC](#perframe60ntsc)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.time.flicks.perFrame60NTSC` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | An approximate for flicks in 1 frame at 60 fps in NTSC, a.k.a. 59.94 fps. |

#### [perFrame90](#perframe90)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.time.flicks.perFrame90` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The number of flicks in 1 frame at 90 fps. |

#### [perHour](#perhour)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.time.flicks.perHour` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The number of flicks in 1 hour. |

#### [perMinutes](#perminutes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.time.flicks.perMinutes` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The number of flicks in 1 minute. |

#### [perSecond](#persecond)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.time.flicks.perSecond` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The number of flicks in 1 second. |

### Functions

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.time.flicks.is(thing) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the `thing` is a `flicks` instance. |
| **Parameters**                                       | <ul><li>thing - the thing to check</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the thingis a flicks instance, otherwise <code>false</code>.</li></ul> |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.time.flicks.new(value) -> flicks` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `flicks` instance. By default, the unit is in flicks`, but can be set as a |
| **Parameters**                                       | <ul><li>value - the base value to set to</li></ul> |
| **Returns**                                          | <ul><li>the new <code>flicks</code> instance</li></ul> |

#### [parse](#parse)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.time.flicks.parse(timecodeString, framerate) -> flicks` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Attempts to parse the timecode string value with the specified framerate. |
| **Parameters**                                       | <ul><li>timecodeString   - The timecode as a string. * framerate        - The number of frames per second.</li></ul> |
| **Returns**                                          | <ul><li>a new <code>flicks</code> instance for the timecode.</li></ul> |

### Methods

#### [toFrames](#toframes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.time.flicks:toFrames(framerate) --> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Converts the flicks into a number for the specific framerate. |

#### [toSeconds](#toseconds)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.time.flicks:toSeconds() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Converts the flicks into a decimal value of the number of seconds it represents. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the number of seconds</li></ul> |

#### [toTimecode](#totimecode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.time.flicks:toTimecode(framerate[, delimeter]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Converts the flicks into a string of the format "HH[:]MM[:]SS[:;]FF", with hours, minutes and frames listed respectively. |
| **Parameters**                                       | <ul><li>framerate    - the framerate to use when calculating frames per second. * delimeter    - either <code>nil</code> (default), ":", or ";".</li></ul> |
| **Returns**                                          | <ul><li>String of the timecode.</li></ul> |

