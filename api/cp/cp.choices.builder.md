# [docs](index.md) » cp.choices.builder
---

Choices Builder Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [id](#id)
 * [params](#params)
 * [subText](#subtext)
 * [text](#text)

## API Documentation

### Functions

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.choices.builder.new(choiceType) -> builder` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates a new choice builder instance.                                                                                         |
| **Parameters**                                       | * `choice`	- The choice instance to configure.                                       |
| **Returns**                                          | * The new choice builder.                                                |

### Methods

#### [id](#id)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.choices.builder:id(value) -> builder` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets the ID of the choice.                                                                                         |
| **Parameters**                                       | * `value`	- The ID.                                       |
| **Returns**                                          | * The choice builder.                                                |

#### [params](#params)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.choices.builder:params(value) -> builder` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Specifies a table of parameter values for the choice. These                                                                                         |
| **Parameters**                                       | * `value`	- The table of parameters.                                       |
| **Returns**                                          | * The choice builder, added to the choices set.                                                |

#### [subText](#subtext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.choices.builder:subText(value) -> builder` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Specifies the `subText` value for the choice being built.                                                                                         |
| **Parameters**                                       | * `value`	- The subText title for the choice.                                       |
| **Returns**                                          | * The choice builder.                                                |

#### [text](#text)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.choices.builder:text(value) -> builder` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Specifies the text value for the choice being built.                                                                                         |
| **Parameters**                                       | * `value`	- The text title for the choice.                                       |
| **Returns**                                          | * The choice builder, added to the choices set.                                                |

