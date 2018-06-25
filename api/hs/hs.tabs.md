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
| **Parameters**                                       | <ul><br /><li>app - An <code>hs.application</code> object or the app title</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |

#### [focusTab](#focustab)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tabs.focusTab(app, num)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Focuses a specific tab of an app                                                                                         |
| **Parameters**                                       | <ul><br /><li>app - An <code>hs.application</code> object previously enabled for tabbing * num - A tab number to switch to</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>If num is higher than the number of tabs, the last tab will be focussed</li><br /></ul>                                             |

#### [tabWindows](#tabwindows)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.tabs.tabWindows(app)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets a list of the tabs of a window                                                                                         |
| **Parameters**                                       | <ul><br /><li>app - An <code>hs.application</code> object</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>An array of the tabbed windows of an app in the same order as they would be tabbed</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>This function can be used when writing tab switchers</li><br /></ul>                                             |

