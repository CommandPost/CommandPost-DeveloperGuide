# [docs](index.md) » hs.hash
---

Various hashing algorithms

## API Overview
* Functions - API calls offered directly by the extension
 * [MD5](#MD5)
 * [SHA1](#SHA1)
 * [SHA256](#SHA256)
 * [SHA512](#SHA512)
 * [hmacMD5](#hmacMD5)
 * [hmacSHA1](#hmacSHA1)
 * [hmacSHA256](#hmacSHA256)
 * [hmacSHA512](#hmacSHA512)

## API Documentation

### Functions

| [MD5](#MD5)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.hash.MD5(data) -> string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Calculates an MD5 hash                                                                     |
| **Parameters**                              | <ul><li>data - A string containing some data to hash</li></ul> |
| **Returns**                                 | <ul><li>A string containing the hash of the supplied data</li></ul>          |

| [SHA1](#SHA1)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.hash.SHA1(data) -> string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Calculates an SHA1 hash                                                                     |
| **Parameters**                              | <ul><li>data - A string containing some data to hash</li></ul> |
| **Returns**                                 | <ul><li>A string containing the hash of the supplied data</li></ul>          |

| [SHA256](#SHA256)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.hash.SHA256(data) -> string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Calculates an SHA256 hash                                                                     |
| **Parameters**                              | <ul><li>data - A string containing some data to hash</li></ul> |
| **Returns**                                 | <ul><li>A string containing the hash of the supplied data</li></ul>          |

| [SHA512](#SHA512)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.hash.SHA512(data) -> string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Calculates an SHA512 hash                                                                     |
| **Parameters**                              | <ul><li>data - A string containing some data to hash</li></ul> |
| **Returns**                                 | <ul><li>A string containing the hash of the supplied data</li></ul>          |

| [hmacMD5](#hmacMD5)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.hash.hmacMD5(key, data) -> string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Calculates an HMAC using a key and an MD5 hash                                                                     |
| **Parameters**                              | <ul><li>key - A string containing a secret key to use</li><li>data - A string containing the data to hash</li></ul> |
| **Returns**                                 | <ul><li>A string containing the hash of the supplied data</li></ul>          |

| [hmacSHA1](#hmacSHA1)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.hash.hmacSHA1(key, data) -> string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Calculates an HMAC using a key and a SHA1 hash                                                                     |
| **Parameters**                              | <ul><li>key - A string containing a secret key to use</li><li>data - A string containing the data to hash</li></ul> |
| **Returns**                                 | <ul><li>A string containing the hash of the supplied data</li></ul>          |

| [hmacSHA256](#hmacSHA256)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.hash.hmacSHA256(key, data) -> string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Calculates an HMAC using a key and a SHA256 hash                                                                     |
| **Parameters**                              | <ul><li>key - A string containing a secret key to use</li><li>data - A string containing the data to hash</li></ul> |
| **Returns**                                 | <ul><li>A string containing the hash of the supplied data</li></ul>          |

| [hmacSHA512](#hmacSHA512)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.hash.hmacSHA512(key, data) -> string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Calculates an HMAC using a key and a SHA512 hash                                                                     |
| **Parameters**                              | <ul><li>key - A string containing a secret key to use</li><li>data - A string containing the data to hash</li></ul> |
| **Returns**                                 | <ul><li>A string containing the hash of the supplied data</li></ul>          |
