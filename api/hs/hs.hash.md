# [docs](index.md) » hs.hash
---

Various hashing algorithms

## API Overview
* Functions - API calls offered directly by the extension
 * [hmacMD5](#hmacmd5)
 * [hmacSHA1](#hmacsha1)
 * [hmacSHA256](#hmacsha256)
 * [hmacSHA512](#hmacsha512)
 * [MD5](#md5)
 * [SHA1](#sha1)
 * [SHA256](#sha256)
 * [SHA512](#sha512)

## API Documentation

### Functions

#### [hmacMD5](#hmacmd5)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hash.hmacMD5(key, data) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Calculates an HMAC using a key and an MD5 hash |
| **Parameters**                                       | <ul><li>key - A string containing a secret key to use</li><li>data - A string containing the data to hash</li></ul> |
| **Returns**                                          | <ul><li>A string containing the hash of the supplied data</li></ul> |

#### [hmacSHA1](#hmacsha1)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hash.hmacSHA1(key, data) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Calculates an HMAC using a key and a SHA1 hash |
| **Parameters**                                       | <ul><li>key - A string containing a secret key to use</li><li>data - A string containing the data to hash</li></ul> |
| **Returns**                                          | <ul><li>A string containing the hash of the supplied data</li></ul> |

#### [hmacSHA256](#hmacsha256)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hash.hmacSHA256(key, data) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Calculates an HMAC using a key and a SHA256 hash |
| **Parameters**                                       | <ul><li>key - A string containing a secret key to use</li><li>data - A string containing the data to hash</li></ul> |
| **Returns**                                          | <ul><li>A string containing the hash of the supplied data</li></ul> |

#### [hmacSHA512](#hmacsha512)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hash.hmacSHA512(key, data) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Calculates an HMAC using a key and a SHA512 hash |
| **Parameters**                                       | <ul><li>key - A string containing a secret key to use</li><li>data - A string containing the data to hash</li></ul> |
| **Returns**                                          | <ul><li>A string containing the hash of the supplied data</li></ul> |

#### [MD5](#md5)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hash.MD5(data) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Calculates an MD5 hash |
| **Parameters**                                       | <ul><li>data - A string containing some data to hash</li></ul> |
| **Returns**                                          | <ul><li>A string containing the hash of the supplied data</li></ul> |

#### [SHA1](#sha1)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hash.SHA1(data) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Calculates an SHA1 hash |
| **Parameters**                                       | <ul><li>data - A string containing some data to hash</li></ul> |
| **Returns**                                          | <ul><li>A string containing the hash of the supplied data</li></ul> |

#### [SHA256](#sha256)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hash.SHA256(data) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Calculates an SHA256 hash |
| **Parameters**                                       | <ul><li>data - A string containing some data to hash</li></ul> |
| **Returns**                                          | <ul><li>A string containing the hash of the supplied data</li></ul> |

#### [SHA512](#sha512)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.hash.SHA512(data) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Calculates an SHA512 hash |
| **Parameters**                                       | <ul><li>data - A string containing some data to hash</li></ul> |
| **Returns**                                          | <ul><li>A string containing the hash of the supplied data</li></ul> |

