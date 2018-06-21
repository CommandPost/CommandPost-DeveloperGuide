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
| **Parameters**                                       | <ul markdown="1"><li markdown="1">x - A number containing the horizontal co-ordinate of the top-left point of the dialog box.</li><li markdown="1">y - A number containing the vertical co-ordinate of the top-left point of the dialog box.</li><li markdown="1">callbackFn - The callback function that's called when a button is pressed.</li><li markdown="1">message - The message text to display.</li><li markdown="1">[informativeText] - Optional informative text to display.</li><li markdown="1">[buttonOne] - An optional value for the first button as a string. Defaults to "OK".</li><li markdown="1">[buttonTwo] - An optional value for the second button as a string. If `nil` is used, no second button will be displayed.</li><li markdown="1">[style] - An optional style of the dialog box as a string. Defaults to "warning".</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">nil</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">The optional values must be entered in order (i.e. you can't supply `style` without also supplying `buttonOne` and `buttonTwo`).</li><li markdown="1">[style] can be "warning", "informational" or "critical". If something other than these string values is given, it will use "informational".</li><li markdown="1">Example:</li><li markdown="1">     ```testCallbackFn = function(result) print("Callback Result: " .. result) end</li><li markdown="1">     hs.dialog.alert(100, 100, testCallbackFn, "Message", "Informative Text", "Button One", "Button Two", "NSCriticalAlertStyle")</li><li markdown="1">     hs.dialog.alert(200, 200, testCallbackFn, "Message", "Informative Text", "Single Button")```</li></ul>                |

#### [blockAlert](#blockalert)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.dialog.blockAlert(message, informativeText, [buttonOne], [buttonTwo], [style]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Displays a simple dialog box using `NSAlert` that will halt Lua code processing until the alert is closed.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">message - The message text to display.</li><li markdown="1">informativeText - The informative text to display.</li><li markdown="1">[buttonOne] - An optional value for the first button as a string. Defaults to "OK".</li><li markdown="1">[buttonTwo] - An optional value for the second button as a string. If `nil` is used, no second button will be displayed.</li><li markdown="1">[style] - An optional style of the dialog box as a string. Defaults to "informational".</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The value of the button as a string.</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">The optional values must be entered in order (i.e. you can't supply `style` without also supplying `buttonOne` and `buttonTwo`).</li><li markdown="1">[style] can be "warning", "informational" or "critical". If something other than these string values is given, it will use "informational".</li><li markdown="1">Example:</li><li markdown="1">     `hs.dialog.blockAlert("Message", "Informative Text", "Button One", "Button Two", "NSCriticalAlertStyle")`</li></ul>                |

#### [chooseFileOrFolder](#choosefileorfolder)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.dialog.chooseFileOrFolder([message], [defaultPath], [canChooseFiles], [canChooseDirectories], [allowsMultipleSelection], [allowedFileTypes], [resolvesAliases]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Displays a file and/or folder selection dialog box using NSOpenPanel.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">[message] - The optional message text to display.</li><li markdown="1">[defaultPath] - The optional path you want to dialog to open to.</li><li markdown="1">[canChooseFiles] - Whether or not the user can select files. Defaults to `true`.</li><li markdown="1">[canChooseDirectories] - Whether or not the user can select folders. Default to `false`.</li><li markdown="1">[allowsMultipleSelection] - Allow multiple selections of files and/or folders. Defaults to `false`.</li><li markdown="1">[allowedFileTypes] - An optional table of allowed file types. Defaults to `true`.</li><li markdown="1">[resolvesAliases] - An optional boolean that indicates whether the panel resolves aliases.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The selected files in a table or `nil` if cancel was pressed.</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">The optional values must be entered in order (i.e. you can't supply `allowsMultipleSelection` without also supplying `canChooseFiles` and `canChooseDirectories`).</li><li markdown="1">Example:</li><li markdown="1">     `hs.inspect(hs.dialog.chooseFileOrFolder("Please select a file:", "~/Desktop", true, false, true, {"jpeg", "pdf"}, true))`</li></ul>                |

#### [textPrompt](#textprompt)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.dialog.textPrompt(message, informativeText, [defaultText], [buttonOne], [buttonTwo]) -> string, string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Displays a simple text input dialog box.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">message - The message text to display</li><li markdown="1">informativeText - The informative text to display</li><li markdown="1">[defaultText] - The informative text to display</li><li markdown="1">[buttonOne] - An optional value for the first button as a string</li><li markdown="1">[buttonTwo] - An optional value for the second button as a string</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">The value of the button as a string</li><li markdown="1">The value of the text input as a string</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">`buttonOne` defaults to "OK" if no value is supplied.</li><li markdown="1">`buttonOne` will also be triggered by pressing `ENTER`, whereas `buttonTwo` will be triggered by pressing `ESC`.</li><li markdown="1">Examples:</li><li markdown="1">     `hs.dialog.textPrompt("Main message.", "Please enter something:")`</li><li markdown="1">     `hs.dialog.textPrompt("Main message.", "Please enter something:", "Default Value", "OK")`</li><li markdown="1">     `hs.dialog.textPrompt("Main message.", "Please enter something:", "Default Value", "OK", "Cancel")`</li></ul>                |

#### [webviewAlert](#webviewalert)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.dialog.webviewAlert(webview, callbackFn, message, [informativeText], [buttonOne], [buttonTwo], [style]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Displays a simple dialog box using `NSAlert` in a `hs.webview`.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">webview - The `hs.webview` to display the alert on.</li><li markdown="1">callbackFn - The callback function that's called when a button is pressed.</li><li markdown="1">message - The message text to display.</li><li markdown="1">[informativeText] - Optional informative text to display.</li><li markdown="1">[buttonOne] - An optional value for the first button as a string. Defaults to "OK".</li><li markdown="1">[buttonTwo] - An optional value for the second button as a string. If `nil` is used, no second button will be displayed.</li><li markdown="1">[style] - An optional style of the dialog box as a string. Defaults to "warning".</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">nil</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">This alert is will prevent the user from interacting with the `hs.webview` until a button is pressed on the alert.</li><li markdown="1">The optional values must be entered in order (i.e. you can't supply `style` without also supplying `buttonOne` and `buttonTwo`).</li><li markdown="1">[style] can be "warning", "informational" or "critical". If something other than these string values is given, it will use "informational".</li><li markdown="1">Example:</li><li markdown="1">     ```testCallbackFn = function(result) print("Callback Result: " .. result) end</li><li markdown="1">     testWebviewA = hs.webview.newBrowser(hs.geometry.rect(250, 250, 250, 250)):show()</li><li markdown="1">     testWebviewB = hs.webview.newBrowser(hs.geometry.rect(450, 450, 450, 450)):show()</li><li markdown="1">     hs.dialog.webviewAlert(testWebviewA, testCallbackFn, "Message", "Informative Text", "Button One", "Button Two", "warning")</li><li markdown="1">     hs.dialog.webviewAlert(testWebviewB, testCallbackFn, "Message", "Informative Text", "Single Button")```</li></ul>                |

