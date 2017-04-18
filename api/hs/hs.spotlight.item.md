# [docs](index.md) » hs.spotlight.item
---

This sub-module is used to access the individual results of a spotlightObject or a spotlightGroupObject.

Each Spotlight item contains attributes which you can access with the [hs.spotlight.item:valueForAttribute](#valueForAttribute) method. An array containing common attributes for the type of entity the item represents can be retrieved with the [hs.spotlight.item:attributes](#attributes) method, however this list of attributes is usually not a complete list of the attributes available for a given spotlightItemObject. Many of the known attribute names are included in the `hs.spotlight.commonAttributeKeys` constant array, but even this is not an exhaustive list -- an application may create and assign any key it wishes to an entity for inclusion in the Spotlight metadata database.

For convenience, metamethods have been added to the spotlightItemObjects as a shortcut to the [hs.spotlight.item:valueForAttribute](#valueForAttribute) method; e.g. you can access the value of a specific attribute by treating the attribute as a key name: `spotlightItemObject.kMDItemPath` will return the path to the entity the spotlightItemObject refers to.

## API Overview
* Methods - API calls which can only be made on an object returned by a constructor
 * [attributes](#attributes)
 * [valueForAttribute](#valueforattribute)

## API Documentation

### Methods

#### [attributes](#attributes)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.spotlight.item:attributes() -> table` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a list of attributes associated with the spotlightItemObject                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>an array table containing a list of attributes associated with the result item.</li></ul>          |
| **Notes**                                            | <ul><li>This list of attributes is usually not a complete list of the attributes available for a given spotlightItemObject. Many of the known attribute names are included in the `hs.spotlight.commonAttributeKeys` constant array, but even this is not an exhaustive list -- an application may create and assign any key it wishes to an entity for inclusion in the Spotlight metadata database.</li></ul>                |

#### [valueForAttribute](#valueforattribute)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.spotlight.item:valueForAttribute(attribute) -> value` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the value for the specified attribute of the spotlightItemObject                                                                                         |
| **Parameters**                                       | <ul><li>`attribute` - a string specifying the attribute to get the value of for the spotlightItemObject</li></ul> |
| **Returns**                                          | <ul><li>the attribute value as an appropriate data type or nil if the attribute does not exist or contains no value</li></ul>          |
| **Notes**                                            | <ul><li>See [hs.spotlight.item:attributes](#attributes) for information about possible attribute names.</li></ul>                |

