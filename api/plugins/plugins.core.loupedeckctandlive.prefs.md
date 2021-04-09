# [docs](index.md) » plugins.core.loupedeckctandlive.prefs
---

Loupedeck CT & Loupedeck Live Preferences Panels

## API Overview
* Variables - Configurable values
 * [defaultIconPath](#defaulticonpath)
 * [supportedExtensions](#supportedextensions)
* Functions - API calls offered directly by the extension
 * [updateUI](#updateui)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [generateContent](#generatecontent)
 * [generateKnobImages](#generateknobimages)
 * [panelCallback](#panelcallback)
 * [renderPanel](#renderpanel)
 * [setItem](#setitem)

## API Documentation

### Variables

#### [defaultIconPath](#defaulticonpath)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.loupedeckctandlive.prefs.defaultIconPath -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Default Path where built-in icons are stored |

#### [supportedExtensions](#supportedextensions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.loupedeckctandlive.prefs.supportedExtensions -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable |
| **Description**                                      | Table of supported extensions for Icons. |

### Functions

#### [updateUI](#updateui)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.loupedeckctandlive.prefs:updateUI([params]) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Update the Preferences Panel UI. |
| **Parameters**                                       | <ul><li>params - A optional table of parameters</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.loupedeckctandlive.prefs.new() -> Loupedeck` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new Loupedeck Preferences panel. |
| **Parameters**                                       | <ul><li>deviceType - The device type defined in <code>hs.loupedeck.deviceTypes</code></li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |
| **Notes**                                            | <ul><li>The deviceType should be either <code>hs.loupedeck.deviceTypes.LIVE</code>   or <code>hs.loupedeck.deviceTypes.CT</code>.</li></ul> |

### Methods

#### [generateContent](#generatecontent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.loupedeckctandlive.prefs:generateContent() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Generates the Preference Panel HTML Content. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>HTML content as string</li></ul> |

#### [generateKnobImages](#generateknobimages)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.loupedeckctandlive.prefs:generateKnobImages(app, bank, id) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Generates a combined image for all the knobs. |
| **Parameters**                                       | <ul><li>app - The application bundle ID</li><li>bank - The bank as a string</li><li>id - The ID</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [panelCallback](#panelcallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.loupedeckctandlive.prefs:panelCallback() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | JavaScript Callback for the Preferences Panel |
| **Parameters**                                       | <ul><li>id - ID as string</li><li>params - Table of paramaters</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [renderPanel](#renderpanel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.loupedeckctandlive.prefs:renderPanel(context) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Generates the Preference Panel HTML Content. |
| **Parameters**                                       | <ul><li>context - Table of data that you want to share with the renderer</li></ul> |
| **Returns**                                          | <ul><li>HTML content as string</li></ul> |

#### [setItem](#setitem)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.core.loupedeckctandlive.prefs:setItem(app, bank, controlType, id, valueA, valueB) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Update the Loupedeck CT layout file. |
| **Parameters**                                       | <ul><li>app - The application bundle ID as a string</li><li>bank - The bank ID as a string</li><li>controlType - The control type as a string</li><li>id - The ID of the item as a string</li><li>valueA - The value of the item as a string</li><li>valueB - An optional value</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

