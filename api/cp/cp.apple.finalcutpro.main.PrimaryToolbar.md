# [docs](index.md) » cp.apple.finalcutpro.main.PrimaryToolbar
---

Timeline Toolbar.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [PrimaryToolbar](#primarytoolbar)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [backgroundTasksWindow](#backgroundtaskswindow)
 * [browserShowing](#browsershowing)
 * [extensions](#extensions)
 * [inspectorShowing](#inspectorshowing)
 * [keywordEditor](#keywordeditor)
 * [mediaImport](#mediaimport)
 * [shareButton](#sharebutton)
 * [timelineShowing](#timelineshowing)

## API Documentation

### Functions

#### [matches](#matches)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.PrimaryToolbar.matches(element) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks to see if an element matches what we think it should be. |
| **Parameters**                                       | <ul><li>element - An <code>axuielementObject</code> to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if matches otherwise <code>false</code></li></ul> |

### Constructors

#### [PrimaryToolbar](#primarytoolbar)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.PrimaryToolbar(parent) -> PrimaryToolbar` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `PrimaryToolbar` instance. |
| **Parameters**                                       | <ul><li>parent - The parent object.</li></ul> |
| **Returns**                                          | <ul><li>A new <code>PrimaryToolbar</code> object.</li></ul> |

### Fields

#### [backgroundTasksWindow](#backgroundtaskswindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.PrimaryToolbar.backgroundTasksWindow <cp.ui.CheckBox>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `CheckBox` that will open the `BackgroundTasksWindow` dialog |

#### [browserShowing](#browsershowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.PrimaryToolbar.browserShowing <cp.ui.CheckBox>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `CheckBox` indicating if the `Browser` is showing |

#### [extensions](#extensions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.PrimaryToolbar.extensions <cp.ui.Button>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `Button` that will open the "Available Extensions" dialog, or trigger the only extension, if only one is installed. |

#### [inspectorShowing](#inspectorshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.PrimaryToolbar.inspectorShowing <cp.ui.CheckBox>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `CheckBox` indicating if the Inspector is showing |

#### [keywordEditor](#keywordeditor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.PrimaryToolbar.keywordEditor <cp.ui.CheckBox>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `CheckBox` that will open the `KeywordEditor` dialog when checked. |

#### [mediaImport](#mediaimport)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.PrimaryToolbar.mediaImport <cp.ui.Button>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `Button` that will open the `MediaImport` dialog |

#### [shareButton](#sharebutton)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.PrimaryToolbar.shareButton <cp.ui.Button>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The Share Button. |

#### [timelineShowing](#timelineshowing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.PrimaryToolbar.timelineShowing <cp.ui.CheckBox>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The `CheckBox` indicating if the `Timeline` is showing |

