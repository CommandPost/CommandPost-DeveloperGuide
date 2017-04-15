# [docs](index.md) » cp.choices.builder
---

Choices Builder Module.

## API Overview
* Functions - API calls offered directly by the extension
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [id](#id)
 * [params](#params)
 * [subText](#subText)
 * [text](#text)

## API Documentation

### Functions

| [new](#new)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.choices.builder.new(choiceType) -> builder`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Creates a new choice builder instance.                                                                     |
| **Parameters**                              | <ul><li>* `choice`	- The choice instance to configure.</li></ul> |
| **Returns**                                 | <ul><li>* The new choice builder.</li></ul>          |

### Methods

| [id](#id)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.choices.builder:id(value) -> builder`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Indicates the choice is a favorite.                                                                     |
| **Parameters**                              | <ul><li>* `value`	- True or false.</li></ul> |
| **Returns**                                 | <ul><li>* The choice builder.</li></ul>          |

| [params](#params)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.choices.builder:params(value) -> builder`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Specifies a table of parameter values for the choice. These                                                                     |
| **Parameters**                              | <ul><li>* `value`	- The table of parameters.</li></ul> |
| **Returns**                                 | <ul><li>* The choice builder, added to the choices set.</li></ul>          |

| [subText](#subText)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.choices.builder:subText(value) -> builder`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Specifies the `subText` value for the choice being built.                                                                     |
| **Parameters**                              | <ul><li>* `value`	- The subText title for the choice.</li></ul> |
| **Returns**                                 | <ul><li>* The choice builder.</li></ul>          |

| [text](#text)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.choices.builder:text(value) -> builder`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Specifies the text value for the choice being built.                                                                     |
| **Parameters**                              | <ul><li>* `value`	- The text title for the choice.</li></ul> |
| **Returns**                                 | <ul><li>* The choice builder, added to the choices set.</li></ul>          |

