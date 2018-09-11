# [docs](index.md) » cp.apple.finalcutpro.inspector.BasePanel
---

A base class for the different panels in the [Inspector](cp.apple.finalcutpro.inspector.Inspector.md).

Extends [Element](cp.ui.Element.md).

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [BasePanel](#basepanel)
* Methods - API calls which can only be made on an object returned by a constructor
 * [doShow](#doshow)
 * [hide](#hide)
 * [panelType](#paneltype)
 * [show](#show)

## API Documentation

### Constructors

#### [BasePanel](#basepanel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.BasePanel(parent, panelType) -> BasePanel` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Constructs the panel, initialising the parent and the [UI](cp.ui.Element.md#UI). |
| **Parameters**                                       | <ul><li>parent        - The parent <a href="cp.ui.Element.md">Element</a>.</li><li>panelType     - The panel type string, as defined in <a href="cp.apple.finalcutpro.inspector.Inspector.md#INSPECTOR_TABS">Inspector.INSPECTOR_TABS</a>.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>BasePanel</code> instance.</li></ul> |

### Methods

#### [doShow](#doshow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.BasePanel:doShow() -> cp.rx.go.Statment` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that hides the panel. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The <code>Statement</code>, resolving to <code>true</code> if successful and sending an error if not.</li></ul> |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.BasePanel:hide() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Hides the panel. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [panelType](#paneltype)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.BasePanel:panelType() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the type of panel this is. |
| **Returns**                                          | <ul><li>The panel type identifier.</li></ul> |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.inspector.BasePanel:show() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Shows the panel. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

