# [docs](index.md) » hs.bonjour
---

Find and publish network services advertised by multicast DNS (Bonjour) with Hammerspoon.

This module will allow you to discover services advertised on your network through multicast DNS and publish services offered by your computer.

## Submodules
 * [hs.bonjour.service](hs.bonjour.service.md)

## API Overview
* Functions - API calls offered directly by the extension
 * [machineServices](#machineservices)
 * [networkServices](#networkservices)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [findBrowsableDomains](#findbrowsabledomains)
 * [findRegistrationDomains](#findregistrationdomains)
 * [findServices](#findservices)
 * [includesPeerToPeer](#includespeertopeer)
 * [stop](#stop)

## API Documentation

### Functions

#### [machineServices](#machineservices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.bonjour.machineServices(target, callback) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Polls a host for the service types it is advertising via multicast DNS. |
| **Parameters**                                       | <ul><li><code>target</code>   - a string specifying the target host to query for advertised service types</li><li><code>callback</code> - a callback function which will be invoked when the service type query has completed. The callback should expect one argument which will either be an array of strings specifying the service types the target is advertising or a string specifying the error that occurred.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |
| **Notes**                                            | <ul><li>this function may not work for all clients implementing multicast DNS; it has been successfully tested with macOS and Linux targets running the Avahi Daemon service, but has generally returned an error when used with minimalist implementations found in common IOT devices and embedded electronics.</li></ul> |

#### [networkServices](#networkservices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.bonjour.networkServices(callback, [timeout]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a list of service types being advertised on your local network. |
| **Parameters**                                       | <ul><li><code>callback</code> - a callback function which will be invoked when the services query has completed. The callback should expect one argument: an array of strings specifying the service types discovered on the local network.</li><li><code>timeout</code>  - an optional number, default 5, specifying the maximum number of seconds after the most recently received service type Hammerspoon should wait trying to identify advertised service types before finishing its query and invoking the callback.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |
| **Notes**                                            | <ul><li>This function is a convienence wrapper to <a href="#findServices">hs.bonjour:findServices</a> which collects the results from multiple callbacks made to <code>findServices</code> and returns them all at once to the callback function provided as an argument to this function.</li></ul> |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.bonjour.new() -> browserObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new network service browser that finds published services on a network using multicast DNS. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a new browserObject or nil if an error occurs</li></ul> |

### Methods

#### [findBrowsableDomains](#findbrowsabledomains)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.bonjour:findBrowsableDomains(callback) -> browserObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Return a list of zero-conf and bonjour domains visibile to the users computer. |
| **Parameters**                                       | <ul><li><code>callback</code> - a function which will be invoked as visible domains are discovered. The function should accept the following parameters and return none:</li><li><code>browserObject</code>    - the userdata object for the browserObject which initiated the search</li><li><code>type</code>             - a string which will be 'domain' or 'error'<ul><li>if <code>type</code> == 'domain', the remaining arguments will be:</li><li><code>added</code>        - a boolean value indicating whether this callback invocation represents a newly discovered or added domain (true) or that the domain has been removed from the network (false)</li><li><code>domain</code>       - a string specifying the name of the domain discovered or removed</li><li><code>moreExpected</code> - a boolean value indicating whether or not the browser expects to discover additional domains or not.</li><li>if <code>type</code> == 'error', the remaining arguments will be:</li><li><code>errorString</code>  - a string specifying the error which has occurred</li></ul></li></ul> |
| **Returns**                                          | <ul><li>the browserObject</li></ul> |
| **Notes**                                            | <ul><li>This method returns domains which are visible to your machine; however, your machine may or may not be able to access or publish records within the returned domains. See  <a href="#findRegistrationDomains">hs.bonjour:findRegistrationDomains</a></li></ul> |

#### [findRegistrationDomains](#findregistrationdomains)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.bonjour:findRegistrationDomains(callback) -> browserObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Return a list of zero-conf and bonjour domains this computer can register services in. |
| **Parameters**                                       | <ul><li><code>callback</code> - a function which will be invoked as domains are discovered. The function should accept the following parameters and return none:</li><li><code>browserObject</code>    - the userdata object for the browserObject which initiated the search</li><li><code>type</code>             - a string which will be 'domain' or 'error'<ul><li>if <code>type</code> == 'domain', the remaining arguments will be:</li><li><code>added</code>        - a boolean value indicating whether this callback invocation represents a newly discovered or added domain (true) or that the domain has been removed from the network (false)</li><li><code>domain</code>       - a string specifying the name of the domain discovered or removed</li><li><code>moreExpected</code> - a boolean value indicating whether or not the browser expects to discover additional domains or not.</li><li>if <code>type</code> == 'error', the remaining arguments will be:</li><li><code>errorString</code>  - a string specifying the error which has occurred</li></ul></li></ul> |
| **Returns**                                          | <ul><li>the browserObject</li></ul> |
| **Notes**                                            | <ul><li>This is the preferred method for accessing domains as it guarantees that the host machine can connect to services in the returned domains. Access to domains outside this list may be more limited. See also <a href="#findBrowsableDomains">hs.bonjour:findBrowsableDomains</a></li></ul> |

#### [findServices](#findservices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.bonjour:findServices(type, [domain], [callback]) -> browserObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Find advertised services of the type specified. |
| **Parameters**                                       | <ul><li><code>type</code>     - a string specifying the type of service to discover on your network. This string should be specified in the format of '_service._protocol.' where _protocol is one of '_tcp' or '_udp'. Examples of common service types can be found in <a href="#serviceTypes">hs.bonjour.serviceTypes</a>.</li><li><code>domain</code>   - an optional string specifying the domain to look for advertised services in. The domain should end with a period. If you omit this parameter, the default registration domain will be used, usually "local."</li><li><code>callback</code> - a callback function which will be invoked as service advertisements meeting the specified criteria are discovered. The callback function should expect 2-5 arguments as follows:</li><li>if a service is discovered or advertising for the service is terminated, the arguments will be:<ul><li>the browserObject</li><li>the string "domain"</li><li>a boolean indicating whether the service is being advertised (true) or should be removed because advertisments for the service are being terminated (false)</li><li>the serviceObject for the specific advertisement (see <code>hs.bonjour.service</code>)</li><li>a boolean indicating if more advertisements are expected (true) or if the macOS believes that there are no more advertisements to be discovered (false).</li></ul></li><li>if an error occurs, the callback arguments will be:<ul><li>the browserObject</li><li>the string "error"</li><li>a string specifying the specific error that occurred</li></ul></li></ul> |
| **Returns**                                          | <ul><li>the browserObject</li></ul> |
| **Notes**                                            | <ul><li>macOS will indicate when it believes there are no more advertisements of the type specified by <code>type</code> in <code>domain</code> by marking the last argument to your callback function as false. This is a best guess and may not always be accurate if your network is slow or some servers on your network are particularly slow to respond.</li><li>In addition, if you leave the browser running this method, you will get future updates when services are removed because of server shutdowns or added because of new servers being booted up.</li><li>Leaving the browser running does consume some system resources though, so you will have to determine, based upon your specific requirements, if this is a concern for your specific task or not. To terminate the browser when you have rtrieved all of the infomration you reuqire, you can use the <a href="#stop">hs.bonjour:stop</a> method.</li></ul> |

#### [includesPeerToPeer](#includespeertopeer)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.bonjour:includesPeerToPeer([value]) -> current value | browserObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Get or set whether to also browse over peer-to-peer Bluetooth and Wi-Fi, if available. |
| **Parameters**                                       | <ul><li><code>value</code> - an optional boolean, default false, value specifying whether to also browse over peer-to-peer Bluetooth and Wi-Fi, if available.</li></ul> |
| **Returns**                                          | <ul><li>if <code>value</code> is provided, returns the browserObject; otherwise returns the current value for this property</li></ul> |
| **Notes**                                            | <ul><li>This property must be set before initiating a search to have an effect.</li></ul> |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.bonjour:stop() -> browserObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Stops a currently running search or resolution for the browser object |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the browserObject</li></ul> |
| **Notes**                                            | <ul><li>This method should be invoked when you have identified the services or hosts you require to reduce the consumption of system resources.</li><li>Invoking this method on an already idle browser will do nothing</li></ul> |

