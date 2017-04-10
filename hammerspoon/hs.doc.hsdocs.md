# [docs](index.md) » hs.doc.hsdocs
---

Manage the internal documentation web server.

This module provides functions for managing the Hammerspoon built-in documentation web server.  Currently, this is the same documentation available in the Dash docset for Hammerspoon, but does not require third party software for viewing.

Future enhancements to this module under consideration include:
 * Support for third-party modules to add to the documentation set at run-time
 * Markdown/HTML based tutorials and How-To examples
 * Documentation for the LuaSkin Objective-C Framework
 * Lua Reference documentation

The intent of this sub-module is to provide as close a rendering of the same documentation available at the Hammerspoon Github site and Dash documentation as possible in a manner suitable for run-time modification so module developers can test out documentation additions without requiring a complete recompilation of the Hammerspoon source.  As always, the most current and official documentation can be found at http://www.hammerspoon.org and in the official Hammerspoon Dash docset.

## API Overview
* Functions - API calls offered directly by the extension
 * [browserDarkMode](#browserDarkMode)
 * [browserFrame](#browserFrame)
 * [forceExternalBrowser](#forceExternalBrowser)
 * [help](#help)
 * [interface](#interface)
 * [port](#port)
 * [start](#start)
 * [stop](#stop)
 * [trackBrowserFrame](#trackBrowserFrame)

## API Documentation
### Functions

#### [browserDarkMode](#browserDarkMode)
|             |                 |
| ------------|-----------------|
| Signature   | hs.doc.hsdocs.browserDarkMode([value]) -> currentValue  |
| Type        | Function |
| Description | Get or set whether or not the Hammerspoon browser renders output in Dark mode. |
| Returns |  * the current, possibly new, value |
| Notes |  * Inversion is applied through the use of CSS filtering, so while numeric values other than 0 (false) and 100 (true) are allowed, the result is generally not what is desired.

#### [browserFrame](#browserFrame)
|             |                 |
| ------------|-----------------|
| Signature   | hs.doc.hsdocs.browserFrame([frameTable]) -> currentValue  |
| Type        | Function |
| Description | Get or set the currently saved initial frame location for the documentation browser. |
| Parameters |  * frameTable - a frame table containing x, y, h, and w values specifying the browser's initial position when Hammerspoon starts. |
| Returns |  * the current, possibly new, value |
| Notes |  * If [hs.doc.hsdocs.trackBrowserFrame](#trackBrowserFrame) is false or nil (the default), then you can use this function to specify the initial position of the documentation browser. * If [hs.doc.hsdocs.trackBrowserFrame](#trackBrowserFrame) is true, then this any value set with this function will be overwritten whenever the browser window is moved or resized.

#### [forceExternalBrowser](#forceExternalBrowser)
|             |                 |
| ------------|-----------------|
| Signature   | hs.doc.hsdocs.forceExternalBrowser([value]) -> currentValue  |
| Type        | Function |
| Description | Get or set whether or not [hs.doc.hsdocs.help](#help) uses an external browser. |
| Returns |  * the current, possibly new, value |
| Notes |  * If this value is set to true, help requests invoked by [hs.doc.hsdocs.help](#help) will be invoked by your system's default handler for the `http` scheme. * If this value is set to a string, the string specifies the bundle ID of an application which will be used to handle the url request for the documentation.  The string should match one of the items returned by `hs.urlevent.getAllHandlersForScheme("http")`.

#### [help](#help)
|             |                 |
| ------------|-----------------|
| Signature   | hs.doc.hsdocs.help([identifier]) -> nil  |
| Type        | Function |
| Description | Display the documentation for the specified Hammerspoon function, or the Table of Contents for the Hammerspoon documentation in a built-in mini browser. |
| Parameters |  * an optional string specifying a Hammerspoon module, function, or method to display documentation for. If you leave out this parameter, the table of contents for the Hammerspoon built-in documentation is displayed instead. |
| Returns |  * None |


#### [interface](#interface)
|             |                 |
| ------------|-----------------|
| Signature   | hs.doc.hsdocs.interface([interface]) -> currentValue  |
| Type        | Function |
| Description | Get or set the network interface that the Hammerspoon documentation web server will be served on |
| Returns |  * the current, possibly new, value |
| Notes |  * See `hs.httpserver.setInterface` for a description of valid values that can be specified as the `interface` argument to this function. * A change to the interface can only occur when the documentation server is not running. If the server is currently active when you call this function with an argument, the server will be temporarily stopped and then restarted after the interface has been changed.

#### [port](#port)
|             |                 |
| ------------|-----------------|
| Signature   | hs.doc.hsdocs.port([value]) -> currentValue  |
| Type        | Function |
| Description | Get or set the Hammerspoon documentation server HTTP port. |
| Returns |  * the current, possibly new, value |
| Notes |  * The default port number is 12345.

#### [start](#start)
|             |                 |
| ------------|-----------------|
| Signature   | hs.doc.hsdocs.start() -> `hs.doc.hsdocs`  |
| Type        | Function |
| Description | Start the Hammerspoon internal documentation web server. |
| Parameters |  * None |
| Returns |  * the table representing the `hs.doc.hsdocs` module |
| Notes |  * This function is automatically called, if necessary, when [hs.doc.hsdocs.help](#help) is invoked. * The documentation web server can be viewed from a web browser by visiting "http://localhost:port" where `port` is the port the server is running on, 12345 by default -- see [hs.doc.hsdocs.port](#port).

#### [stop](#stop)
|             |                 |
| ------------|-----------------|
| Signature   | hs.doc.hsdocs.stop() -> `hs.doc.hsdocs`  |
| Type        | Function |
| Description | Stop the Hammerspoon internal documentation web server. |
| Parameters |  * None |
| Returns |  * the table representing the `hs.doc.hsdocs` module |


#### [trackBrowserFrame](#trackBrowserFrame)
|             |                 |
| ------------|-----------------|
| Signature   | hs.doc.hsdocs.trackBrowserFrame([value]) -> currentValue  |
| Type        | Function |
| Description | Get or set whether or not changes in the documentation browsers location and size persist through launches of Hammerspoon. |
| Parameters |  * value - an optional boolean specifying whether or not the browsers location should be saved across launches of Hammerspoon. |
| Returns |  * the current, possibly new, value |
| Notes |  * Changes made with this function are saved with `hs.settings` with the label "_documentationServer.trackBrowserFrameChanges" and will persist through a reload or restart of Hammerspoon. |
