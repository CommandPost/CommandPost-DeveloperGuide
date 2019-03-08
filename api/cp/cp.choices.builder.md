# [docs](index.md) » cp.choices.builder
---

Choices Builder Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [id](#id)
 * [image](#image)
 * [params](#params)
 * [subText](#subtext)
 * [text](#text)

## API Documentation

### Functions

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.choices.builder.new(choiceType) -> builder` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Creates a new choice builder instance. |
| **Parameters**                                       | <ul><li><code>choice</code> - The choice instance to configure.</li></ul> |
| **Returns**                                          | <ul><li>The new choice builder.</li></ul> |

### Methods

#### [id](#id)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.choices.builder:id(value) -> builder` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the ID of the choice. |
| **Parameters**                                       | <ul><li><code>value</code>  - The ID.</li></ul> |
| **Returns**                                          | <ul><li>The choice builder.</li></ul> |

#### [image](#image)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.choices.builder:image(value) -> builder` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the image of the choice. |
| **Parameters**                                       | <ul><li>value - A <code>hs.image</code> image object that will be displayed next to the choice</li></ul> |
| **Returns**                                          | <ul><li>The choice builder.</li></ul> |

#### [params](#params)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.choices.builder:params(value) -> builder` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Specifies a table of parameter values for the choice. These |
| **Parameters**                                       | <ul><li><code>value</code>  - The table of parameters.</li></ul> |
| **Returns**                                          | <ul><li>The choice builder, added to the choices set.</li></ul> |

#### [subText](#subtext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.choices.builder:subText(value) -> builder` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Specifies the `subText` value for the choice being built. |
| **Parameters**                                       | <ul><li><code>value</code>  - The subText title for the choice.</li></ul> |
| **Returns**                                          | <ul><li>The choice builder.</li></ul> |

#### [text](#text)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.choices.builder:text(value) -> builder` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Specifies the text value for the choice being built. |
| **Parameters**                                       | <ul><li><code>value</code>  - The text title for the choice.</li></ul> |
| **Returns**                                          | <ul><li>The choice builder, added to the choices set.</li></ul> |

