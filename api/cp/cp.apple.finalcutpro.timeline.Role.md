# [docs](index.md) » cp.apple.finalcutpro.timeline.Role
---

*Extends [Row](cp.ui.Row.md)*

Represents a Role in the [Timeline Index](cp.apple.finalcutpro.timeline.Index.md).

## API Overview
* Constants - Useful values which cannot be changed
 * [TITLE_KEY](#title_key)
 * [TYPE](#type)
* Functions - API calls offered directly by the extension
 * [findTitle](#findtitle)
 * [is](#is)
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [Role](#role)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [active](#active)
 * [cellUI](#cellui)
 * [subroleRow](#subrolerow)
 * [title](#title)
* Methods - API calls which can only be made on an object returned by a constructor
 * [doActivate](#doactivate)
 * [doDeactivate](#dodeactivate)
 * [type](#type)

## API Documentation

### Constants

#### [TITLE_KEY](#title_key)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Role.TITLE_KEY <table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Contains the list of [strings](cp.apple.finalcutpro.strings.md) used for default roles. |
| **Notes**                                            | <ul><li>CAPTIONS - "Captions"</li><li>VIDEO - "Video"</li><li>TITLES - "Titles"</li><li>DIALOGUE - "Dialogue"</li><li>MUSIC - "Music"</li><li>EFFECTS - "Effects"</li></ul> |

#### [TYPE](#type)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Role.TYPE <table>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Contains the set of role types. |
| **Notes**                                            | <ul><li>VIDEO - A Video Role</li><li>AUDIO - An Audio Role</li><li>CAPTION - A Caption Role</li></ul> |

### Functions

#### [findTitle](#findtitle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Role.findTitle(title) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if FCPX is not currently running in English, it will check if the title is one |

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Role.is(thing) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the `thing` is a `Role`. |
| **Parameters**                                       | <ul><li><code>thing</code>      - The thing to check</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the thing is a <code>Table</code> instance.</li></ul> |

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Role.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the `element` is a `Role`. |
| **Parameters**                                       | <ul><li>element - the <code>axuielement</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if it matches, otherwise <code>false</code>.</li></ul> |

### Constructors

#### [Role](#role)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Role(parent, uiFinder, type)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates the new Role. Typically this is not called directly, but rather by one of the |
| **Parameters**                                       | <ul><li>parent - The parent <a href="cp.ui.Element.md">Element</a></li><li>uiFinder - The <code>function</code> or <code>cp.prop</code> that provides the <code>axuielement</code>.</li><li>type - The [#TYPE] of Role.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Role</code> instance.</li></ul> |

### Fields

#### [active](#active)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Role.active <cp.ui.CheckBox>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [CheckBox](cp.ui.CheckBox.md) that determines if the `Role` is active in the timeline. |

#### [cellUI](#cellui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Role.cellUI <cp.prop: axuielement; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The AXCell `axuielement` containing the Role details. |

#### [subroleRow](#subrolerow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Role.subroleRow <cp.prop: boolean; read-only>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | This is `true` if the `Role` is an Subrole [Row](cp.ui.Row.md). |

#### [title](#title)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Role.title <cp.ui.StaticText>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The [StaticText](cp.ui.StaticText.md) containing the title. |

### Methods

#### [doActivate](#doactivate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Role:doActivate() -> cp.rx.go.Statement.md` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will activate the current role, if possible. |

#### [doDeactivate](#dodeactivate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Role:doDeactivate() -> cp.rx.go.Statement.md` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will deactivate the current role, if possible. |

#### [type](#type)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.timeline.Role:type() -> cp.apple.finalcut.timeline.Role.TYPE` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the type of Role this is. |

