# [docs](index.md) » hs.dialog
---

A collection of useful dialog boxes, alerts and panels for user interaction.

## Submodules
 * [hs.dialog.color](hs.dialog.color.md)

## API Overview
* Functions - API calls offered directly by the extension
 * [alert](#alert)
 * [blockAlert](#blockalert)
 * [chooseFileOrFolder](#choosefileorfolder)
 * [textPrompt](#textprompt)
 * [webviewAlert](#webviewalert)

## API Documentation

### Functions

#### [alert](#alert)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.dialog.alert(rect, callbackFn, message, [informativeText], [buttonOne], [buttonTwo], [style]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Displays a simple non-blocking dialog box using `NSAlert` and a hidden `hs.webview` that's automatically destroyed when the alert is closed.                                                                                         |
| **Parameters**                                       | <ul><li>x - A number containing the horizontal co-ordinate of the top-left point of the dialog box.</li></ul><ul><li>y - A number containing the vertical co-ordinate of the top-left point of the dialog box.</li></ul><ul><li>callbackFn - The callback function that's called when a button is pressed.</li></ul><ul><li>message - The message text to display.</li></ul><ul><li>[informativeText] - Optional informative text to display.</li></ul><ul><li>[buttonOne] - An optional value for the first button as a string. Defaults to "OK".</li></ul><ul><li>[buttonTwo] - An optional value for the second button as a string. If <code>nil</code> is used, no second button will be displayed.</li></ul><ul><li>[style] - An optional style of the dialog box as a string. Defaults to "warning".</li></ul>   |
| **Returns**                                          | <ul><li>nil</li></ul>            |
| **Notes**                                            | <ul><li>The optional values must be entered in order (i.e. you can't supply <code>style</code> without also supplying <code>buttonOne</code> and <code>buttonTwo</code>).</li></ul><ul><li>[style] can be "warning", "informational" or "critical". If something other than these string values is given, it will use "informational".</li></ul><ul><li>Example:</li></ul><pre><code> ```testCallbackFn = function(result) print("Callback Result: " .. result) end</code></pre><pre><code> hs.dialog.alert(100, 100, testCallbackFn, "Message", "Informative Text", "Button One", "Button Two", "NSCriticalAlertStyle")</code></pre><pre><code> hs.dialog.alert(200, 200, testCallbackFn, "Message", "Informative Text", "Single Button")```</code></pre>                 |

#### [blockAlert](#blockalert)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.dialog.blockAlert(message, informativeText, [buttonOne], [buttonTwo], [style]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Displays a simple dialog box using `NSAlert` that will halt Lua code processing until the alert is closed.                                                                                         |
| **Parameters**                                       | <ul><li>message - The message text to display.</li></ul><ul><li>informativeText - The informative text to display.</li></ul><ul><li>[buttonOne] - An optional value for the first button as a string. Defaults to "OK".</li></ul><ul><li>[buttonTwo] - An optional value for the second button as a string. If <code>nil</code> is used, no second button will be displayed.</li></ul><ul><li>[style] - An optional style of the dialog box as a string. Defaults to "informational".</li></ul>   |
| **Returns**                                          | <ul><li>The value of the button as a string.</li></ul>            |
| **Notes**                                            | <ul><li>The optional values must be entered in order (i.e. you can't supply <code>style</code> without also supplying <code>buttonOne</code> and <code>buttonTwo</code>).</li></ul><ul><li>[style] can be "warning", "informational" or "critical". If something other than these string values is given, it will use "informational".</li></ul><ul><li>Example:</li></ul><pre><code> `hs.dialog.blockAlert("Message", "Informative Text", "Button One", "Button Two", "NSCriticalAlertStyle")`</code></pre>                 |

#### [chooseFileOrFolder](#choosefileorfolder)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.dialog.chooseFileOrFolder([message], [defaultPath], [canChooseFiles], [canChooseDirectories], [allowsMultipleSelection], [allowedFileTypes], [resolvesAliases]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Displays a file and/or folder selection dialog box using NSOpenPanel.                                                                                         |
| **Parameters**                                       | <ul><li>[message] - The optional message text to display.</li></ul><ul><li>[defaultPath] - The optional path you want to dialog to open to.</li></ul><ul><li>[canChooseFiles] - Whether or not the user can select files. Defaults to <code>true</code>.</li></ul><ul><li>[canChooseDirectories] - Whether or not the user can select folders. Default to <code>false</code>.</li></ul><ul><li>[allowsMultipleSelection] - Allow multiple selections of files and/or folders. Defaults to <code>false</code>.</li></ul><ul><li>[allowedFileTypes] - An optional table of allowed file types. Defaults to <code>true</code>.</li></ul><ul><li>[resolvesAliases] - An optional boolean that indicates whether the panel resolves aliases.</li></ul>   |
| **Returns**                                          | <ul><li>The selected files in a table or <code>nil</code> if cancel was pressed.</li></ul>            |
| **Notes**                                            | <ul><li>The optional values must be entered in order (i.e. you can't supply <code>allowsMultipleSelection</code> without also supplying <code>canChooseFiles</code> and <code>canChooseDirectories</code>).</li></ul><ul><li>Example:</li></ul><pre><code> `hs.inspect(hs.dialog.chooseFileOrFolder("Please select a file:", "~/Desktop", true, false, true, {"jpeg", "pdf"}, true))`</code></pre>                 |

#### [textPrompt](#textprompt)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.dialog.textPrompt(message, informativeText, [defaultText], [buttonOne], [buttonTwo]) -> string, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Displays a simple text input dialog box.                                                                                         |
| **Parameters**                                       | <ul><li>message - The message text to display</li></ul><ul><li>informativeText - The informative text to display</li></ul><ul><li>[defaultText] - The informative text to display</li></ul><ul><li>[buttonOne] - An optional value for the first button as a string</li></ul><ul><li>[buttonTwo] - An optional value for the second button as a string</li></ul>   |
| **Returns**                                          | <ul><li>The value of the button as a string</li></ul><ul><li>The value of the text input as a string</li></ul>            |
| **Notes**                                            | <ul><li><code>buttonOne</code> defaults to "OK" if no value is supplied.</li></ul><ul><li><code>buttonOne</code> will also be triggered by pressing <code>ENTER</code>, whereas <code>buttonTwo</code> will be triggered by pressing <code>ESC</code>.</li></ul><ul><li>Examples:</li></ul><pre><code> `hs.dialog.textPrompt("Main message.", "Please enter something:")`</code></pre><pre><code> `hs.dialog.textPrompt("Main message.", "Please enter something:", "Default Value", "OK")`</code></pre><pre><code> `hs.dialog.textPrompt("Main message.", "Please enter something:", "Default Value", "OK", "Cancel")`</code></pre>                 |

#### [webviewAlert](#webviewalert)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.dialog.webviewAlert(webview, callbackFn, message, [informativeText], [buttonOne], [buttonTwo], [style]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Displays a simple dialog box using `NSAlert` in a `hs.webview`.                                                                                         |
| **Parameters**                                       | <ul><li>webview - The <code>hs.webview</code> to display the alert on.</li></ul><ul><li>callbackFn - The callback function that's called when a button is pressed.</li></ul><ul><li>message - The message text to display.</li></ul><ul><li>[informativeText] - Optional informative text to display.</li></ul><ul><li>[buttonOne] - An optional value for the first button as a string. Defaults to "OK".</li></ul><ul><li>[buttonTwo] - An optional value for the second button as a string. If <code>nil</code> is used, no second button will be displayed.</li></ul><ul><li>[style] - An optional style of the dialog box as a string. Defaults to "warning".</li></ul>   |
| **Returns**                                          | <ul><li>nil</li></ul>            |
| **Notes**                                            | <ul><li>This alert is will prevent the user from interacting with the <code>hs.webview</code> until a button is pressed on the alert.</li></ul><ul><li>The optional values must be entered in order (i.e. you can't supply <code>style</code> without also supplying <code>buttonOne</code> and <code>buttonTwo</code>).</li></ul><ul><li>[style] can be "warning", "informational" or "critical". If something other than these string values is given, it will use "informational".</li></ul><ul><li>Example:</li></ul><pre><code> ```testCallbackFn = function(result) print("Callback Result: " .. result) end</code></pre><pre><code> testWebviewA = hs.webview.newBrowser(hs.geometry.rect(250, 250, 250, 250)):show()</code></pre><pre><code> testWebviewB = hs.webview.newBrowser(hs.geometry.rect(450, 450, 450, 450)):show()</code></pre><pre><code> hs.dialog.webviewAlert(testWebviewA, testCallbackFn, "Message", "Informative Text", "Button One", "Button Two", "warning")</code></pre><pre><code> hs.dialog.webviewAlert(testWebviewB, testCallbackFn, "Message", "Informative Text", "Single Button")```</code></pre>                 |

