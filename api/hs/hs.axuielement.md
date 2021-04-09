# [docs](index.md) » hs.axuielement
---

This module allows you to access the accessibility objects of running applications, their windows, menus, and other user interface elements that support the OS X accessibility API.

This module works through the use of axuielementObjects, which is the Hammerspoon representation for an accessibility object.  An accessibility object represents any object or component of an OS X application which can be manipulated through the OS X Accessibility API -- it can be an application, a window, a button, selected text, etc.  As such, it can only support those features and objects within an application that the application developers make available through the Accessibility API.

In addition to the formal methods described in this documentation, dynamic methods exist for accessing element attributes and actions. These will differ somewhat between objects as the specific attributes and actions will depend upon the accessibility object's role and purpose, but the following outlines the basics.

Getting and Setting Attribute values:
 * `object.attribute` is a shortcut for `object:attributeValue(attribute)`
 * `object.attribute = value` is a shortcut for `object:setAttributeValue(attribute, value)`
   * If detecting accessiblity errors that may occur is necessary, you must use the formal methods [hs.axuielement:attributeValue](#attributeValue) and [hs.axuielement:setAttributeValue](#setAttributeValue)
   * Note that setting an attribute value is not guaranteeed to work with either method:
     * internal logic within the receiving application may decline to accept the newly assigned value
     * an accessibility error may occur
     * the element may not be settable (surprisingly this does not return an error, even when [hs.axuielement:isAttributeSettable](#isAttributeSettable) returns false for the attribute specified)
   * If you require confirmation of the change, you will need to check the value of the attribute with one of the methods described above after setting it.

Iteration over Attributes:
 * `for k,v in pairs(object) do ... end` is a shortcut for `for k,_ in ipairs(object:attributeNames()) do local v = object:attributeValue(k) ; ... end` or `for k,v in pairs(object:allAttributeValues()) do ... end` (though see note below)
    * If detecting accessiblity errors that may occur is necessary, you must use one of the formal approaches [hs.axuielement:allAttributeValues](#allAttributeValues) or [hs.axuielement:attributeNames](#attributeNames) and [hs.axuielement:attributeValue](#attributeValue)
   * By default, [hs.axuielement:allAttributeValues](#allAttributeValues) will not include key-value pairs for which the attribute (key) exists for the element but has no assigned value (nil) at the present time. This is because the value of `nil` prevents the key from being retained in the table returned. See [hs.axuielement:allAttributeValues](#allAttributeValues) for details and a workaround.

Iteration over Child Elements (AXChildren):
 * `for i,v in ipairs(object) do ... end` is a shortcut for `for i,v in pairs(object:attributeValue("AXChildren") or {}) do ... end`
   * Note that `object:attributeValue("AXChildren")` *may* return nil if the object does not have the `AXChildren` attribute; the shortcut does not have this limitation.
 * `#object` is a shortcut for `#object:attributeValue("AXChildren")`
 * `object[i]` is a shortcut for `object:attributeValue("AXChildren")[i]`
   * If detecting accessiblity errors that may occur is necessary, you must use the formal method [hs.axuielement:attributeValue](#attributeValue) to get the "AXChildren" attribute.

Actions ([hs.axuielement:actionNames](#actionNames)):
 * `object:do<action>()` is a shortcut for `object:performAction(action)`
   * See [hs.axuielement:performAction](#performAction) for a description of the return values and [hs.axuielement:actionNames](#actionNames) to get a list of actions that the element supports.

ParameterizedAttributes:
 * `object:<attribute>WithParameter(value)` is a shortcut for `object:parameterizedAttributeValue(attribute, value)
   * See [hs.axuielement:parameterizedAttributeValue](#parameterizedAttributeValue) for a description of the return values and [hs.axuielement:parameterizedAttributeNames](#parameterizedAttributeNames) to get a list of parameterized values that the element supports

   * The specific value required for a each parameterized attribute is different and is often application specific thus requiring some experimentation. Notes regarding identified parameter types and thoughts on some still being investigated will be provided in the Hammerspoon Wiki, hopefully shortly after this module becomes part of a Hammerspoon release.

## Submodules
 * [hs.axuielement.axtextmarker](hs.axuielement.axtextmarker.md)
 * [hs.axuielement.observer](hs.axuielement.observer.md)

## API Overview
* Constants - Useful values which cannot be changed
 * [actions](#actions)
 * [attributes](#attributes)
 * [orientations](#orientations)
 * [parameterizedAttributes](#parameterizedattributes)
 * [roles](#roles)
 * [rulerMarkers](#rulermarkers)
 * [sortDirections](#sortdirections)
 * [subroles](#subroles)
 * [units](#units)
* Functions - API calls offered directly by the extension
 * [searchCriteriaFunction](#searchcriteriafunction)
* Constructors - API calls which return an object, typically one that offers API methods
 * [applicationElement](#applicationelement)
 * [applicationElementForPID](#applicationelementforpid)
 * [systemElementAtPosition](#systemelementatposition)
 * [systemWideElement](#systemwideelement)
 * [windowElement](#windowelement)
* Methods - API calls which can only be made on an object returned by a constructor
 * [actionDescription](#actiondescription)
 * [actionNames](#actionnames)
 * [allAttributeValues](#allattributevalues)
 * [allDescendantElements](#alldescendantelements)
 * [asHSApplication](#ashsapplication)
 * [asHSWindow](#ashswindow)
 * [attributeNames](#attributenames)
 * [attributeValue](#attributevalue)
 * [attributeValueCount](#attributevaluecount)
 * [buildTree](#buildtree)
 * [copy](#copy)
 * [elementAtPosition](#elementatposition)
 * [elementSearch](#elementsearch)
 * [isAttributeSettable](#isattributesettable)
 * [isValid](#isvalid)
 * [matchesCriteria](#matchescriteria)
 * [parameterizedAttributeNames](#parameterizedattributenames)
 * [parameterizedAttributeValue](#parameterizedattributevalue)
 * [path](#path)
 * [performAction](#performaction)
 * [pid](#pid)
 * [setAttributeValue](#setattributevalue)
 * [setTimeout](#settimeout)

## API Documentation

### Constants

#### [actions](#actions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement.actions[]` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | A table of common accessibility object action names, provided for reference. |
| **Notes**                                            | <ul><li>this table is provided for reference only and is not intended to be comprehensive.</li><li>you can view the contents of this table from the Hammerspoon console by typing in <code>hs.axuielement.actions</code></li></ul> |

#### [attributes](#attributes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement.attributes[]` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | A table of common accessibility object attribute names which may be used with [hs.axuielement:elementSearch](#elementSearch) or [hs.axuielement:matchesCriteria](#matchesCriteria) as keys in the match criteria argument. |
| **Notes**                                            | <ul><li>This table is provided for reference only and is not intended to be comprehensive.</li><li>You can view the contents of this table from the Hammerspoon console by typing in <code>hs.axuielement.attributes</code></li></ul> |

#### [orientations](#orientations)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement.orientations[]` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | A table of orientation types which may be used with [hs.axuielement:elementSearch](#elementSearch) or [hs.axuielement:matchesCriteria](#matchesCriteria) as attribute values for "AXOrientation" in the match criteria argument. |
| **Notes**                                            | <ul><li>this table is provided for reference only and may not be comprehensive.</li><li>you can view the contents of this table from the Hammerspoon console by typing in <code>hs.axuielement.orientations</code></li></ul> |

#### [parameterizedAttributes](#parameterizedattributes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement.parameterizedAttributes[]` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | A table of common accessibility object parameterized attribute names, provided for reference. |
| **Notes**                                            | <ul><li>this table is provided for reference only and is not intended to be comprehensive.</li><li>you can view the contents of this table from the Hammerspoon console by typing in <code>hs.axuielement.parameterizedAttributes</code></li></ul> |

#### [roles](#roles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement.roles[]` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | A table of common accessibility object roles which may be used with [hs.axuielement:elementSearch](#elementSearch) or [hs.axuielement:matchesCriteria](#matchesCriteria) as attribute values for "AXRole" in the match criteria argument. |
| **Notes**                                            | <ul><li>this table is provided for reference only and is not intended to be comprehensive.</li><li>you can view the contents of this table from the Hammerspoon console by typing in <code>hs.axuielement.roles</code></li></ul> |

#### [rulerMarkers](#rulermarkers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement.rulerMarkers[]` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | A table of ruler marker types which may be used with [hs.axuielement:elementSearch](#elementSearch) or [hs.axuielement:matchesCriteria](#matchesCriteria) as attribute values for "AXMarkerType" in the match criteria argument. |
| **Notes**                                            | <ul><li>this table is provided for reference only and may not be comprehensive.</li><li>you can view the contents of this table from the Hammerspoon console by typing in <code>hs.axuielement.rulerMarkers</code></li></ul> |

#### [sortDirections](#sortdirections)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement.sortDirections[]` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | A table of sort direction types which may be used with [hs.axuielement:elementSearch](#elementSearch) or [hs.axuielement:matchesCriteria](#matchesCriteria) as attribute values for "AXSortDirection" in the match criteria argument. |
| **Notes**                                            | <ul><li>this table is provided for reference only and may not be comprehensive.</li><li>you can view the contents of this table from the Hammerspoon console by typing in <code>hs.axuielement.sortDirections</code></li></ul> |

#### [subroles](#subroles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement.subroles[]` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | A table of common accessibility object subroles which may be used with [hs.axuielement:elementSearch](#elementSearch) or [hs.axuielement:matchesCriteria](#matchesCriteria) as attribute values for "AXSubrole" in the match criteria argument. |
| **Notes**                                            | <ul><li>this table is provided for reference only and is not intended to be comprehensive.</li><li>you can view the contents of this table from the Hammerspoon console by typing in <code>hs.axuielement.subroles</code></li></ul> |

#### [units](#units)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement.units[]` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | A table of measurement unit types which may be used with [hs.axuielement:elementSearch](#elementSearch) or [hs.axuielement:matchesCriteria](#matchesCriteria) as attribute values for attributes which specify measurement unit types (e.g. "AXUnits", "AXHorizontalUnits", and "AXVerticalUnits") in the match criteria argument. |
| **Notes**                                            | <ul><li>this table is provided for reference only and may not be comprehensive.</li><li>you can view the contents of this table from the Hammerspoon console by typing in <code>hs.axuielement.units</code></li></ul> |

### Functions

#### [searchCriteriaFunction](#searchcriteriafunction)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement.searchCriteriaFunction(criteria) -> function` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a function for use with [hs.axuielement:elementSearch](#elementSearch) that uses [hs.axuielement:matchesCriteria](#matchesCriteria) with the specified criteria. |
| **Parameters**                                       | <ul><li><code>criteria</code> - a criteria definition as defined for the <a href="#matchesCriteria">hs.axuielement:matchesCriteria</a> method.</li></ul> |
| **Returns**                                          | <ul><li>a function which can be used as the <code>criteriaFunction</code> for <a href="#elementSearch">hs.axuielement:elementSearch</a>.</li></ul> |

### Constructors

#### [applicationElement](#applicationelement)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement.applicationElement(applicationObject) -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Returns the top-level accessibility object for the application specified by the `hs.application` object. |
| **Parameters**                                       | <ul><li><code>applicationObject</code> - the <code>hs.application</code> object for the Application or a string or number which will be passed to <code>hs.application.find</code> to get an <code>hs.application</code> object.</li></ul> |
| **Returns**                                          | <ul><li>an axuielementObject for the application specified</li></ul> |
| **Notes**                                            | <ul><li>if <code>applicationObject</code> is a string or number, only the first item found with <code>hs.application.find</code> will be used by this function to create an axuielementObject.</li></ul> |

#### [applicationElementForPID](#applicationelementforpid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement.applicationElementForPID(pid) -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Returns the top-level accessibility object for the application with the specified process ID. |
| **Parameters**                                       | <ul><li><code>pid</code> - the process ID of the application.</li></ul> |
| **Returns**                                          | <ul><li>an axuielementObject for the application specified, or nil if it cannot be determined</li></ul> |

#### [systemElementAtPosition](#systemelementatposition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement.systemElementAtPosition(x, y | pointTable) -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Returns the accessibility object at the specified position on the screen. The top-left corner of the primary screen is 0, 0. |
| **Parameters**                                       | <ul><li><code>x</code> - the x coordinate of the screen location to test</li><li><code>y</code> - the y coordinate of the screen location to test</li><li><code>pointTable</code> - the x and y coordinates of the screen location to test, provided as a point-table, like the one returned by <code>hs.mouse.getAbsolutePosition</code>. A point-table is a table with key-value pairs for keys <code>x</code> and <code>y</code>.</li></ul> |
| **Returns**                                          | <ul><li>an axuielementObject for the object at the specified coordinates, or nil if no object could be identified.</li></ul> |
| **Notes**                                            | <ul><li>See also <a href="#elementAtPosition">hs.axuielement:elementAtPosition</a> -- this function is a shortcut for <code>hs.axuielement.systemWideElement():elementAtPosition(...)</code>.</li></ul> |

#### [systemWideElement](#systemwideelement)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement.systemWideElement() -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Returns an accessibility object that provides access to system attributes. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the axuielementObject for the system attributes</li></ul> |

#### [windowElement](#windowelement)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement.windowElement(windowObject) -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Returns the accessibility object for the window specified by the `hs.window` object. |
| **Parameters**                                       | <ul><li><code>windowObject</code> - the <code>hs.window</code> object for the window or a string or number which will be passed to <code>hs.window.find</code> to get an <code>hs.window</code> object.</li></ul> |
| **Returns**                                          | <ul><li>an axuielementObject for the window specified</li></ul> |
| **Notes**                                            | <ul><li>if <code>windowObject</code> is a string or number, only the first item found with <code>hs.window.find</code> will be used by this function to create an axuielementObject.</li></ul> |

### Methods

#### [actionDescription](#actiondescription)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement:actionDescription(action) -> string | nil, errString` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a localized description of the specified accessibility object's action. |
| **Parameters**                                       | <ul><li><code>action</code> - the name of the action, as specified by <a href="#actionNames">hs.axuielement:actionNames</a>.</li></ul> |
| **Returns**                                          | <ul><li>a string containing a description of the object's action, nil if no description is available, or nil and an error string if an accessibility error occurred</li></ul> |
| **Notes**                                            | <ul><li>The action descriptions are provided by the target application; as such their accuracy and usefulness rely on the target application's developers.</li></ul> |

#### [actionNames](#actionnames)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement:actionNames() -> table | nil, errString` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a list of all the actions the specified accessibility object can perform. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>an array of the names of all actions supported by the axuielementObject or nil and an error string if an accessibility error occurred</li></ul> |
| **Notes**                                            | <ul><li>Common action names can be found in the <a href="#actions">hs.axuielement.actions</a> table; however, this method will list only those names which are supported by this object, and is not limited to just those in the referenced table.</li></ul> |

#### [allAttributeValues](#allattributevalues)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement:allAttributeValues([includeErrors]) -> table | nil, errString` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a table containing key-value pairs for all attributes of the accessibility object. |
| **Parameters**                                       | <ul><li><code>includeErrors</code> - an optional boolean, default false, that specifies whether attribute names which generate an error when retrieved are included in the returned results.</li></ul> |
| **Returns**                                          | <ul><li>a table with key-value pairs corresponding to the attributes of the accessibility object or nil and an error string if an accessibility error occurred</li></ul> |
| **Notes**                                            | <ul><li>if <code>includeErrors</code> is not specified or is false, then attributes which exist for the element, but currently have no value assigned, will not appear in the table. This is because Lua treats a nil value for a table's key-value pair as an instruction to remove the key from the table, if it currently exists.</li><li>To include attributes which exist but are currently unset, you need to specify <code>includeErrors</code> as true.</li><li>attributes for which no value is currently assigned will be given a table value with the following key-value pairs:<ul><li><code>_code</code> = -25212</li><li><code>error</code> = "Requested value does not exist"</li></ul></li></ul> |

#### [allDescendantElements](#alldescendantelements)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement:allDescendantElements(callback, [withParents]) -> elementSearchObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Query the accessibility object for all child accessibility objects and their descendants |
| **Parameters**                                       | <ul><li><code>callback</code>    - a required function which should expect two arguments: a <code>msg</code> string specifying how the search ended, and a table containing the discovered descendant elements. <code>msg</code> will be "completed" when the traversal has completed normally and will contain a string starting with "**" if it terminates early for some reason (see Notes: section for more information)</li><li><code>withParents</code> - an optional boolean, default false, indicating that the parent of objects (and their descendants) should be collected as well.</li></ul> |
| **Returns**                                          | <ul><li>an elementSearchObject as described in <a href="#elementSearch">hs.axuielement:elementSearch</a></li></ul> |
| **Notes**                                            | <ul><li>This method is syntactic sugar for <code>hs.axuielement:elementSearch(callback, { [includeParents = withParents] })</code>. Please refer to <a href="#elementSearch">hs.axuielement:elementSearch</a> for details about the returned object and callback arguments.</li></ul> |

#### [asHSApplication](#ashsapplication)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement:asHSApplication() -> hs.application object | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | If the element referes to an application, return an `hs.application` object for the element. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>if the element refers to an application, return an <code>hs.application</code> object for the element ; otherwise return nil</li></ul> |
| **Notes**                                            | <ul><li>An element is considered an application by this method if it has an AXRole of AXApplication and has a process identifier (pid).</li></ul> |

#### [asHSWindow](#ashswindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement:asHSWindow() -> hs.window object | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | If the element referes to a window, return an `hs.window` object for the element. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>if the element refers to a window, return an <code>hs.window</code> object for the element ; otherwise return nil</li></ul> |
| **Notes**                                            | <ul><li>An element is considered a window by this method if it has an AXRole of AXWindow.</li></ul> |

#### [attributeNames](#attributenames)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement:attributeNames() -> table | nil, errString` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a list of all the attributes supported by the specified accessibility object. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>an array of the names of all attributes supported by the axuielementObject or nil and an error string if an accessibility error occurred</li></ul> |
| **Notes**                                            | <ul><li>Common attribute names can be found in the <a href="#attributes">hs.axuielement.attributes</a> tables; however, this method will list only those names which are supported by this object, and is not limited to just those in the referenced table.</li></ul> |

#### [attributeValue](#attributevalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement:attributeValue(attribute) -> value | nil, errString` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the value of an accessibility object's attribute. |
| **Parameters**                                       | <ul><li><code>attribute</code> - the name of the attribute, as specified by <a href="#attributeNames">hs.axuielement:attributeNames</a>.</li></ul> |
| **Returns**                                          | <ul><li>the current value of the attribute, nil if the attribute has no value, or nil and an error string if an accessibility error occurred</li></ul> |

#### [attributeValueCount](#attributevaluecount)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement:attributeValueCount(attribute) -> integer | nil, errString` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the count of the array of an accessibility object's attribute value. |
| **Parameters**                                       | <ul><li><code>attribute</code> - the name of the attribute, as specified by <a href="#attributeNames">hs.axuielement:attributeNames</a>.</li></ul> |
| **Returns**                                          | <ul><li>the number of items in the value for the attribute, if it is an array, or nil and an error string if an accessibility error occurred</li></ul> |

#### [buildTree](#buildtree)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement:buildTree(callback, [depth], [withParents]) -> elementSearchObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Captures all of the available information for the accessibility object and its descendants and returns it in a table for inspection. |
| **Parameters**                                       | <ul><li><code>callback</code> - a required function which should expect two arguments: a <code>msg</code> string specifying how the search ended, and a table containing the recorded information. <code>msg</code> will be "completed" when the search has completed normally (or reached the specified depth) and will contain a string starting with "**" if it terminates early for some reason (see Notes: section for more information)</li><li><code>depth</code>    - an optional integer, default <code>math.huge</code>, specifying the maximum depth from the initial accessibility object that should be visited to identify descendant elements and their attributes.</li><li><code>withParents</code> - an optional boolean, default false, specifying whether or not an element's (or descendant's) attributes for <code>AXParent</code> and <code>AXTopLevelUIElement</code> should also be visited when identifying additional elements to include in the results table.</li></ul> |
| **Returns**                                          | <ul><li>an elementSearchObject as described in <a href="#elementSearch">hs.axuielement:elementSearch</a></li></ul> |
| **Notes**                                            | <ul><li>The format of the <code>results</code> table passed to the callback for this method is primarily for debugging and exploratory purposes and may not be arranged for easy programatic evaluation.</li></ul> |

#### [copy](#copy)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement:copy() -> axuielementObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Return a duplicate userdata reference to the Accessibility object. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a new userdata object representing a new reference to the Accessibility object.</li></ul> |

#### [elementAtPosition](#elementatposition)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement:elementAtPosition(x, y | pointTable) -> axuielementObject | nil, errString` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the accessibility object at the specified position on the screen. The top-left corner of the primary screen is 0, 0. |
| **Parameters**                                       | <ul><li><code>x</code> - the x coordinate of the screen location to tes</li><li><code>y</code> - the y coordinate of the screen location to test</li><li><code>pointTable</code> - the x and y coordinates of the screen location to test, provided as a point-table, like the one returned by <code>hs.mouse.getAbsolutePosition</code>. A point-table is a table with key-value pairs for keys <code>x</code> and <code>y</code>.</li></ul> |
| **Returns**                                          | <ul><li>an axuielementObject for the object at the specified coordinates, or nil and an error string if no object could be identified or an accessibility error occurred</li></ul> |
| **Notes**                                            | <ul><li>This method can only be called on an axuielementObject that represents an application or the system-wide element (see <a href="#systemWideElement">hs.axuielement.systemWideElement</a>).</li></ul> |

#### [elementSearch](#elementsearch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement:elementSearch(callback, [criteria], [namedModifiers]) -> elementSearchObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Search for and generate a table of the accessibility elements for the attributes and descendants of this object based on the specified criteria. |
| **Parameters**                                       | <ul><li><code>callback</code>       - a (usually) required function which will receive the results of this search. The callback should expect three arguments and return none. The arguments to the callback function will be <code>msg</code>, a string specifying how the search ended and <code>results</code>, the elementSearchObject containing the requested results, and the number of items added to the results (see <code>count</code> in <code>namedModifiers</code>). <code>msg</code> will be "completed" if the search completes normally, or a string starting with "**" if it is terminated early (see Returns: and Notes: for more details).</li><li><code>criteria</code>       - an optional function which should accept one argument (the current element being examined) and return true if it should be included in the results or false if it should be rejected. See <a href="#searchCriteriaFunction">hs.axuielement.searchCriteriaFunction</a> to create a search function that uses <a href="#matchesCriteria">hs.axuielement:matchesCriteria</a> for evaluation.</li><li><code>namedModifiers</code> - an optional table specifying key-value pairs that further modify or control the search. This table may contain 0 or more of the following keys:</li><li><code>count</code>          - an optional integer, default <code>math.huge</code>, specifying the maximum number of matches to collect before ending the search and invoking the callback. You can continue the search to find additional elements by invoking <code>elementSearchObject:next()</code> (described below in the <code>Returns</code> section) on the return value of this method, or on the results argument passed to the callback.</li><li><code>depth</code>          - an optional integer, default <code>math.huge</code>, specifying the maximum number of steps (descendants) from the initial accessibility element the search should visit. If you know that your desired element(s) are relatively close to your starting element, setting this to a lower value can significantly speed up the search.</li></ul> |
| **Returns**                                          | <ul><li>an elementSearchObject which contains metamethods allowing you to check to see if the process has completed and cancel it early if desired. The methods include:</li><li><code>elementSearchObject:cancel([reason])</code> - cancels the current search and invokes the callback with the partial results already collected. If you specify <code>reason</code>, the <code>msg</code> argument for the callback will be <code>** &lt;reason&gt;</code>; otherwise it will be "** cancelled".</li><li><code>elementSearchObject:isRunning()</code>      - returns true if the search is currently ongoing or false if it has completed or been cancelled.</li><li><code>elementSearchObject:matched()</code>        - returns an integer specifying the number of elements which have already been found that meet the specified criteria function.</li><li><code>elementSearchObject:runTime()</code>        - returns an integer specifying the number of seconds spent performing this search. Note that this is <em>not</em> an accurate measure of how much time a given search will always take because the time will be greatly affected by how much other activity is occurring within Hammerspoon and on the users computer. Resuming a cancelled search or a search which invoked the callback because it reached <code>count</code> items with the <code>next</code> method (descibed below) will cause this number to begin increasing again to provide a cumulative total of time spent performing the search; time between when the callback is invoked and the <code>next</code> method is invoked is not included.</li><li><code>elementSearchObject:visited()</code>        - returns an integer specifying the number of elements which have been examined during the search so far.</li></ul> |
| **Notes**                                            | <ul><li>This method utilizes coroutines to keep Hammerspoon responsive, but may be slow to complete if <code>includeParents</code> is true, if you do not specify <code>depth</code>, or if you start from an element that has a lot of descendants (e.g. the application element for a web browser). This is dependent entirely upon how many active accessibility elements the target application defines and where you begin your search and cannot reliably be determined up front, so you may need to experiment to find the best balance for your specific requirements.</li></ul> |

#### [isAttributeSettable](#isattributesettable)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement:isAttributeSettable(attribute) -> boolean | nil, errString` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns whether the specified accessibility object's attribute can be modified. |
| **Parameters**                                       | <ul><li><code>attribute</code> - the name of the attribute, as specified by <a href="#attributeNames">hs.axuielement:attributeNames</a>.</li></ul> |
| **Returns**                                          | <ul><li>a boolean value indicating whether or not the value of the parameter can be modified or nil and an error string if an accessibility error occurred</li></ul> |

#### [isValid](#isvalid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement:isValid() -> boolean | nil, errString` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns whether the specified accessibility object is still valid. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a boolean value indicating whether or not the accessibility object is still valid or nil and an error string if any other accessibility error occurred</li></ul> |
| **Notes**                                            | <ul><li>an accessibilityObject can become invalid for a variety of reasons, including but not limited to the element referred to no longer being available (e.g. an element referring to a window or one of its descendants that has been closed) or the application terminating.</li></ul> |

#### [matchesCriteria](#matchescriteria)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement:matchesCriteria(criteria) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns true if the axuielementObject matches the specified criteria or false if it does not. |
| **Parameters**                                       | <ul><li><code>criteria</code>  - the criteria to compare against the accessibility object</li></ul> |
| **Returns**                                          | <ul><li>true if the axuielementObject matches the criteria, false if it does not.</li></ul> |
| **Notes**                                            | <ul><li>the <code>criteria</code> argument must be one of the following:</li><li>a single string, specifying the value the element's AXRole attribute must equal for a positive match</li></ul> |

#### [parameterizedAttributeNames](#parameterizedattributenames)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement:parameterizedAttributeNames() -> table | nil, errString` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a list of all the parameterized attributes supported by the specified accessibility object. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>an array of the names of all parameterized attributes supported by the axuielementObject or nil and an error string if an accessibility error occurred</li></ul> |

#### [parameterizedAttributeValue](#parameterizedattributevalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement:parameterizedAttributeValue(attribute, parameter) -> value | nil, errString` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the value of an accessibility object's parameterized attribute. |
| **Parameters**                                       | <ul><li><code>attribute</code> - the name of the attribute, as specified by <a href="#parameterizedAttributeNames">hs.axuielement:parameterizedAttributeNames</a>.</li><li><code>parameter</code> - the parameter required by the paramaterized attribute.</li></ul> |
| **Returns**                                          | <ul><li>the current value of the parameterized attribute, nil if the parameterized attribute has no value, or nil and an error string if an accessibility error occurred</li></ul> |
| **Notes**                                            | <ul><li>The specific parameter required for a each parameterized attribute is different and is often application specific thus requiring some experimentation. Notes regarding identified parameter types and thoughts on some still being investigated will be provided in the Hammerspoon Wiki, hopefully shortly after this module becomes part of a Hammerspoon release.</li></ul> |

#### [path](#path)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement:path() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a table of axuielements tracing this object through its parent objects to the root for this element, most likely an application object or the system wide object. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a table containing this object and 0 or more parent objects representing the path from the root object to this element.</li></ul> |
| **Notes**                                            | <ul><li>this object will always exist as the last element in the table (e.g. at <code>table[#table]</code>) with its most immediate parent at <code>#table - 1</code>, etc. until the rootmost object for this element is reached at index position 1.</li></ul> |

#### [performAction](#performaction)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement:performAction(action) -> axuielement | false | nil, errString` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Requests that the specified accessibility object perform the specified action. |
| **Parameters**                                       | <ul><li><code>action</code> - the name of the action, as specified by <a href="#actionNames">hs.axuielement:actionNames</a>.</li></ul> |
| **Returns**                                          | <ul><li>if the requested action was accepted by the target, returns the axuielementObject; if the requested action was rejected, returns false; otherwise returns nil and an error string if an accessibility error occurred</li></ul> |
| **Notes**                                            | <ul><li>The return value only suggests success or failure, but is not a guarantee.  The receiving application may have internal logic which prevents the action from occurring at this time for some reason, even though this method returns success (the axuielementObject).  Contrawise, the requested action may trigger a requirement for a response from the user and thus appear to time out, causing this method to return false or nil.</li></ul> |

#### [pid](#pid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement:pid() -> integer | nil, errString` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the process ID associated with the specified accessibility object. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the process ID for the application to which the accessibility object ultimately belongs or nil and an error string if an accessibility error occurred</li></ul> |

#### [setAttributeValue](#setattributevalue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement:setAttributeValue(attribute, value) -> axuielementObject  | nil, errString` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the accessibility object's attribute to the specified value. |
| **Parameters**                                       | <ul><li><code>attribute</code> - the name of the attribute, as specified by <a href="#attributeNames">hs.axuielement:attributeNames</a>.</li><li><code>value</code>     - the value to assign to the attribute</li></ul> |
| **Returns**                                          | <ul><li>the axuielementObject on success; nil and an error string if the attribute could not be set or an accessibility error occurred.</li></ul> |

#### [setTimeout](#settimeout)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.axuielement:setTimeout(value) -> axuielementObject | nil, errString` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets the timeout value used accessibility queries performed from this element. |
| **Parameters**                                       | <ul><li><code>value</code> - the number of seconds for the new timeout value. Must be 0 or positive.</li></ul> |
| **Returns**                                          | <ul><li>the axuielementObject or nil and an error string if an accessibility error occurred</li></ul> |
| **Notes**                                            | <ul><li>To change the global timeout affecting all queries on elements which do not have a specific timeout set, use this method on the systemwide element (see <a href="#systemWideElement">hs.axuielement.systemWideElement</a>.</li><li>Changing the timeout value for an axuielement object only changes the value for that specific element -- other axuieleement objects that may refer to the identical accessibiity item are not affected.</li></ul> |

