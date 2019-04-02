# [docs](index.md) » cp.ui.ElementCache
---

Provides caching for [Element](cp.ui.Element.md) subclasses that want to cache children.

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [ElementCache](#elementcache)
* Methods - API calls which can only be made on an object returned by a constructor
 * [cachedElement](#cachedelement)
 * [cacheElement](#cacheelement)
 * [clean](#clean)
 * [fetchElement](#fetchelement)
 * [fetchElements](#fetchelements)
 * [reset](#reset)

## API Documentation

### Constructors

#### [ElementCache](#elementcache)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ElementCache(parent[, createFn])` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates and returns a new `ElementCache`, with the specified parent and function which |
| **Parameters**                                       | <ul><li>parent - the parent <a href="cp.ui.Element.md">Element</a> that contains the cached items.</li><li>createFn - a function that will create new <code>Element</code> subclasses based on cached <code>axuielement</code> values.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>ElementCache</code>.</li></ul> |

### Methods

#### [cachedElement](#cachedelement)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ElementCache:cachedElement(cache, ui) -> cp.ui.Element or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the cached [Element](cp.ui.Element.md), if it is present. |
| **Parameters**                                       | <ul><li>ui - The <code>axuielement</code> it is linked to. If not provided, it will be fetched by calling <code>Element:UI()</code>.</li></ul> |
| **Returns**                                          | <ul><li><code>cp.ui.Element</code> or <code>nil</code></li></ul> |

#### [cacheElement](#cacheelement)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ElementCache:cacheElement(element[, ui]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Caches the provided [Element](cp.ui.Element.md). |
| **Parameters**                                       | <ul><li>element - The <a href="cp.ui.Element.md">Element</a></li><li>ui - The <code>axuielement</code> it is linked to. If not provided, it will be fetched by calling <code>Element:UI()</code>.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [clean](#clean)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ElementCache:clean()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Clears the cache of any invalid (aka dead) items. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [fetchElement](#fetchelement)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ElementCache:fetchElement(ui) -> cp.ui.Element or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Retrieves the matching [Element](cp.ui.Element.md) instance from the cache. |
| **Parameters**                                       | <ul><li>ui - The <code>axuielement</code> being fetched for.</li></ul> |
| **Returns**                                          | <ul><li><code>cp.ui.Element</code> or <code>nil</code></li></ul> |

#### [fetchElements](#fetchelements)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ElementCache:fetchElements(uis) -> table of cp.ui.Elements or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Fetches a list of [Element](cp.ui.Element.md) instances linked to the provided `axuielement` list. |
| **Parameters**                                       | <ul><li>uis  - A <code>table</code> of <code>axuielement</code> values.</li></ul> |
| **Returns**                                          | <ul><li>A <code>table</code> of <a href="cp.ui.Element.md">Element</a> values.</li></ul> |
| **Notes**                                            | <ul><li>If any of the provided <code>axuielement</code> values are either not from the parent, or no longer valid, a <code>nil</code> value will be stored in the matching index. Note that in that case, this will break useage of <code>ipairs</code> due to leaving holes in the list.</li></ul> |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.ui.ElementCache:reset() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Removes all cached items from the cache. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

