# [docs](index.md) » cp.apple.finalcutpro.inspector.info.InfoInspector
---

Video Inspector Module.

## API Overview
* Constants - Useful values which cannot be changed
 * [metadataViews](#metadataviews)
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [metadataView](#metadataview)
* Methods - API calls which can only be made on an object returned by a constructor
 * [app](#app)
 * [isShowing](#isshowing)
 * [parent](#parent)
 * [propertiesUI](#propertiesui)
 * [show](#show)
 * [UI](#ui)

## API Documentation

### Constants

#### [metadataViews](#metadataviews)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.info.InfoInspector.metadataViews -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Metadata Views                                                                                         |

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.info.InfoInspector.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Checks to see if an element matches what we think it should be.                                                                                         |
| **Parameters**                                       |  * element - An `axuielementObject` to check.                                       |
| **Returns**                                          |  * `true` if matches otherwise `false`                                                |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.info.InfoInspector.new(parent) -> InfoInspector object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new InfoInspector object                                                                                         |
| **Parameters**                                       |  * `parent`     - The parent                                       |
| **Returns**                                          |  * A InfoInspector object                                                |

### Fields

#### [metadataView](#metadataview)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.info.InfoInspector.metadataView <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Gets the name of the current metadata view.                                                                                         |

### Methods

#### [app](#app)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.info.InfoInspector:app() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `cp.apple.finalcutpro` app table                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The application object as a table                                                |

#### [isShowing](#isshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.info.InfoInspector:isShowing() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Is the Info Inspector currently showing?                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `true` if showing, otherwise `false`                                                |

#### [parent](#parent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.info.InfoInspector:parent() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the InfoInspector's parent table                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The parent object as a table                                                |

#### [propertiesUI](#propertiesui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.info.InfoInspector:propertiesUI() -> hs._asm.axuielement object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `hs._asm.axuielement` object for the Properties UI.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A `hs._asm.axuielement` object.                                                |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.info.InfoInspector:show() -> MenuButton` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Gets the Info Inspector Metadata View Button.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * An `MenuButton` object.                                                |

#### [UI](#ui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.info.InfoInspector:UI() -> hs._asm.axuielement object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the `hs._asm.axuielement` object for the Info Inspector                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A `hs._asm.axuielement` object.                                                |

