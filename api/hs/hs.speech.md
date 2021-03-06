# [docs](index.md) » hs.speech
---

This module provides access to the Speech Synthesizer component of OS X.

The speech synthesizer functions and methods provide access to OS X's Text-To-Speech capabilities and facilitates generating speech output both to the currently active audio device and to an AIFF file.

A discussion concerning the embedding of commands into the text to be spoken can be found at https://developer.apple.com/library/mac/documentation/UserExperience/Conceptual/SpeechSynthesisProgrammingGuide/FineTuning/FineTuning.html#//apple_ref/doc/uid/TP40004365-CH5-SW6.  It is somewhat dated and specific to the older MacinTalk style voices, but still contains some information relevant to the more modern higer quality voices as well in its discussion about embedded commands.

## Submodules
 * [hs.speech.listener](hs.speech.listener.md)

## API Overview
* Functions - API calls offered directly by the extension
 * [attributesForVoice](#attributesforvoice)
 * [availableVoices](#availablevoices)
 * [defaultVoice](#defaultvoice)
 * [isAnyApplicationSpeaking](#isanyapplicationspeaking)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
* Methods - API calls which can only be made on an object returned by a constructor
 * [continue](#continue)
 * [isPaused](#ispaused)
 * [isSpeaking](#isspeaking)
 * [modulation](#modulation)
 * [pause](#pause)
 * [phonemes](#phonemes)
 * [phoneticSymbols](#phoneticsymbols)
 * [pitch](#pitch)
 * [rate](#rate)
 * [reset](#reset)
 * [setCallback](#setcallback)
 * [speak](#speak)
 * [speaking](#speaking)
 * [speakToFile](#speaktofile)
 * [stop](#stop)
 * [usesFeedbackWindow](#usesfeedbackwindow)
 * [voice](#voice)
 * [volume](#volume)

## API Documentation

### Functions

#### [attributesForVoice](#attributesforvoice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.speech.attributesForVoice(voice) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a table containing a variety of properties describing and defining the specified voice. |
| **Parameters**                                       | <ul><li>voice - the name of the voice to look up attributes for</li></ul> |
| **Returns**                                          | <ul><li>a table containing key-value pairs which describe the voice specified.  These attributes may include (but is not limited to) information about specific characters recognized, sample text, gender, etc.</li></ul> |
| **Notes**                                            | <ul><li>All of the names that have been encountered thus far follow this pattern for their full name:  <code>com.apple.speech.synthesis.voice.*name*</code>.  You can provide this suffix or not as you prefer when specifying a voice name.</li></ul> |

#### [availableVoices](#availablevoices)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.speech.availableVoices([full]) -> array` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a list of the currently installed voices for speech synthesis. |
| **Parameters**                                       | <ul><li>full - an optional boolean flag indicating whether or not the full internal names should be returned, or if the shorter versions should be returned.  Defaults to false.</li></ul> |
| **Returns**                                          | <ul><li>an array of the available voice names.</li></ul> |
| **Notes**                                            | <ul><li>All of the names that have been encountered thus far follow this pattern for their full name:  <code>com.apple.speech.synthesis.voice.*name*</code>.  This prefix is normally suppressed unless you pass in true.</li></ul> |

#### [defaultVoice](#defaultvoice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.speech.defaultVoice([full]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the name of the currently selected default voice for the user.  This voice is the voice selected in the System Preferences for Dictation & Speech as the System Voice. |
| **Parameters**                                       | <ul><li>full - an optional boolean flag indicating whether or not the full internal name should be returned, or if the shorter version should be returned.  Defaults to false.</li></ul> |
| **Returns**                                          | <ul><li>the name of the system voice.</li></ul> |
| **Notes**                                            | <ul><li>All of the names that have been encountered thus far follow this pattern for their full name:  <code>com.apple.speech.synthesis.voice.*name*</code>.  This prefix is normally suppressed unless you pass in true.</li></ul> |

#### [isAnyApplicationSpeaking](#isanyapplicationspeaking)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.speech.isAnyApplicationSpeaking() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns whether or not the system is currently using a speech synthesizer in any application to generate speech. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a boolean value indicating whether or not any application is currently generating speech with a synthesizer.</li></ul> |
| **Notes**                                            | <ul><li>See also <code>hs.speech:speaking</code>.</li></ul> |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.speech.new([voice]) -> synthesizerObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new speech synthesizer object for use by Hammerspoon. |
| **Parameters**                                       | <ul><li>voice - an optional string specifying the voice the synthesizer should use for generating speech.  Defaults to the system voice.</li></ul> |
| **Returns**                                          | <ul><li>a speech synthesizer object or nil, if the system was unable to create a new synthesizer.</li></ul> |
| **Notes**                                            | <ul><li>All of the names that have been encountered thus far follow this pattern for their full name:  <code>com.apple.speech.synthesis.voice.*name*</code>.  You can provide this suffix or not as you prefer when specifying a voice name.</li><li>You can change the voice later with the <code>hs.speech:voice</code> method.</li></ul> |

### Methods

#### [continue](#continue)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.speech:continue() -> synthesizerObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Resumes a paused speech synthesizer. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the synthesizer object</li></ul> |

#### [isPaused](#ispaused)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.speech:isPaused() -> boolean | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns whether or not the synthesizer is currently paused. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>True or false indicating whether or not the synthesizer is currently paused.  If there is an error, returns nil.</li></ul> |
| **Notes**                                            | <ul><li>If an error occurs retrieving this value, the details will be logged in the system logs which can be viewed with the Console application.  You can also have such messages logged to the Hammerspoon console by setting the module's log level to at least Information (This can be done with the following, or similar, command: <code>hs.speech.log.level = 3</code>.  See <code>hs.logger</code> for more information)</li></ul> |

#### [isSpeaking](#isspeaking)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.speech:isSpeaking() -> boolean | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns whether or not the synthesizer is currently speaking, either to an audio device or to a file. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>True or false indicating whether or not the synthesizer is currently producing speech.  If there is an error, returns nil.</li></ul> |
| **Notes**                                            | <ul><li>If an error occurs retrieving this value, the details will be logged in the system logs which can be viewed with the Console application.  You can also have such messages logged to the Hammerspoon console by setting the module's log level to at least Information (This can be done with the following, or similar, command: <code>hs.speech.log.level = 3</code>.  See <code>hs.logger</code> for more information)</li></ul> |

#### [modulation](#modulation)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.speech:modulation([modulation]) -> synthsizerObject | modulation | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets or sets the pitch modulation for the synthesizer's voice. |
| **Parameters**                                       | <ul><li>modulation - an optional number indicating the pitch modulation for the synthesizer.</li></ul> |
| **Returns**                                          | <ul><li>If no parameter is provided, returns the current value; otherwise returns the synthesizer object.  Returns nil if an error occurs.</li></ul> |
| **Notes**                                            | <ul><li>Pitch modulation is expressed as a floating-point value in the range of 0.000 to 127.000. These values correspond to MIDI note values, where 60.000 is equal to middle C on a piano scale. The most useful speech pitches fall in the range of 40.000 to 55.000. A pitch modulation value of 0.000 corresponds to a monotone in which all speech is generated at the frequency corresponding to the speech pitch. Given a speech pitch value of 46.000, a pitch modulation of 2.000 would mean that the widest possible range of pitches corresponding to the actual frequency of generated text would be 44.000 to 48.000.</li></ul> |

#### [pause](#pause)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.speech:pause([where]) -> synthesizerObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Pauses the output of the speech synthesizer. |
| **Parameters**                                       | <ul><li>where - an optional string indicating when to pause the audio output (defaults to "immediate").  The string can be one of the following:</li><li>"immediate" - pauses output immediately.  If in the middle of a word, when speech is resumed, the word will be repeated.</li><li>"word"      - pauses at the end of the current word.</li><li>"sentence"  - pauses at the end of the current sentence.</li></ul> |
| **Returns**                                          | <ul><li>the synthesizer object</li></ul> |

#### [phonemes](#phonemes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.speech:phonemes(text) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the phonemes which would be spoken if the text were to be synthesized. |
| **Parameters**                                       | <ul><li>text - the text to tokenize into phonemes.</li></ul> |
| **Returns**                                          | <ul><li>the text converted into the series of phonemes the synthesizer would use for the provided text if it were to be synthesized.</li></ul> |
| **Notes**                                            | <ul><li>This method only returns a phonetic representation of the text if a Macintalk voice has been selected.  The more modern higher quality voices do not use a phonetic representation and an empty string will be returned if this method is used.</li><li>You can modify the phonetic representation and feed it into <code>hs.speech:speak</code> if you find that the default interpretation is not correct.  You will need to set the input mode to Phonetic by prefixing the text with "[[inpt PHON]]".</li><li>The specific phonetic symbols recognized by a given voice can be queried by examining the array returned by <code>hs.speech:phoneticSymbols</code> after setting an appropriate voice.</li></ul> |

#### [phoneticSymbols](#phoneticsymbols)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.speech:phoneticSymbols() -> array | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns an array of the phonetic symbols recognized by the synthesizer for the current voice. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>For MacinTalk voices, this method will return an array of the recognized symbols for the currently selected voice.  For the modern higher quality voices, or if an error occurs, returns nil.</li></ul> |
| **Notes**                                            | <ul><li>Each entry in the array of phonemes returned will contain the following keys:</li><li>Symbol      - The textual representation of this phoneme when returned by <code>hs.speech:phonemes</code> or that you should use for this sound when crafting a phonetic string yourself.</li><li>Opcode      - The numeric opcode passed to the callback for the "willSpeakPhoneme" message corresponding to this phoneme.</li><li>Example     - An example word which contains the sound the phoneme represents</li><li>HiliteEnd   - The character position in the Example where this phoneme's sound begins</li><li>HiliteStart - The character position in the Example where this phoneme's sound ends</li></ul> |

#### [pitch](#pitch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.speech:pitch([pitch]) -> synthsizerObject | pitch | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets or sets the base pitch for the synthesizer's voice. |
| **Parameters**                                       | <ul><li>pitch - an optional number indicating the pitch base for the synthesizer.</li></ul> |
| **Returns**                                          | <ul><li>If no parameter is provided, returns the current value; otherwise returns the synthesizer object.  Returns nil if an error occurs.</li></ul> |
| **Notes**                                            | <ul><li>Typical voice frequencies range from around 90 hertz for a low-pitched male voice to perhaps 300 hertz for a high-pitched child’s voice. These frequencies correspond to approximate pitch values in the ranges of 30.000 to 40.000 and 55.000 to 65.000, respectively.</li></ul> |

#### [rate](#rate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.speech:rate([rate]) -> synthesizerObject | rate` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets or sets the synthesizers speaking rate (words per minute). |
| **Parameters**                                       | <ul><li>rate - an optional number indicating the speaking rate for the synthesizer.</li></ul> |
| **Returns**                                          | <ul><li>If no parameter is provided, returns the current value; otherwise returns the synthesizer object.</li></ul> |
| **Notes**                                            | <ul><li>The range of supported rates is not predefined by the Speech Synthesis framework; but the synthesizer may only respond to a limited range of speech rates. Average human speech occurs at a rate of 180.0 to 220.0 words per minute.</li></ul> |

#### [reset](#reset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.speech:reset() -> synthsizerObject | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Reset a synthesizer back to its default state. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>Returns the synthesizer object.  Returns nil if an error occurs.</li></ul> |
| **Notes**                                            | <ul><li>This method will reset a synthesizer to its default state, including pitch, modulation, volume, rate, etc.</li><li>The changes go into effect immediately, if queried, but will not affect a synthesis in progress.</li></ul> |

#### [setCallback](#setcallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.speech:setCallback(fn) -> synthesizerObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Sets or removes a callback function for the synthesizer. |
| **Parameters**                                       | <ul><li>fn - a function to set as the callback for this speech synthesizer.  If the value provided is nil, any currently existing callback function is removed.</li></ul> |
| **Returns**                                          | <ul><li>the synthesizer object</li></ul> |
| **Notes**                                            | <ul><li>The callback function should expect between 3 and 5 arguments and should not return anything.  The first two arguments will always be the synthesizer object itself and a string indicating the activity which has caused the callback.  The value of this string also dictates the remaining arguments as follows:</li></ul> |

#### [speak](#speak)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.speech:speak(textToSpeak) -> synthesizerObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Starts speaking the provided text through the system's current audio device. |
| **Parameters**                                       | <ul><li>textToSpeak - the text to speak with the synthesizer.</li></ul> |
| **Returns**                                          | <ul><li>the synthesizer object</li></ul> |

#### [speaking](#speaking)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.speech:speaking() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns whether or not this synthesizer is currently generating speech. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A boolean value indicating whether or not this synthesizer is currently generating speech.</li></ul> |
| **Notes**                                            | <ul><li>See also <code>hs.speech.isAnyApplicationSpeaking</code>.</li></ul> |

#### [speakToFile](#speaktofile)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.speech:speakToFile(textToSpeak, destination) -> synthesizerObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Starts speaking the provided text and saves the audio as an AIFF file. |
| **Parameters**                                       | <ul><li>textToSpeak - the text to speak with the synthesizer.</li><li>destination - the path to the file to create and store the audio data in.</li></ul> |
| **Returns**                                          | <ul><li>the synthesizer object</li></ul> |

#### [stop](#stop)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.speech:stop([where]) -> synthesizerObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Stops the output of the speech synthesizer. |
| **Parameters**                                       | <ul><li>where - an optional string indicating when to stop the audio output (defaults to "immediate").  The string can be one of the following:</li><li>"immediate" - stops output immediately.</li><li>"word"      - stops at the end of the current word.</li><li>"sentence"  - stops at the end of the current sentence.</li></ul> |
| **Returns**                                          | <ul><li>the synthesizer object</li></ul> |

#### [usesFeedbackWindow](#usesfeedbackwindow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.speech:usesFeedbackWindow([flag]) -> synthesizerObject | boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets or sets whether or not the synthesizer uses the speech feedback window. |
| **Parameters**                                       | <ul><li>flag - an optional boolean indicating whether or not the synthesizer should user the speech feedback window or not.  Defaults to false.</li></ul> |
| **Returns**                                          | <ul><li>If no parameter is provided, returns the current value; otherwise returns the synthesizer object.</li></ul> |
| **Notes**                                            | <ul><li><em>Special Note:</em> I am not sure where the visual feedback actually occurs -- I have not been able to locate a feedback window for synthesis in 10.11; however the method is defined and not marked deprecated, so I include it in the module.  If anyone has more information, please file an issue and the documentation will be updated.</li></ul> |

#### [voice](#voice)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.speech:voice([full] | [voice]) -> synthesizerObject | voice` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets or sets the active voice for a synthesizer. |
| **Parameters**                                       | <ul><li>full  - an optional boolean indicating whether or not you wish the full internal voice name to be returned, or if you want the shorter version.  Defaults to false.</li><li>voice - an optional string indicating the name of the voice to change the synthesizer to.</li></ul> |
| **Returns**                                          | <ul><li>If no parameter is provided (or the parameter is a boolean value), returns the current value; otherwise returns the synthesizer object or nil if the voice could not be changed for some reason.</li></ul> |
| **Notes**                                            | <ul><li>All of the names that have been encountered thus far follow this pattern for their full name:  <code>com.apple.speech.synthesis.voice.*name*</code>.  You can provide this suffix or not as you prefer when specifying a voice name.</li><li>The voice cannot be changed while the synthesizer is currently producing output.</li><li>If you change the voice while a synthesizer is paused, the current synthesis will be terminated and the voice will be changed.</li></ul> |

#### [volume](#volume)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.speech:volume([volume]) -> synthesizerObject | volume` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets or sets the synthesizers speaking volume. |
| **Parameters**                                       | <ul><li>volume - an optional number between 0.0 and 1.0 indicating the speaking volume for the synthesizer.</li></ul> |
| **Returns**                                          | <ul><li>If no parameter is provided, returns the current value; otherwise returns the synthesizer object.</li></ul> |
| **Notes**                                            | <ul><li>Volume units lie on a scale that is linear with amplitude or voltage. A doubling of perceived loudness corresponds to a doubling of the volume.</li></ul> |

