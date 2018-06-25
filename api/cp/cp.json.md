# [docs](index.md) » cp.json
---

A collection of handy JSON tools.

## API Overview
* Functions - API calls offered directly by the extension
 * [decode](#decode)
 * [encode](#encode)
 * [prop](#prop)
 * [read](#read)
 * [write](#write)

## API Documentation

### Functions

#### [decode](#decode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.json.decode(jsonString) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Decodes JSON into a table                                                                                         |
| **Parameters**                                       | <ul><br /><li>jsonString - A string containing some JSON data</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A table representing the supplied JSON data</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>This is useful for retrieving some of the more complex lua table structures as a persistent setting (see <code>hs.settings</code>)</li><br /></ul>                                             |

#### [encode](#encode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.json.encode(val[, prettyprint]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Encodes a table as JSON                                                                                         |
| **Parameters**                                       | <ul><br /><li>val - A table containing data to be encoded as JSON * prettyprint - An optional boolean, true to format the JSON for human readability, false to format the JSON for size efficiency. Defaults to false</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A string containing a JSON representation of the supplied table</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>This is useful for storing some of the more complex lua table structures as a persistent setting (see <code>hs.settings</code>)</li><br /></ul>                                             |

#### [prop](#prop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.json.prop(folder, filename, defaultValue) -> cp.prop` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns a `cp.prop` instance for a JSON file.                                                                                         |
| **Parameters**                                       | <ul><br /><li>path - The path to the JSON folder (i.e. "~/Library/Caches") * folder - The folder containing the JSON file (i.e. "Final Cut Pro") * filename - The filename of the JSON file (i.e. "Test.json") * defaultValue - The default value if the JSON file doesn't exist yet.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>A <code>cp.prop</code> instance.</li><br /></ul>                                           |

#### [read](#read)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.json.read(path) -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Attempts to read the specified path as a JSON file.                                                                                         |
| **Parameters**                                       | <ul><br /><li>path      - The JSON file path.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>The JSON file converted into table, or <code>nil</code>.</li><br /></ul>                                           |

#### [write](#write)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.json.write(path, data) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Writes data to a JSON file.                                                                                         |
| **Parameters**                                       | <ul><br /><li>path - The path to where you want to save the JSON file. * data - A table containing data to be encoded as JSON.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li><code>true</code> if successfully saved, otherwise <code>false</code>.</li><br /></ul>                                           |

