# [docs](index.md) » cp.collect.Set
---

An implementation of a logical `set`, which contains a single unique
reference of each item in it. For example:

```lua
Set(1,2,2,3) == Set(1,1,2,3,3) == Set(1,2,3)
```

You can combine sets in a couple of ways. For example, a `union`:

```lua
Set(1,2):union(Set(2,3)) == Set(1,2,3)
Set(1,2) | Set(2,3) == Set(1,2,3)
```

...or an `intersection`:

```lua
Set(1,2):intersection(Set(2,3)) == Set(2)
Set(1,2) & Set(2,3) == Set(2)
```

As indicated above, you can use operators for common set operations. Specifically:

* [union](#union) (A ⋃ B):                          `a | b` or `a + b`
* [intersection](#intersection) (A ∩ B):            `a & b`
* [complement](#complement) (A<sup>c</sup>):        `-a`
* [difference](#diference) (A - B):                 `a - b`
* [symetric diference](#symetricDiference) (A ⊕ B)  `a ~ b`

Keep in mind that Lua's operator precedence may be different to that of standard set operations, so it's probably best to group operations in brackets if you combine more than one in a single statement. For example:

```lua
a + b | c ~= a + (b | c)
```

## API Overview
* Constants - Useful values which cannot be changed
 * [everything](#everything)
 * [nothing](#nothing)
* Functions - API calls offered directly by the extension
 * [complement](#complement)
 * [difference](#difference)
 * [has](#has)
 * [intersection](#intersection)
 * [is](#is)
 * [isComplement](#iscomplement)
 * [size](#size)
 * [symetricDifference](#symetricdifference)
 * [union](#union)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [complement](#complement)
 * [difference](#difference)
 * [has](#has)
 * [intersection](#intersection)
 * [isComplement](#iscomplement)
 * [size](#size)
 * [symetricDifference](#symetricdifference)
 * [union](#union)

## API Documentation

### Constants

#### [everything](#everything)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.Set.everything <cp.collect.Set>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | A `Set` which contains the whole universe. |

#### [nothing](#nothing)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.Set.nothing <cp.collect.Set>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | An empty `Set`. |

### Functions

#### [complement](#complement)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.Set.complement(set) -> cp.collect.Set` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a `Set` which is the complement of the provided set. |
| **Parameters**                                       | <ul><li>set       - The <code>Set</code> to complement.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Set</code>.</li></ul> |

#### [difference](#difference)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.Set.difference(left, right) -> cp.collect.Set` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a new `Set` which is the set of values in `left` that are not in `right`. |
| **Parameters**                                       | <ul><li>left      - The left <code>Set</code>.</li><li>right     - The right <code>Set</code>.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Set</code>.</li></ul> |

#### [has](#has)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.Set.has(set, value) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the set has the specified value. |
| **Parameters**                                       | <ul><li>set   - The <code>Set</code> to check.</li><li>value - The value to check for.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the value is contained in the <code>Set</code>.</li></ul> |

#### [intersection](#intersection)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.Set.intersection(left, right) -> cp.collect.Set` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      |  |
| **Parameters**                                       | <ul><li>left      - The left <code>Set</code></li><li>right     - The right <code>Set</code>.</li></ul> |
| **Returns**                                          | <ul><li>A new <code>Set</code> which contains an intersection <code>left</code> and <code>right</code>.</li></ul> |

#### [is](#is)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.Set.is(thing) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the `thing` is a `Set`. |
| **Parameters**                                       | <ul><li>thing     - The thing to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if it is a <code>Set</code>.</li></ul> |

#### [isComplement](#iscomplement)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.Set.isComplement(set) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Checks if the set is a complement set. |
| **Parameters**                                       | <ul><li>set       - The set to check.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the set is a complement.</li></ul> |

#### [size](#size)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.Set.size(set) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the size of the set. |
| **Parameters**                                       | <ul><li>set   - The set to find the size of.</li></ul> |
| **Returns**                                          | <ul><li>the number of values in the set, or the number of values removed from a complement set.</li></ul> |
| **Notes**                                            | <ul><li>If the set is empty, <code>0</code> is returned.</li><li>If the set is a complement, this will return a negative number indicating how many values have been removed from the universal set of all things.</li><li>If the set is a complement of an empty set, <code>nil</code> is returned to indicate the size is infinite.</li></ul> |

#### [symetricDifference](#symetricdifference)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.Set.symetricDifference(left, right) -> cp.collect.Set` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Performs a symetric difference of keys with a value of `true` in the left and right table into a new table. |
| **Parameters**                                       | <ul><li>left      - The left <code>Set</code>.</li><li>right     - The right <code>Set</code>.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Set</code>.</li></ul> |

#### [union](#union)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.Set.union(left, right) -> cp.collect.Set` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a new `Set` which is a union of the `left` and `right` |
| **Parameters**                                       | <ul><li>left      - The left <code>Set</code>.</li><li>right     - The right <code>Set</code>.</li></ul> |
| **Returns**                                          | <ul><li>A new <code>Set</code> which contains a union of the <code>left</code> and <code>right</code> <code>Set</code>s.</li></ul> |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.Set.new(...) -> cp.collect.Set` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new `Set` instance, containing the items in the parameter list. |
| **Parameters**                                       | <ul><li>The set items.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Set</code> instance.</li></ul> |

### Methods

#### [complement](#complement)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.Set:complement() -> cp.collect.Set` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a new `Set` which is the complement of the current `Set`. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Set</code>.</li></ul> |
| **Notes**                                            | <ul><li>You can also use the <code>-</code> or <code>~</code> prefix operators. E.g. <code>-a</code> or <code>~a</code>.</li></ul> |

#### [difference](#difference)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.Set:difference(right) -> cp.collect.Set` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a new `Set` which is the set of values in this `Set` that are not in `right`. |
| **Parameters**                                       | <ul><li>right     - The right <code>Set</code>.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Set</code>.</li></ul> |
| **Notes**                                            | <ul><li>You can also use the <code>-</code> operator. E.g. <code>a - b</code>.</li></ul> |

#### [has](#has)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.Set:has(value) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Checks if this set has the specified value. |
| **Parameters**                                       | <ul><li>value     - The value to check for.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the <code>Set</code> contains the <code>value</code>.</li></ul> |
| **Notes**                                            | <ul><li>You can also check for specific values via <code>mySet['key']</code> or <code>mySet.key</code>.</li></ul> |

#### [intersection](#intersection)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.Set:intersection(...) -> cp.collect.Set` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Creates a new `Set` which is an intersection of the current values plus other `Set`s passed in. |
| **Parameters**                                       | <ul><li>...       - The list of <code>Set</code>s to create an intersection from.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Set</code>.</li></ul> |
| **Notes**                                            | <ul><li>You can also use the <code>&amp;</code> operator. E.g. <code>a &amp; b</code>.</li></ul> |

#### [isComplement](#iscomplement)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.Set:isComplement() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Checks if the set is a complement set. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the set is a complement.</li></ul> |

#### [size](#size)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.Set:size() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the size of the `Set`. If the set is a complement, this will return a negative number indicating |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the number of values in the set, or the number of values removed from a complement set.</li></ul> |
| **Notes**                                            | <ul><li>If the set is empty, <code>0</code> is returned.</li><li>If the set is a complement, this will return a negative number indicating how many values have been removed from the universal set of all things.</li><li>If the set is a complement of an empty set, <code>nil</code> is returned to indicate the size is infinite.</li></ul> |

#### [symetricDifference](#symetricdifference)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.Set:symetricDifference(right) -> cp.collect.Set` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Performs a symetric difference of keys with a value of `true` in the left and right table into a new table. |
| **Parameters**                                       | <ul><li>right     - The right <code>Set</code>.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Set</code>.</li></ul> |
| **Notes**                                            | <ul><li>You can also use the <code>~</code> operator. E.g. <code>a ~ b</code>.</li></ul> |

#### [union](#union)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.collect.Set:union(...) -> cp.collect.Set` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Creates a new set which is a union of the current set plus other `Set`s passed in. |
| **Parameters**                                       | <ul><li>...       - The list of <code>Set</code>s to create a union from.</li></ul> |
| **Returns**                                          | <ul><li>The new <code>Set</code> which is a union.</li></ul> |
| **Notes**                                            | <ul><li>You can also use the <code>\|</code> or <code>+</code> operator. E.g. <code>a \| b</code> or <code>a + b</code>.</li></ul> |

