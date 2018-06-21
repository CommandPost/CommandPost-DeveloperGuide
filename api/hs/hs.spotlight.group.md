# [docs](index.md) » hs.spotlight.group
---

This sub-module is used to access results to a spotlightObject query which have been grouped by one or more attribute values.

A spotlightGroupObject is a special object created when you specify one or more grouping attributes with [hs.spotlight:groupingAttributes](#groupingAttributes). Spotlight items which match the Spotlight query and share a common value for the specified attribute will be grouped in objects you can retrieve with the [hs.spotlight:groupedResults](#groupedResults) method. This method returns an array of spotlightGroupObjects.

For each spotlightGroupObject you can identify the attribute and value the grouping represents with the [hs.spotlight.group:attribute](#attribute) and [hs.spotlight.group:value](#value) methods.  An array of the results which belong to the group can be retrieved with the [hs.spotlight.group:resultAtIndex](#resultAtIndex) method.  For convenience, metamethods have been added to the spotlightGroupObject which make accessing individual results easier:  an individual spotlightItemObject may be accessed from a spotlightGroupObject by treating the spotlightGroupObject like an array; e.g. `spotlightGroupObject[n]` will access the n'th spotlightItemObject in the grouped results.

## API Overview
* Methods - API calls which can only be made on an object returned by a constructor
 * [attribute](#attribute)
 * [count](#count)
 * [resultAtIndex](#resultatindex)
 * [subgroups](#subgroups)
 * [value](#value)

## API Documentation

### Methods

#### [attribute](#attribute)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spotlight.group:attribute() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the name of the attribute the spotlightGroupObject results are grouped by.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">the attribute name as a string</li></ul>          |

#### [count](#count)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spotlight.group:count() -> integer` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the number of query results contained in the spotlightGroupObject.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">an integer specifying the number of results that match the attribute and value represented by this spotlightGroup object.</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">For convenience, metamethods have been added to the spotlightGroupObject which allow you to use `#spotlightGroupObject` as a shortcut for `spotlightGroupObject:count()`.</li></ul>                |

#### [resultAtIndex](#resultatindex)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spotlight.group:resultAtIndex(index) -> spotlightItemObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the spotlightItemObject at the specified index of the spotlightGroupObject                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">`index` - an integer specifying the index of the result to return.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">the spotlightItemObject at the specified index or an error if the index is out of bounds.</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">For convenience, metamethods have been added to the spotlightGroupObject which allow you to use `spotlightGroupObject[index]` as a shortcut for `spotlightGroupObject:resultAtIndex(index)`.</li></ul>                |

#### [subgroups](#subgroups)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spotlight.group:subgroups() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the subgroups of the spotlightGroupObject                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">an array table containing the subgroups of the spotlightGroupObject or nil if no subgroups exist</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">Subgroups are created when you supply more than one grouping attribute to `hs.spotlight:groupingAttributes`.</li></ul>                |

#### [value](#value)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.spotlight.group:value() -> value` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the value for the attribute the spotlightGroupObject results are grouped by.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">None</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">the attribute value as an appropriate data type</li></ul>          |

