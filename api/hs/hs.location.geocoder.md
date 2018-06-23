# [docs](index.md) » hs.location.geocoder
---

Converts between GPS coordinates and more user friendly representations like an address or points of interest.

This module converts between GPS coordinates and the user-friendly representation of that coordinate. A user-friendly representation of the coordinate typically consists of the street, city, state, and country information corresponding to the given location, but it may also contain a relevant point of interest, landmarks, or other identifying information.

Your computer must have network access for the geocoder object to return detailed placemark information and is rate limited.  Geocoding requests are rate-limited, so making too many requests in a short period of time may cause some of the requests to fail with a network error.

Use of this module does not require Location Services to be enabled for Hammerspoon.

A `placemarkTable` is returned to the callback functions used by the constructor methods of this module.  These tables may contain one or more of the following keys:
 * `addressDictionary`     - a table containing key-value pairs for the components of the address for the placemark
 * `administrativeArea`    - a string containing the state or province associated with the placemark
 * `subAdministrativeArea` - a string containing additional administrative area information for the placemark
 * `areasOfInterest`       - a table as an array of strings describing areas of interest associated with the placemark
 * `country`               - a string containing the name of the country associated with the placemark
 * `countryCode`           - a string containing the standard abbreviation for the country associated with the placemark
 * `inlandWater`           - a string containing the name of the inland water body associated with the placemark
 * `locality`              - a string containing the city associated with the placemark
 * `subLocality`           - a string containing additional city-level information for the placemark
 * `location`              - the locationTable, as described in the `hs.location` module header, for the placemark
 * `name`                  - a string containing the name of the placemark
 * `ocean`                 - a string containing the name of the ocean associated with the placemark
 * `postalCode`            - a string containing the postal code associated with the placemark
 * `region`                - a regionTable, as described in the `hs.location` module header, specifying the he geographic region associated with the placemark
 * `thoroughfare`          - a string containing the street address associated with the placemark
 * `subThoroughfare`       - a string containing additional street-level information for the placemark
 * `timeZone`              - a string containing the time zone associated with the placemark

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [lookupAddress](#lookupaddress)
 * [lookupAddressNear](#lookupaddressnear)
 * [lookupLocation](#lookuplocation)
* Methods - API calls which can only be made on an object returned by a constructor
 * [cancel](#cancel)
 * [geocoding](#geocoding)

## API Documentation

### Constructors

#### [lookupAddress](#lookupaddress)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.location.geocoder.lookupAddress(address, fn) -> geocoderObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Look up geocoding information for the specified address.                                                                                         |
| **Parameters**                                       | <ul><li><code>address</code> - a string containing address information as commonly expressed in your locale.</li></ul><ul><li><code>fn</code>      - A callback function which should expect 2 arguments and return none:</li></ul><ul><li><code>state</code>  - a boolean indicating whether or not geocoding data was provided</li></ul><ul><li><code>result</code> - if <code>state</code> is true indicating that geocoding was successful, this argument will be a table containing one or more placemarkTables (as described in the module header) containing the geocoding data available for the location.  If <code>state</code> is false, this argument will be a string containing an error message describing the problem encountered.</li></ul>   |
| **Returns**                                          | <ul><li>a geocodingObject</li></ul>            |
| **Notes**                                            | <ul><li>This constructor requires internet access and the callback will be invoked with an error message if the internet is not currently accessible.</li></ul><ul><li>This constructor does not require Location Services to be enabled for Hammerspoon.</li></ul>                 |

#### [lookupAddressNear](#lookupaddressnear)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.location.geocoder.lookupAddressNear(address, [regionTable], fn) -> geocoderObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Look up geocoding information for the specified address.                                                                                         |
| **Parameters**                                       | <ul><li><code>address</code>     - a string containing address information as commonly expressed in your locale.</li></ul><ul><li><code>regionTable</code> - an optional regionTable as described in the <code>hs.location</code> header used to prioritize the order of the results found.  If this parameter is not provided and Location Services is enabled for Hammerspoon, a region containing current location is used.</li></ul><ul><li><code>fn</code>          - A callback function which should expect 2 arguments and return none:</li></ul><ul><li><code>state</code>  - a boolean indicating whether or not geocoding data was provided</li></ul><ul><li><code>result</code> - if <code>state</code> is true indicating that geocoding was successful, this argument will be a table containing one or more placemarkTables (as described in the module header) containing the geocoding data available for the location.  If <code>state</code> is false, this argument will be a string containing an error message describing the problem encountered.</li></ul>   |
| **Returns**                                          | <ul><li>a geocodingObject</li></ul>            |
| **Notes**                                            | <ul><li>This constructor requires internet access and the callback will be invoked with an error message if the internet is not currently accessible.</li></ul><ul><li>This constructor does not require Location Services to be enabled for Hammerspoon.</li></ul><ul><li>While a partial address can be given, the more information you provide, the more likely the results will be useful.  The <code>regionTable</code> only determines sort order if multiple entries are returned, it does not constrain the search.</li></ul>                 |

#### [lookupLocation](#lookuplocation)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.location.geocoder.lookupLocation(locationTable, fn) -> geocoderObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Look up geocoding information for the specified location.                                                                                         |
| **Parameters**                                       | <ul><li><code>locationTable</code> - a locationTable as described in the <code>hs.location</code> header specifying a location to obtain geocoding information about.</li></ul><ul><li><code>fn</code>            - A callback function which should expect 2 arguments and return none:</li></ul><ul><li><code>state</code>  - a boolean indicating whether or not geocoding data was provided</li></ul><ul><li><code>result</code> - if <code>state</code> is true indicating that geocoding was successful, this argument will be a table containing one or more placemarkTables (as described in the module header) containing the geocoding data available for the location.  If <code>state</code> is false, this argument will be a string containing an error message describing the problem encountered.</li></ul>   |
| **Returns**                                          | <ul><li>a geocodingObject</li></ul>            |
| **Notes**                                            | <ul><li>This constructor requires internet access and the callback will be invoked with an error message if the internet is not currently accessible.</li></ul><ul><li>This constructor does not require Location Services to be enabled for Hammerspoon.</li></ul>                 |

### Methods

#### [cancel](#cancel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.location.geocoder:cancel() -> nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Cancels the pending or in progress geocoding request.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>nil to facilitate garbage collection by assigning this result to the geocodeObject</li></ul>            |
| **Notes**                                            | <ul><li>This method has no effect if the geocoding process has already completed.</li></ul>                 |

#### [geocoding](#geocoding)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.location.geocoder:geocoding() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a boolean indicating whether or not the geocoding process is still active.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul>   |
| **Returns**                                          | <ul><li>a boolean indicating if the geocoding process is still active.  If false, then the callback function either has already been called or will be as soon as the main thread of Hammerspoon becomes idle again.</li></ul>            |

