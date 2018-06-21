# [docs](index.md) » cp.plugins.env
---

Provides access to resources in the plugin environment. In generally, this will be files stored in a Complex Plugin's folder.

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [compileTemplate](#compiletemplate)
 * [pathToAbsolute](#pathtoabsolute)
 * [pathToURL](#pathtourl)
 * [readResource](#readresource)
 * [renderTemplate](#rendertemplate)

## API Documentation

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plugins.env.new(rootPath) -> cp.plugins.env` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new `env` pointing at the specified root folder path.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* `rootPath` the path to the plugin's root folder.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The new `env` instance.</li></ul>          |

### Methods

#### [compileTemplate](#compiletemplate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plugins.env:compileTemplate(view[, layout]) -> function` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Compiles a Resty Template within the context of the plugin. The `view` may be a resource path pointing at a template file in the plugin, or may be raw template markup. The `layout` is an optional path/template for a layout template. See the [Resty Template](https://github.com/bungle/lua-resty-template) documentation for details.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* `view`	- The local path inside the plugin to the template file, or raw template markup.</li><li markdown="1">* `layout`	- The local path inside the plugin to the layout file.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* A function which will render the template.</li></ul>          |

#### [pathToAbsolute](#pathtoabsolute)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plugins.env:pathToAbsolute(resourcePath) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the absolute path to the file referred to by the relative resource path. If an image is stored as `images/my.jpg` in the plugin, the resource path will be `"images/my.jpg"`. The result will be the full path to that file. If the file cannot be found in the plugin, it will look in the `cp/resources/assets` folder for globally-shared resources.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* `resourcePath`	- The local path to the resource inside the plugin.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The absolute path to the resource, or `nil` if it does not exist.</li></ul>          |

#### [pathToURL](#pathtourl)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plugins.env:pathToURL(resourcePath) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns an absolute `file://` URL to the file referred to by the relative resource path. If an image is stored as `images/my.jpg` in the plugin, the resource path will be `"images/my.jpg"`. The result will be a URL to that file. If the file cannot be found in the plugin, it will look in the `cp/resources/assets` folder for globally-shared resources.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* `resourcePath`	- The local path to the resource inside the plugin.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The absolute URL to the resource, or `nil` if it does not exist.</li></ul>          |

#### [readResource](#readresource)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plugins.env:readResource(resourcePath) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Reads the contents of the resource at the specified resource path. This is returned as a string of data (which may or may not be an actual readable string, depending on the source content).                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* `resourcePath`	- The local path to the resource inside the plugin.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* The contents of the resouce, or `nil` if the file does not exist.</li></ul>          |

#### [renderTemplate](#rendertemplate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.plugins.env:renderTemplate(view[, model[, layout]]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Renders a Resty Template within the context of the plugin. The `view` may be a resource path pointing at a template file in the plugin, or may be raw template markup. The `layout` is an optional path/template for a layout template. See the [Resty Template](https://github.com/bungle/lua-resty-template) documentation for details.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">* `view`	- The local path inside the plugin to the template file, or raw template markup.</li><li markdown="1">* `model`	- The model which provides variables/functions/etc to the template.</li><li markdown="1">* `layout`	- The local path inside the plugin to the layout file.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">* A function which will render the template.</li></ul>          |

