# [docs](/hammerspoon/index.html) » hs.webview
---

Display web content in a window from Hammerspoon

This module uses Apple's WebKit WKWebView class to provide web content display with JavaScript injection support.  The objective is to provide a functional interface to the WKWebView and WKUserContentController classes.

This module is not intended to replace a full web browser and does have some limitations to keep in mind:
  * Self-signed SSL certificates are not accepted unless they have first been approved and included in the users Keychain by another method, for example, opening the page first in Safari.
  * The context-menu (right clicking or ctrl-clicking in the webview) provides some menu items which are currently unsupported -- a known example of this is any "Download..." menu item in the context menu for links and images.
  * It is uncertain at present exactly how or where cookies and cached page data is stored or how it can be invalidated.
    * This can be mitigated to an extent for web requests by using `hs.webview:reload(true)` and by crafting the url for `hs.webview:url({...})` as a table -- see the appropriate help entries for more information.

Any suggestions or updates to the code to address any of these or other limitations as they may become apparent are welcome at the Hammerspoon github site: https://www.github.com/Hammerspoon/hammerspoon


## Submodules
 * [hs.webview.datastore](hs.webview.datastore.md)
 * [hs.webview.toolbar](hs.webview.toolbar.md)
 * [hs.webview.usercontent](hs.webview.usercontent.md)

## API Overview
* Deprecateds - API features which will be removed in an future release
 * [asHSDrawing](#asHSDrawing)
 * [asHSWindow](#asHSWindow)
 * [setLevel](#setLevel)
* Constants - Useful values which cannot be changed
 * [certificateOIDs[]](#certificateOIDs[])
 * [windowMasks[]](#windowMasks[])
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
 * [newBrowser](#newBrowser)
* Methods - API calls which can only be made on an object returned by a constructor
 * [allowGestures](#allowGestures)
 * [allowMagnificationGestures](#allowMagnificationGestures)
 * [allowNavigationGestures](#allowNavigationGestures)
 * [allowNewWindows](#allowNewWindows)
 * [allowTextEntry](#allowTextEntry)
 * [alpha](#alpha)
 * [behavior](#behavior)
 * [behaviorAsLabels](#behaviorAsLabels)
 * [bringToFront](#bringToFront)
 * [certificateChain](#certificateChain)
 * [children](#children)
 * [closeOnEscape](#closeOnEscape)
 * [delete](#delete)
 * [deleteOnClose](#deleteOnClose)
 * [estimatedProgress](#estimatedProgress)
 * [evaluateJavaScript](#evaluateJavaScript)
 * [examineInvalidCertificates](#examineInvalidCertificates)
 * [goBack](#goBack)
 * [goForward](#goForward)
 * [hide](#hide)
 * [historyList](#historyList)
 * [hswindow](#hswindow)
 * [html](#html)
 * [isOnlySecureContent](#isOnlySecureContent)
 * [level](#level)
 * [loading](#loading)
 * [magnification](#magnification)
 * [navigationCallback](#navigationCallback)
 * [navigationID](#navigationID)
 * [orderAbove](#orderAbove)
 * [orderBelow](#orderBelow)
 * [parent](#parent)
 * [policyCallback](#policyCallback)
 * [privateBrowsing](#privateBrowsing)
 * [reload](#reload)
 * [sendToBack](#sendToBack)
 * [shadow](#shadow)
 * [show](#show)
 * [sslCallback](#sslCallback)
 * [stopLoading](#stopLoading)
 * [title](#title)
 * [toolbar](#toolbar)
 * [transparent](#transparent)
 * [url](#url)
 * [urlParts](#urlParts)
 * [userAgent](#userAgent)
 * [windowStyle](#windowStyle)
 * [windowTitle](#windowTitle)

## API Documentation

### Deprecateds

| [asHSDrawing](#asHSDrawing)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:asHSDrawing() -> hs.drawing object`                                                                    |
| **Type**                                    | Deprecated                                                                     |
| **Description**                             | Because use of this method can easily lead to a crash, useful methods from `hs.drawing` have been added to the `hs.webview` module itself.  If you believe that a useful method has been overlooked, please submit an issue.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>a placeholder object</li></ul>          |

| [asHSWindow](#asHSWindow)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:asHSWindow() -> hs.window object`                                                                    |
| **Type**                                    | Deprecated                                                                     |
| **Description**                             | Returns an hs.window object for the webview so that you can use hs.window methods on it.                                                                     |

| [setLevel](#setLevel)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:setLevel(theLevel) -> drawingObject`                                                                    |
| **Type**                                    | Deprecated                                                                     |
| **Description**                             | Deprecated; you should use [hs.webview:level](#level) instead.                                                                     |
| **Parameters**                              | <ul><li>`theLevel` - the level specified as a number, which can be obtained from `hs.drawing.windowLevels`.</li></ul> |
| **Returns**                                 | <ul><li>the webview object</li></ul>          |
| **Notes**                                   | <ul><li>see the notes for `hs.drawing.windowLevels`</li></ul>                |

### Constants

| [certificateOIDs[]](#certificateOIDs[])         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview.certificateOIDs[]`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | A table of common OID values found in SSL certificates.  SSL certificates provided to the callback function for [hs.webview:sslCallback](#sslCallback) or in the results of [hs.webview:certificateChain](#certificateChain) use OID strings as the keys which describe the properties of the certificate and this table can be used to get a more common name for the keys you are most likely to see.                                                                     |

| [windowMasks[]](#windowMasks[])         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview.windowMasks[]`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | A table containing valid masks for the webview window.                                                                     |
| **Notes**                                   | <ul><li>The Maximize button in the window title is enabled when Resizable is set.</li><li>The Close, Minimize, and Maximize buttons are only visible when the Window is also Titled.</li></ul>                |

### Constructors

| [new](#new)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview.new(rect, [preferencesTable], [userContentController]) -> webviewObject`                                                                    |
| **Type**                                    | Constructor                                                                     |
| **Description**                             | Create a webviewObject and optionally modify its preferences.                                                                     |
| **Parameters**                              | <ul><li>`rect` - a rectangle specifying where the webviewObject should be displayed.</li><li>`preferencesTable` - an optional table which can include one of more of the following keys:</li><li> `javaEnabled`                           - java is enabled (default false)</li><li> `javaScriptEnabled`                     - JavaScript is enabled (default true)</li><li> `javaScriptCanOpenWindowsAutomatically` - can JavaScript open windows without user intervention (default true)</li><li> `minimumFontSize`                       - minimum font size (default 0.0)</li><li> `plugInsEnabled`                        - plug-ins are enabled (default false)</li><li> `developerExtrasEnabled`                - include "Inspect Element" in the context menu</li><li> `suppressesIncrementalRendering`        - suppresses content rendering until fully loaded into memory (default false)</li></ul> |
| **Returns**                                 | <ul><li>The webview object</li></ul>          |
| **Notes**                                   | <ul><li>To set the initial URL, use the `hs.webview:url` method before showing the webview object.</li><li>Preferences can only be set when the webview object is created.  To change the preferences of an open webview, you will need to close it and recreate it with this method.</li></ul>                |

| [newBrowser](#newBrowser)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview.newBrowser(rect, [preferencesTable], [userContentController]) -> webviewObject`                                                                    |
| **Type**                                    | Constructor                                                                     |
| **Description**                             | Create a webviewObject with some presets common to an interactive web browser.                                                                     |
| **Parameters**                              | <ul><li>The parameters are the same as for [hs.webview.new](#new) -- check there for more details</li><li>  `rect`                  - a rectangle specifying where the webviewObject should be displayed.</li><li>  `preferencesTable`      - an optional table which specifies special settings for the webview object.</li><li>  `userContentController` - an optional `hs.webview.usercontent` object to provide script injection and JavaScript messaging with Hammerspoon from the webview.</li></ul> |
| **Returns**                                 | <ul><li>The webview object</li></ul>          |
| **Notes**                                   | <ul><li>This constructor is just a short-hand for `hs.webview.new(...):allowTextEntry(true):allowGestures(true):windowStyle(15)`, which specifies a webview with a title bar, title bar buttons (zoom, close, minimize), and allows form entry and gesture support for previous and next pages.</li></ul>                |

### Methods

| [allowGestures](#allowGestures)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:allowGestures([value]) -> webviewObject | current value`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set whether or not the webview will respond to gestures from a trackpad or magic mouse.  Default is false.                                                                     |
| **Parameters**                              | <ul><li>value - an optional boolean value indicating whether or not the webview should respond gestures.</li></ul> |
| **Returns**                                 | <ul><li>If a value is provided, then this method returns the webview object; otherwise the current value</li></ul>          |
| **Notes**                                   | <ul><li>This is a shorthand method for getting or setting both `hs.webview:allowMagnificationGestures` and `hs.webview:allowNavigationGestures`.</li><li>This method will set both types of gestures to true or false, if given an argument, but will only return true if *both* gesture types are currently true; if either or both gesture methods are false, then this method will return false.</li></ul>                |

| [allowMagnificationGestures](#allowMagnificationGestures)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:allowMagnificationGestures([value]) -> webviewObject | current value`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set whether or not the webview will respond to magnification gestures from a trackpad or magic mouse.  Default is false.                                                                     |
| **Parameters**                              | <ul><li>`value` - an optional boolean value indicating whether or not the webview should respond to magnification gestures.</li></ul> |
| **Returns**                                 | <ul><li>If a value is provided, then this method returns the webview object; otherwise the current value</li></ul>          |

| [allowNavigationGestures](#allowNavigationGestures)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:allowNavigationGestures([value]) -> webviewObject | current value`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set whether or not the webview will respond to the navigation gestures from a trackpad or magic mouse.  Default is false.                                                                     |
| **Parameters**                              | <ul><li>`value` - an optional boolean value indicating whether or not the webview should respond to navigation gestures.</li></ul> |
| **Returns**                                 | <ul><li>If a value is provided, then this method returns the webview object; otherwise the current value</li></ul>          |

| [allowNewWindows](#allowNewWindows)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:allowNewWindows([value]) -> webviewObject | current value`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set whether or not the webview allows new windows to be opened from it by any method.  Defaults to true.                                                                     |
| **Parameters**                              | <ul><li>`value` - an optional boolean value indicating whether or not the webview should allow new windows to be opened from it.</li></ul> |
| **Returns**                                 | <ul><li>If a value is provided, then this method returns the webview object; otherwise the current value</li></ul>          |
| **Notes**                                   | <ul><li>This method allows you to prevent a webview from being able to open a new window by any method.   This includes right-clicking on a link and selecting "Open in a New Window", JavaScript pop-ups, links with the target of "__blank", etc.</li><li>If you just want to prevent automatic JavaScript windows, set the preference value javaScriptCanOpenWindowsAutomatically to false when creating the web view - this method blocks *all* methods.</li></ul>                |

| [allowTextEntry](#allowTextEntry)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:allowTextEntry([value]) -> webviewObject | current value`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set whether or not the webview can accept keyboard for web form entry. Defaults to false.                                                                     |
| **Parameters**                              | <ul><li>`value` - an optional boolean value which sets whether or not the webview will accept keyboard input.</li></ul> |
| **Returns**                                 | <ul><li>If a value is provided, then this method returns the webview object; otherwise the current value</li></ul>          |

| [alpha](#alpha)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:alpha([alpha]) -> webviewObject | currentValue`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set the alpha level of the window containing the hs.webview object.                                                                     |
| **Parameters**                              | <ul><li>`alpha` - an optional number between 0.0 and 1.0 specifying the new alpha level for the webview.</li></ul> |
| **Returns**                                 | <ul><li>If a parameter is provided, returns the webview object; otherwise returns the current value.</li></ul>          |

| [behavior](#behavior)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:behavior([behavior]) -> webviewObject | currentValue`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set the window behavior settings for the webview object.                                                                     |
| **Parameters**                              | <ul><li>`behavior` - an optional number representing the desired window behaviors for the webview object.</li></ul> |
| **Returns**                                 | <ul><li>If an argument is provided, the webview object; otherwise the current value.</li></ul>          |
| **Notes**                                   | <ul><li>Window behaviors determine how the webview object is handled by Spaces and Exposé. See `hs.drawing.windowBehaviors` for more information.</li></ul>                |

| [behaviorAsLabels](#behaviorAsLabels)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:behaviorAsLabels(behaviorTable) -> webviewObject | currentValue`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set the window behavior settings for the webview object using labels defined in `hs.drawing.windowBehaviors`.                                                                     |
| **Parameters**                              | <ul><li>behaviorTable - an optional table of strings and/or numbers specifying the desired window behavior for the webview object.</li></ul> |
| **Returns**                                 | <ul><li>If an argument is provided, the webview object; otherwise the current value.</li></ul>          |
| **Notes**                                   | <ul><li>Window behaviors determine how the webview object is handled by Spaces and Exposé. See `hs.drawing.windowBehaviors` for more information.</li></ul>                |

| [bringToFront](#bringToFront)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:bringToFront([aboveEverything]) -> webviewObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Places the drawing object on top of normal windows                                                                     |
| **Parameters**                              | <ul><li>`aboveEverything` - An optional boolean value that controls how far to the front the webview should be placed. True to place the webview on top of all windows (including the dock and menubar and fullscreen windows), false to place the webview above normal windows, but below the dock, menubar and fullscreen windows. Defaults to false.</li></ul> |
| **Returns**                                 | <ul><li>The webview object</li></ul>          |

| [certificateChain](#certificateChain)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:certificateChain() -> table | nil`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns the certificate chain for the most recently committed navigation of the webview.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>a table containing the certificates that make up the SSL certificate chain securing the most recent committed navigation.  Each certificate is described in a table with the following keys:</li><li>  `commonName` - the common name for the certificate; most commonly this will be a string matching the server portion of the URL request or other descriptor of the certificate's purpose.</li><li>  `values`     - a table containing key-value pairs describing the certificate.  The keys will be certificate OIDs.  Common OIDs and their meaning can be found in [hs.webview.certificateOIDs](#certificateOIDs). The value for each key will be a table with the following keys:</li><li>    `label`           - a description or label for the entry</li><li>    `localized label` - a localized version of `label`</li><li>    `type`            - a description of the data type for this value</li><li>    `value`           - the value</li></ul>          |
| **Notes**                                   | <ul><li>This method is only supported by OS X 10.11 and newer</li><li>A navigation which was performed via HTTP instead of HTTPS will return an empty array.</li></ul>                |

| [children](#children)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:children() -> array`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns an array of webview objects which have been opened as children of this webview.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>an array containing the webview objects of all child windows opened from this webview.</li></ul>          |

| [closeOnEscape](#closeOnEscape)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:closeOnEscape([flag]) -> webviewObject | current value`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | If the webview is closable, this will get or set whether or not the Escape key is allowed to close the webview window.                                                                     |
| **Parameters**                              | <ul><li>`flag` - an optional boolean value which indicates whether a webview, when it's style includes Closable (see `hs.webview:windowStyle`), should allow the Escape key to be a shortcut for closing the webview window.  Defaults to false.</li></ul> |
| **Returns**                                 | <ul><li>If a value is provided, then this method returns the webview object; otherwise the current value</li></ul>          |
| **Notes**                                   | <ul><li>If this is set to true, Escape will only close the window if no other element responds to the Escape key first (e.g. if you are editing a text input field, the Escape will be captured by the text field, not by the webview Window.)</li></ul>                |

| [delete](#delete)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:delete([propagate], [fadeOutTime]) -> none`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Destroys the webview object, optionally fading it out first (if currently visible).                                                                     |
| **Parameters**                              | <ul><li>`propagate`   - an optional boolean, default false, which indicates whether or not the child windows of this webview should also be deleted.</li><li>`fadeOutTime` - an optional number of seconds over which to fade out the webview object. Defaults to zero.</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul><li>This method is automatically called during garbage collection, notably during a Hammerspoon termination or reload, with a fade time of 0.</li></ul>                |

| [deleteOnClose](#deleteOnClose)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:deleteOnClose([value]) -> webviewObject | current value`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set whether or not the webview should delete itself when its window is closed.                                                                     |
| **Parameters**                              | <ul><li>`value` - an optional boolean value which sets whether or not the webview will delete itself when its window is closed by any method.  Defaults to false for a window created with `hs.webview.new` and true for any webview windows created by the main webview (user selects "Open Link in New Window", etc.)</li></ul> |
| **Returns**                                 | <ul><li>If a value is provided, then this method returns the webview object; otherwise the current value</li></ul>          |
| **Notes**                                   | <ul><li>If set to true, a webview object will be deleted when the user clicks on the close button of a titled and closable webview (see `hs.webview.windowStyle`).</li><li>Children of an explicitly created webview automatically have this attribute set to true.  To cause closed children to remain after the user closes the parent, you can set this to false with a policy callback function when it receives the "newWindow" action.</li></ul>                |

| [estimatedProgress](#estimatedProgress)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:estimatedProgress() -> number`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns the estimated percentage of expected content that has been loaded.  Will equal 1.0 when all content has been loaded.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>a numerical value between 0.0 and 1.0 indicating the percentage of expected content which has been loaded.</li></ul>          |

| [evaluateJavaScript](#evaluateJavaScript)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:evaluateJavaScript(script, [callback]) -> webviewObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Execute JavaScript within the context of the current webview and optionally receive its result or error in a callback function.                                                                     |
| **Parameters**                              | <ul><li>`script` - the JavaScript to execute within the context of the current webview's display</li><li>`callback` - an optional function which should accept two parameters as the result of the executed JavaScript.  The function paramaters are as follows:</li><li>  `result` - the result of the executed JavaScript code or nil if there was no result or an error occurred.</li><li>  `error`  - an NSError table describing any error that occurred during the JavaScript execution or nil if no error occurred.</li></ul> |
| **Returns**                                 | <ul><li>the webview object</li></ul>          |

| [examineInvalidCertificates](#examineInvalidCertificates)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:examineInvalidCertificates([flag]) -> webviewObject | current value`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set whether or not invalid SSL server certificates that are approved by the ssl callback function are accepted as valid for browsing with the webview.                                                                     |
| **Parameters**                              | <ul><li>* `flag` - an optional boolean, default false, specifying whether or not an invalid SSL server certificate should be  accepted if it is approved by the ssl callback function.</li></ul> |
| **Returns**                                 | <ul><li>If a value is provided, then this method returns the webview object; otherwise the current value</li></ul>          |
| **Notes**                                   | <ul><li>In order for this setting to have any effect, you must also register an ssl callback function with [hs.webview:sslCallback](#sslCallback) which should return true if the certificate should be granted an exception or false if it should not.  For a certificate to be granted an exception, both this method and the result of the callback *must* be true.</li></ul>                |

| [goBack](#goBack)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:goBack() -> webviewObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Move to the previous page in the webview's history, if possible.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The webview Object</li></ul>          |

| [goForward](#goForward)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:goForward() -> webviewObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Move to the next page in the webview's history, if possible.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The webview Object</li></ul>          |

| [hide](#hide)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:hide([fadeOutTime]) -> webviewObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Hides the webview object                                                                     |
| **Parameters**                              | <ul><li>`fadeOutTime` - An optional number of seconds over which to fade out the webview. Defaults to zero</li></ul> |
| **Returns**                                 | <ul><li>The webview object</li></ul>          |

| [historyList](#historyList)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:historyList() -> historyTable`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns the URL history for the current webview as an array.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A table which is an array of the URLs viewed within this webview and a key named `current` which is equal to the index corresponding to the currently visible entry.  Each array element will be a table with the following keys:</li><li>  `URL`        - the URL of the web page</li><li>  `initialURL` - the URL of the initial request that led to this item</li><li>  `title`      - the web page title</li></ul>          |

| [hswindow](#hswindow)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:hswindow() -> hs.window object`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns an hs.window object for the webview so that you can use hs.window methods on it.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>an hs.window object</li></ul>          |
| **Notes**                                   | <ul><li>hs.window:minimize only works if the webview is minimizable (see `hs.webview.windowStyle`)</li><li>hs.window:setSize only works if the webview is resizable (see `hs.webview.windowStyle`)</li><li>hs.window:close only works if the webview is closable (see `hs.webview.windowStyle`)</li><li>hs.window:maximize will reposition the webview to the upper left corner of your screen, but will only resize the webview if the webview is resizable (see `hs.webview.windowStyle`)</li></ul>                |

| [html](#html)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:html(html,[baseURL]) -> webviewObject, navigationIdentifier`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Render the given HTML in the webview with an optional base URL for relative links.                                                                     |
| **Parameters**                              | <ul><li>`html`    - the html to be rendered in the webview</li><li>`baseURL` - an optional Base URL to use as the starting point for any relative links within the provided html.</li></ul> |
| **Returns**                                 | <ul><li>The webview Object</li></ul>          |
| **Notes**                                   | <ul><li>Web Pages generated in this manner are not added to the webview history list</li></ul>                |

| [isOnlySecureContent](#isOnlySecureContent)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:isOnlySecureContent() -> bool`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns a boolean value indicating if all content current displayed in the webview was loaded over securely encrypted connections.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>true if all content current displayed in the web view was loaded over securely encrypted connections; otherwise false.</li></ul>          |

| [level](#level)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:level([theLevel]) -> drawingObject | currentValue`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set the window level                                                                     |
| **Parameters**                              | <ul><li>`theLevel` - an optional parameter specifying the desired level as an integer, which can be obtained from `hs.drawing.windowLevels`.</li></ul> |
| **Returns**                                 | <ul><li>if a parameter is specified, returns the webview object, otherwise the current value</li></ul>          |
| **Notes**                                   | <ul><li>see the notes for `hs.drawing.windowLevels`</li></ul>                |

| [loading](#loading)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:loading() -> boolean`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns a boolean value indicating whether or not the vebview is still loading content.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>true if the content is still being loaded, or false if it has completed.</li></ul>          |

| [magnification](#magnification)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:magnification([value]) -> webviewObject | current value`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set the webviews current magnification level. Default is 1.0.                                                                     |
| **Parameters**                              | <ul><li>`value` - an optional number specifying the webviews magnification level.</li></ul> |
| **Returns**                                 | <ul><li>If a value is provided, then this method returns the webview object; otherwise the current value</li></ul>          |

| [navigationCallback](#navigationCallback)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:navigationCallback(fn) -> webviewObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Sets a callback for tracking a webview's navigation process.                                                                     |
| **Parameters**                              | <ul><li>`fn` - the function to be called when the navigation status of a webview cahnges.  To disable the callback function, explicitly specify nil.  The function should expect 3 or 4 arguments and may optionally return 1.  The function arguments are defined as follows:</li><li>  `action`  - a string indicating the webview's current status.  It will be one of the following:</li><li>    `didStartProvisionalNavigation`                    - a request or action to change the contents of the main frame has occurred</li><li>    `didReceiveServerRedirectForProvisionalNavigation` - a server redirect was received for the main frame</li><li>    `didCommitNavigation`                              - content has started arriving for the main frame</li><li>    `didFinishNavigation`                              - the webview's main frame has completed loading.</li><li>    `didFailNavigation`                                - an error has occurred after content started arriving</li><li>    `didFailProvisionalNavigation`                     - an error has occurred as or before content has started arriving</li><li>  `webView` - the webview object the navigation is occurring for.</li><li>  `navID`   - a navigation identifier which can be used to link this event back to a specific request made by a `hs.webview:url`, `hs.webview:html`, or `hs.webview:reload` method.</li><li>  `error`   - a table which will only be provided when `action` is equal to `didFailNavigation` or `didFailProvisionalNavigation`.  If provided, it will contain at leas some of the following keys, possibly others as well:</li><li>    `code`        - a numerical value indicating the type of error code.  This will mostly be of use to developers or in debugging and may be removed in the future.</li><li>    `domain`      - a string indcating the error domain of the error.  This will mostly be of use to developers or in debugging and may be removed in the future.</li><li>    `description` - a string describing the condition or problem that has occurred.</li><li>    `reason`      - if available, more information about what may have caused the problem to occur.</li></ul> |
| **Returns**                                 | <ul><li>The webview object</li></ul>          |
| **Notes**                                   | <ul><li>The return value of the callback function is ignored except when the `action` argument is equal to `didFailNavigation` or `didFailProvisionalNavigation`.  If the return value when the action argument is one of these values is a string, it will be treated as html and displayed in the webview as the error message.  If the return value is the boolean value true, then no change will be made to the webview (it will continue to display the previous web page).  All other return values or no return value at all, if these navigation actions occur, will cause a default error page to be displayed in the webview.</li></ul>                |

| [navigationID](#navigationID)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:navigationID() -> navigationID`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get the most recent navigation identifier for the specified webview.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>the navigation identifier</li></ul>          |
| **Notes**                                   | <ul><li>This navigation identifier can be used to track the progress of a webview with the navigation callback function - see `hs.webview.navigationCallback`.</li></ul>                |

| [orderAbove](#orderAbove)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:orderAbove([webview2]) -> webviewObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Moves webview object above webview2, or all webview objects in the same presentation level, if webview2 is not given.                                                                     |
| **Parameters**                              | <ul><li>`webview2` -An optional webview object to place the webview object above.</li></ul> |
| **Returns**                                 | <ul><li>The webview object</li></ul>          |
| **Notes**                                   | <ul><li>If the webview object and webview2 are not at the same presentation level, this method will will move the webview object as close to the desired relationship without changing the webview object's presentation level. See [hs.webview.level](#level).</li></ul>                |

| [orderBelow](#orderBelow)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:orderBelow([webview2]) -> webviewObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Moves webview object below webview2, or all webview objects in the same presentation level, if webview2 is not given.                                                                     |
| **Parameters**                              | <ul><li>`webview2` -An optional webview object to place the webview object below.</li></ul> |
| **Returns**                                 | <ul><li>The webview object</li></ul>          |
| **Notes**                                   | <ul><li>If the webview object and webview2 are not at the same presentation level, this method will will move the webview object as close to the desired relationship without changing the webview object's presentation level. See [hs.webview.level](#level).</li></ul>                |

| [parent](#parent)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:parent() -> webviewObject | nil`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get the parent webview object for the calling webview object, or nil if the webview has no parent.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>the parent webview object for the calling webview object, or nil if the webview has no parent</li></ul>          |

| [policyCallback](#policyCallback)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:policyCallback(fn) -> webviewObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Sets a callback to approve or deny web navigation activity.                                                                     |
| **Parameters**                              | <ul><li>`fn` - the function to be called to approve or deny web navigation activity.  To disable the callback function, explicitly specify nil.  The callback function will accept three or four arguments and must return 1 argument which will determine if the action is approved or denied.  The first argument will specify the type of policy request and will determine the second and third arguments as follows:</li></ul> |
| **Returns**                                 | <ul><li>The webview object</li></ul>          |
| **Notes**                                   | <ul><li>With the `newWindow` action, the navigationCallback and policyCallback are automatically replicated for the new window from its parent.  If you wish to disable these for the new window or assign a different set of callback functions, you can do so before returning true in the callback function with the webview argument provided.</li></ul>                |

| [privateBrowsing](#privateBrowsing)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:privateBrowsing() -> boolean`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns whether or not the webview browser is set up for private browsing (i.e. uses a non-persistent datastore)                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>a boolean value indicating whether or not the datastore is non-persistent.</li></ul>          |
| **Notes**                                   | <ul><li>This method is only supported by OS X 10.11 and newer</li></ul>                |

| [reload](#reload)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:reload([validate]) -> webviewObject, navigationIdentifier`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Reload the page in the webview, optionally performing end-to-end revalidation using cache-validating conditionals if possible.                                                                     |
| **Parameters**                              | <ul><li>`validate` - an optional boolean indicating whether or not an attempt to perform end-to-end revalidation of cached data should be performed.  Defaults to false.</li></ul> |
| **Returns**                                 | <ul><li>The webview Object</li></ul>          |

| [sendToBack](#sendToBack)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:sendToBack() -> webviewObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Places the webview object behind normal windows, between the desktop wallpaper and desktop icons                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The drawing object</li></ul>          |

| [shadow](#shadow)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:shadow([value]) -> webviewObject | current value`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set whether or not the webview window has shadows. Default to false.                                                                     |
| **Parameters**                              | <ul><li>`value` - an optional boolean value indicating whether or not the webview should have shadows.</li></ul> |
| **Returns**                                 | <ul><li>If a value is provided, then this method returns the webview object; otherwise the current value</li></ul>          |

| [show](#show)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:show([fadeInTime]) -> webviewObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Displays the webview object                                                                     |
| **Parameters**                              | <ul><li>`fadeInTime` - An optional number of seconds over which to fade in the webview. Defaults to zero</li></ul> |
| **Returns**                                 | <ul><li>The webview object</li></ul>          |

| [sslCallback](#sslCallback)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:sslCallback(fn) -> webviewObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Sets a callback to examine an invalid SSL certificate and determine if an exception should be granted.                                                                     |
| **Parameters**                              | <ul><li>`fn` - the function to be called to examine the SSL certificate to determine if an exception should be granted.  To disable the callback function, explicitly specify nil.  The callback function will accept two arguments and must return 1 argument which will determine if the action is approved or denied.  The first argument will be the webview this request originates from.  The second argument will be a table containing the protection space details and may include the following keys:</li></ul> |
| **Returns**                                 | <ul><li>The webview object</li></ul>          |
| **Notes**                                   | <ul><li>even if this callback returns `true`, the certificate will only be granted an exception if [hs.webview:examineInvalidCertificates](#examineInvalidCertificates) has also been set to `true`.</li><li>once an invalid certificate has been granted an exception, the exception will remain in effect until the webview object is deleted.</li><li>the callback is only invoked for invalid certificates -- if a certificate is valid, or once an exception has been granted, the callback will not (no longer) be called for that certificate.</li></ul>                |

| [stopLoading](#stopLoading)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:stopLoading() -> webviewObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Stop loading content if the webview is still loading content.  Does nothing if content has already completed loading.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The webview object</li></ul>          |

| [title](#title)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:title() -> title`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get the title of the page displayed in the webview.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>the title</li></ul>          |

| [toolbar](#toolbar)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:toolbar([toolbar | nil]) -> webviewObject | currentValue`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or attach/detach a toolbar to/from the webview.                                                                     |
| **Parameters**                              | <ul><li>`toolbar` - if an `hs.webview.toolbar` object is specified, it will be attached to the webview.  If an explicit nil is specified, the current toolbar will be removed from the webview.</li></ul> |
| **Returns**                                 | <ul><li>if a toolbarObject or explicit nil is specified, returns the webviewObject; otherwise returns the current toolbarObject or nil, if no toolbar is attached to the webview.</li></ul>          |
| **Notes**                                   | <ul><li>this method is a convenience wrapper for the `hs.webview.toolbar.attachToolbar` function.</li></ul>                |

| [transparent](#transparent)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:transparent([value]) -> webviewObject | current value`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set whether or not the webview background is transparent.  Default is false.                                                                     |
| **Parameters**                              | <ul><li>`value` - an optional boolean value indicating whether or not the webview should be transparent.</li></ul> |
| **Returns**                                 | <ul><li>If a value is provided, then this method returns the webview object; otherwise the current value</li></ul>          |
| **Notes**                                   | <ul><li>When enabled, the webview's background color is equal to the body's `background-color` (transparent by default)</li><li>Setting `background-color:rgba(0, 225, 0, 0.3)` on `<body>` will give a translucent green webview background</li></ul>                |

| [url](#url)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:url([URL]) -> webviewObject, navigationIdentifier | url`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set the URL to render for the webview.                                                                     |
| **Parameters**                              | <ul><li>`URL` - an optional string or table representing the URL to display.  If you provide a table, it should contain one or more of the following keys (note that URL is the only required key):</li><li>  `URL`                     - the URL of the desired content</li><li>  `mainDocumentURL`         - the URL of the main document, if it differs.  This usually only matters for cookie negotiation and currently has no effect in this module.</li><li>  `HTTPBody`                - the message body of the request, as in an HTTP POST request</li><li>  `HTTPMethod`              - the HTTP Method of the request, default GET.</li><li>  `timeoutInterval`         - the timeout interval for the request in seconds, default 60.0.</li><li>  `HTTPShouldHandleCookies` - whether or not cookies should be managed automatically, default true.  Currently there is no support for the manual handling of cookies, though this may change in the future.</li><li>  `HTTPShouldUsePipelining` - whether or not the request can continue to transmit data before receiving a response from the remote server.  Default false.</li><li>  `cachePolicy`             - a string value representing the cache policy for the request.  It should match one of the following:</li><li>    `protocolCachePolicy`     - (default) the cache policy defined as the default for the protocol of the URL request</li><li>    `ignoreLocalCache`        - ignore any locally cached content and request all content from the remote server</li><li>    `returnCacheOrLoad`       - return cached data, regardless of its age or expiration date. If there is no existing data in the cache corresponding to the request, load data from the originating source.</li><li>    `returnCacheDontLoad`     - treat the request as if offline - return cached data, regardless of its age or expiration date. If there is no existing data in the cache corresponding to the request, the load is considered to have failed.</li><li>  `networkServiceType`      - a string value representing the network service type of the request.  It should match one of the following:</li><li>    `default`                 - (default) standard network traffic.  You should rarely use a value other than this as it can affect the responsiveness of your computer and other applications.</li><li>    `VoIP`                    - with the VoIP service type, the kernel continues to listen for incoming traffic while your app is in the background, then wakes up your app whenever new data arrives. This should be used only for connections that are used to communicate with a VoIP service.</li><li>    `video`                   - specifies that this is video traffic</li><li>    `background`              - use this for data if your are performing a download that was not requested by the user — for example, prefetching content so that it will be available when the user chooses to view it.</li><li>    `voice`                   - specifies that this is voice traffic</li><li>  `HTTPHeaderFields`        - a table containing key-value pairs corresponding to additional headers you wish to include in your request.  Because the HTTP specification requires that both keys and values are strings, any key which is not a string is ignored, and any value which is not a string or number is also ignored.  In addition, the following keys are handled automatically behind the scenes and will be ignored if you specify them:</li><li>    `Authorization`</li><li>    `Connection`</li><li>    `Host`</li><li>    `WWW-Authenticate`</li><li>    `Content-Length`</li></ul> |
| **Returns**                                 | <ul><li>If a URL is specified, then this method returns the webview Object; otherwise it returns the current url being displayed.</li></ul>          |
| **Notes**                                   | <ul><li>The networkServiceType field of the URL request table is a hint to the operating system about what the underlying traffic is used for. This hint enhances the system's ability to prioritize traffic, determine how quickly it needs to wake up the Wi-Fi radio, and so on. By providing accurate information, you improve the ability of the system to optimally balance battery life, performance, and other considerations.  Likewise, inaccurate information can have a deleterious effect on your system performance and battery life.</li></ul>                |

| [urlParts](#urlParts)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:urlParts() -> table`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns a table of keys containing the individual components of the URL for the webview.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>a table containing the keys for the webview's URL.  See the function `hs.http.urlParts` for a description of the possible keys returned in the table.</li></ul>          |
| **Notes**                                   | <ul><li>This method is a wrapper to the `hs.http.urlParts` function wich uses the OS X APIs, based on RFC 1808.</li><li>You may also want to consider the `hs.httpserver.hsminweb.urlParts` function for a version more consistent with RFC 3986.</li></ul>                |

| [userAgent](#userAgent)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:userAgent([agent]) -> webviewObject | current value`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set the webview's user agent string                                                                     |
| **Parameters**                              | <ul><li>`agent` - an options string specifying the user agent string to include in all URL requests made by the webview object.</li></ul> |
| **Returns**                                 | <ul><li>if a parameter is specified, returns the webviewObject, otherwise returns the current value</li></ul>          |
| **Notes**                                   | <ul><li>This method is only supported by OS X 10.11 and newer</li></ul>                |

| [windowStyle](#windowStyle)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:windowStyle(mask) -> webviewObject | currentMask`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set the window display style                                                                     |
| **Parameters**                              | <ul><li>mask - if present, this mask should be a combination of values found in `hs.webview.windowMasks` describing the window style.  The mask should be provided as one of the following:</li><li>  integer - a number representing the style which can be created by combining values found in `hs.webview.windowMasks` with the logical or operator.</li><li>  string  - a single key from `hs.webview.windowMasks` which will be toggled in the current window style.</li><li>  table   - a list of keys from `hs.webview.windowMasks` which will be combined to make the final style by combining their values with the logical or operator.</li></ul> |
| **Returns**                                 | <ul><li>if a mask is provided, then the webviewObject is returned; otherwise the current mask value is returned.</li></ul>          |

| [windowTitle](#windowTitle)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:windowTitle([title]) -> webviewObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Sets the title for the webview window.                                                                     |
| **Parameters**                              | <ul><li>`title` - if specified and not nil, the title to set for the webview window.  If this parameter is not present or is nil, the title will follow the title of the webview's content.</li></ul> |
| **Returns**                                 | <ul><li>The webview Object</li></ul>          |
| **Notes**                                   | <ul><li>The title will be hidden unless the window style includes the "titled" style (see `hs.webview.windowStyle` and `hs.webview.windowMasks`)</li></ul>                |

