# [docs](index.md) » cp.choices
---

Choices Module.

## Submodules
 * [cp.choices.builder](cp.choices.builder.md)

## API Overview
* Functions - API calls offered directly by the extension
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [getChoices](#getchoices)
 * [new](#new)

## API Documentation

### Functions

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.choices.new(choiceType) -> choices` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates a new `cp.plugin.chooser.choices` instance for the specified type.                                                                                         |
| **Parameters**                                       | <ul><li>* `type`	- The unique ID for the type.</li></ul> |
| **Returns**                                          | <ul><li>* The new `choices` instance.</li></ul>          |

### Methods

#### [getChoices](#getchoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.choices:getChoices() -> array of choices` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the array of choices that have been added to this instance.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The array of choices.</li></ul>          |

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.choices:new(choiceType) -> choices.builder` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Adds a new choice with the specified. Additional settings                                                                                         |
| **Parameters**                                       | <ul><li>`text`	- The text title for the choice.</li></ul> |
| **Returns**                                          | <ul><li>The choice builder, added to the choices set.</li></ul>          |

