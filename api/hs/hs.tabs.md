# [docs](index.md) » hs.tabs
---

Place the windows of an application into tabs drawn on its titlebar

## API Overview
* Functions - API calls offered directly by the extension
 * [enableForApp](#enableforapp)
 * [focusTab](#focustab)
 * [tabWindows](#tabwindows)

## API Documentation

### Functions

#### [enableForApp](#enableforapp)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tabs.enableForApp(app)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Places all the windows of an app into one place and tab them                                                                                         |
| **Parameters**                                       |  * app - An `hs.application` object or the app title                                       |
| **Returns**                                          |  * None                                                |

#### [focusTab](#focustab)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tabs.focusTab(app, num)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Focuses a specific tab of an app                                                                                         |
| **Parameters**                                       |  * app - An `hs.application` object previously enabled for tabbing * num - A tab number to switch to                                       |
| **Returns**                                          |  * None                                                |
| **Notes**                                            |  * If num is higher than the number of tabs, the last tab will be focussed                                                      |

#### [tabWindows](#tabwindows)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tabs.tabWindows(app)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets a list of the tabs of a window                                                                                         |
| **Parameters**                                       |  * app - An `hs.application` object                                       |
| **Returns**                                          |  * An array of the tabbed windows of an app in the same order as they would be tabbed                                                |
| **Notes**                                            |  * This function can be used when writing tab switchers                                                      |

