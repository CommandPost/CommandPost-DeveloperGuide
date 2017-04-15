# [docs](index.md) » cp.choices
---

Choices Module.

## Submodules
 * [cp.choices.builder](cp.choices.builder.md)

## API Overview
* Functions - API calls offered directly by the extension
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [getChoices](#getChoices)
 * [isStatic](#isStatic)
 * [new](#new)
 * [setStatic](#setStatic)

## API Documentation

### Functions

| [new](#new)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.choices.new(choiceType) -> choices`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Creates a new `cp.plugin.chooser.choices` instance for the specified type.                                                                     |
| **Parameters**                              | <ul><li>* `type`	- The unique ID for the type.</li></ul> |
| **Returns**                                 | <ul><li>* The new `choices` instance.</li></ul>          |

### Methods

| [getChoices](#getChoices)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.choices:getChoices() -> array of choices`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns the array of choices that have been added to this instance.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The array of choices.</li></ul>          |

| [isStatic](#isStatic)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.choices:isStatic() -> boolean`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns `true` if the choices set is static.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>`true` if the choices set is static.</li></ul>          |

| [new](#new)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.choices:new(choiceType) -> choices.builder`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Adds a new choice with the specified. Additional settings                                                                     |
| **Parameters**                              | <ul><li>`text`	- The text title for the choice.</li></ul> |
| **Returns**                                 | <ul><li>The choice builder, added to the choices set.</li></ul>          |

| [setStatic](#setStatic)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.choices:setStatic(value) -> choices`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | By default, choices are considered to be dynamic, and should be                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The `choices` instance.</li></ul>          |

