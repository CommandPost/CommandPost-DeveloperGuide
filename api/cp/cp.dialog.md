# [docs](index.md) » cp.dialog
---

A collection of handy Dialog tools for CommandPost.

This extension should no longer be used in favour of `hs.dialog`.

## API Overview
* Functions - API calls offered directly by the extension
 * [displayAlertMessage](#displayalertmessage)
 * [displayChooseFile](#displaychoosefile)
 * [displayChooseFolder](#displaychoosefolder)
 * [displayChooseFromList](#displaychoosefromlist)
 * [displayErrorMessage](#displayerrormessage)
 * [displayMessage](#displaymessage)
 * [displayNotification](#displaynotification)
 * [displaySmallNumberTextBoxMessage](#displaysmallnumbertextboxmessage)
 * [displayTextBoxMessage](#displaytextboxmessage)
 * [displayYesNoQuestion](#displayyesnoquestion)

## API Documentation

### Functions

#### [displayAlertMessage](#displayalertmessage)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.dialog.displayAlertMessage(message) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Display an Alert Dialog (with stop icon).                                                                                         |
| **Parameters**                                       | <ul><li>message - The message you want to display as a string</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |
| **Notes**                                            | <ul><li>IMPORTANT: This should no longer be used in favour of `hs.dialog.alert`</li></ul>                |

#### [displayChooseFile](#displaychoosefile)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.dialog.displayChooseFile(whatMessage, fileType[, defaultLocation]) -> boolean or string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Display a Choose File Dialog Box.                                                                                         |
| **Parameters**                                       | <ul><li>whatMessage - The message you want to display as a string</li><li>fileType - The filetype you wish to display</li><li>defaultLocation - Path to Default Location</li></ul> |
| **Returns**                                          | <ul><li>`false` if cancelled if pressed otherwise the path to the file as a string</li></ul>          |
| **Notes**                                            | <ul><li>IMPORTANT: This should no longer be used in favour of `hs.dialog.chooseFileOrFolder`</li></ul>                |

#### [displayChooseFolder](#displaychoosefolder)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.dialog.displayChooseFolder(whatMessage[, defaultLocation]) -> boolean or string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Display a Choose Folder Dialog Box.                                                                                         |
| **Parameters**                                       | <ul><li>whatMessage - The message you want to display as a string</li><li>defaultLocation - Path to Default Location</li></ul> |
| **Returns**                                          | <ul><li>`false` if cancelled if pressed otherwise the path to the folder as a string</li></ul>          |
| **Notes**                                            | <ul><li>IMPORTANT: This should no longer be used in favour of `hs.dialog.chooseFileOrFolder`</li></ul>                |

#### [displayChooseFromList](#displaychoosefromlist)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.dialog.displayChooseFromList(dialogPrompt, listOptions, defaultItems) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Displays a list that the user can select items from.                                                                                         |
| **Parameters**                                       | <ul><li>dialogPrompt - The message you want to display as a string</li><li>listOptions - A table containing all the options you want to include in the list as strings</li><li>defaultItems - A table containing all the options you want select by default in the list as strings</li></ul> |
| **Returns**                                          | <ul><li>A table with the selected items as strings</li></ul>          |

#### [displayErrorMessage](#displayerrormessage)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.dialog.displayErrorMessage(whatError) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Display an Error Message Dialog, given the user the option to submit feedback.                                                                                         |
| **Parameters**                                       | <ul><li>whatError - The message you want to display as a string</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |
| **Notes**                                            | <ul><li>IMPORTANT: This should no longer be used in favour of `hs.dialog.alert`</li></ul>                |

#### [displayMessage](#displaymessage)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.dialog.displayMessage(whatMessage, optionalButtons) -> object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Display an Error Message Dialog, given the user the option to submit feedback.                                                                                         |
| **Parameters**                                       | <ul><li>whatError - The message you want to display as a string</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |
| **Notes**                                            | <ul><li>IMPORTANT: This should no longer be used in favour of `hs.dialog.alert`</li></ul>                |

#### [displayNotification](#displaynotification)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.dialog.displayNotification(whatMessage) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Display's an alert on the screen.                                                                                         |
| **Parameters**                                       | <ul><li>whatMessage - The message you want to display as a string</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |
| **Notes**                                            | <ul><li>Any existing alerts will be removed to make way for the new one.</li></ul>                |

#### [displaySmallNumberTextBoxMessage](#displaysmallnumbertextboxmessage)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.dialog.displaySmallNumberTextBoxMessage(whatMessage, whatErrorMessage, defaultAnswer) -> boolean or string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Display a dialog box prompting the user for a number input. It accepts only entries that coerce directly to class integer.                                                                                         |
| **Parameters**                                       | <ul><li>whatMessage - The message you want to display as a string</li><li>whatErrorMessage - The error message that appears if a user input is invalid</li><li>defaultAnswer - The default value of the text box</li></ul> |
| **Returns**                                          | <ul><li>`false` if cancelled if pressed otherwise the text entered in the dialog box</li></ul>          |
| **Notes**                                            | <ul><li>IMPORTANT: This should no longer be used in favour of `hs.dialog.textPrompt`</li></ul>                |

#### [displayTextBoxMessage](#displaytextboxmessage)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.dialog.displayTextBoxMessage(whatMessage, whatErrorMessage, defaultAnswer, validationFn) -> boolean or string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Display a dialog box prompting the user for a text input.                                                                                         |
| **Parameters**                                       | <ul><li>whatMessage - The message you want to display as a string</li><li>whatErrorMessage - The error message that appears if a user input is invalid</li><li>defaultAnswer - The default value of the text box</li><li>validationFn - A function that takes one parameter and returns a boolean value</li></ul> |
| **Returns**                                          | <ul><li>`false` if cancelled if pressed otherwise the text entered in the dialog box</li></ul>          |
| **Notes**                                            | <ul><li>IMPORTANT: This should no longer be used in favour of `hs.dialog.textPrompt`</li></ul>                |

#### [displayYesNoQuestion](#displayyesnoquestion)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.dialog.displayYesNoQuestion(message) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Displays a "Yes" or "No" question.                                                                                         |
| **Parameters**                                       | <ul><li>whatMessage - The message you want to display as a string</li></ul> |
| **Returns**                                          | <ul><li>`true` if yes is clicked otherwise `false`</li></ul>          |
| **Notes**                                            | <ul><li>IMPORTANT: This should no longer be used in favour of `hs.dialog.alert`</li></ul>                |

