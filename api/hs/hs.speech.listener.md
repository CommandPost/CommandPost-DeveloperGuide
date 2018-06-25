# [docs](index.md) » hs.speech.listener
---

This module provides access to the Speech Recognizer component of OS X.

The speech recognizer functions and methods provide a way to add commands which may be issued to Hammerspoon through spoken words and phrases to trigger a callback.

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [blocksOtherRecognizers](#blocksotherrecognizers)
 * [commands](#commands)
 * [delete](#delete)
 * [foregroundOnly](#foregroundonly)
 * [isListening](#islistening)
 * [setCallback](#setcallback)
 * [start](#start)
 * [stop](#stop)
 * [title](#title)

## API Documentation

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.speech.listener.new([title]) -> recognizerObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new speech recognizer object for use by Hammerspoon.                                                                                         |
| **Parameters**                                       | <ul><br /><li>title - an optional parameter specifying the title under which commands assigned to this speech recognizer will be listed in the Dictation Commands display when it is visible.  Defaults to "Hammerspoon".</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>a speech recognizer object or nil, if the system was unable to create a new recognizer.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>You can change the title later with the <code>hs.speech.listener:title</code> method.</li><br /></ul>                                             |

### Methods

#### [blocksOtherRecognizers](#blocksotherrecognizers)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.speech.listener:blocksOtherRecognizers([flag]) -> recognizerObject | current value` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set whether or not the speech recognizer should block other recognizers when it is active.                                                                                         |
| **Parameters**                                       | <ul><br /><li>flag - an optional boolean indicating whether or not the speech recognizer should block other speech recognizers when it is active. Defaults to false.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>If no parameter is provided, returns the current value; otherwise returns the recognizer object.</li><br /></ul>                                           |

#### [commands](#commands)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.speech.listener:commands([commandsArray]) -> recognizerObject | current value` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set the commands this speech recognizer will listen for.                                                                                         |
| **Parameters**                                       | <ul><br /><li>commandsArray - an optional array of strings which specify the commands the recognizer will listen for.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>If no parameter is provided, returns the current value; otherwise returns the recognizer object.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>The list of commands will appear in the Dictation Commands window, if it is visible, under the title of this speech recognizer.  The text of each command is a possible value which may be sent as the second argument to a callback function for this speech recognizer, if one is defined. * Setting this to an empty list does not disable the speech recognizer, but it does make it of limited use, other than to provide a title in the Dictation Commands window.  To disable the recognizer, use the <code>hs.speech.listener:stop</code> or <code>hs.speech.listener:delete</code> methods.</li><br /></ul>                                             |

#### [delete](#delete)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.speech.listener:delete() -> recognizerObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Disables the speech recognizer and removes it from the possible available speech recognizers.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>None</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>this disables the speech recognizer and removes it from the list in the Dictation Commands window.  The object is effectively destroyed, so you will need to create a new one with <code>hs.speech.listener.new</code> if you want to bring it back. * if this was the only speech recognizer currently available, the Dictation Commands window and feedback display will be removed from the users display. * this method is automatically called during a reload or restart of Hammerspoon.</li><br /></ul>                                             |

#### [foregroundOnly](#foregroundonly)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.speech.listener:foregroundOnly([flag]) -> recognizerObject | current value` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set whether or not the speech recognizer is active only when the Hammerspoon application is active.                                                                                         |
| **Parameters**                                       | <ul><br /><li>flag - an optional boolean indicating whether or not the speech recognizer should respond to commands only when Hammerspoon is the active application or not. Defaults to true.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>If no parameter is provided, returns the current value; otherwise returns the recognizer object.</li><br /></ul>                                           |

#### [isListening](#islistening)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.speech.listener:isListening() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a boolean value indicating whether or not the recognizer is currently enabled (started).                                                                                         |
| **Parameters**                                       | <ul><br /><li>None</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>true if the listener is listening (has been started) or false if it is not.</li><br /></ul>                                           |

#### [setCallback](#setcallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.speech.listener:setCallback(fn | nil) -> recognizerObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Sets or removes a callback function for the speech recognizer.                                                                                         |
| **Parameters**                                       | <ul><br /><li>fn - a function to set as the callback for this speech synthesizer.  If the value provided is nil, any currently existing callback function is removed.  The callback function should accept two arguments and return none.  The arguments will be the speech recognizer object itself and the string of the command which was spoken.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>the recognizer object</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>Possible string values for the command spoken are set with the <code>hs.speech.listener:commands</code> method. * Removing the callback does not disable the speech recognizer, but it does make it of limited use, other than to provide a list in the Dictation Commands window.  To disable the recognizer, use the <code>hs.speech.listener:stop</code> or <code>hs.speech.listener:delete</code> methods.</li><br /></ul>                                             |

#### [start](#start)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.speech.listener:start() -> recognizerObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Make the speech recognizer active.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>returns the recognizer object.</li><br /></ul>                                           |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.speech.listener:stop() -> recognizerObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Disables the speech recognizer.                                                                                         |
| **Parameters**                                       | <ul><br /><li>None.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>returns the recognizer object.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>this only disables the speech recognizer.  To completely remove it from the list in the Dictation Commands window, use <code>hs.speech.listener:delete</code>.</li><br /></ul>                                             |

#### [title](#title)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.speech.listener:title([title]) -> recognizerObject | current value` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set the title for a speech recognizer.                                                                                         |
| **Parameters**                                       | <ul><br /><li>title - an optional parameter specifying the title under which commands assigned to this speech recognizer will be listed in the Dictation Commands display when it is visible.  If you provide an explicit <code>nil</code>, it will reset to the default of "Hammerspoon".</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>If no parameter is provided, returns the current value; otherwise returns the recognizer object.</li><br /></ul>                                           |

