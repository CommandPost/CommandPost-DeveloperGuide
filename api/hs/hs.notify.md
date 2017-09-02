# [docs](index.md) » hs.notify
---

This module allows you to create on screen notifications in the User Notification Center located at the right of the users screen.

Notifications can be sent immediately or scheduled for delivery at a later time, even if that scheduled time occurs when Hammerspoon is not currently running. Currently, if you take action on a notification while Hammerspoon is not running, the callback function is not honored for the first notification clicked upon -- This is expected to be fixed in a future release.

When setting up a callback function, you have the option of specifying it with the creation of the notification (hs.notify.new) or by pre-registering it with hs.notify.register and then referring it to by the tag name specified with hs.notify.register. If you use this registration method for defining your callback functions, and make sure to register all expected callback functions within your init.lua file or files it includes, then callback functions will remain available for existing notifications in the User Notification Center even if Hammerspoon's configuration is reloaded or if Hammerspoon is restarted. If the callback tag is not present when the user acts on the notification, the Hammerspoon console will be raised as a default action.

A shorthand, based upon the original inspiration for this module from Hydra and Mjolnir, hs.notify.show, is provided if you just require a quick and simple informative notification without the bells and whistles.

This module is based in part on code from the previous incarnation of Mjolnir by [Steven Degutis](https://github.com/sdegutis/).

## API Overview
* Constants - Useful values which cannot be changed
 * [activationTypes](#activationtypes)
 * [defaultNotificationSound](#defaultnotificationsound)
* Variables - Configurable values
 * [registry](#registry)
 * [warnAboutMissingFunctionTag](#warnaboutmissingfunctiontag)
* Functions - API calls offered directly by the extension
 * [register](#register)
 * [unregister](#unregister)
 * [unregisterall](#unregisterall)
 * [withdrawAll](#withdrawall)
 * [withdrawAllScheduled](#withdrawallscheduled)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
 * [show](#show)
* Methods - API calls which can only be made on an object returned by a constructor
 * [actionButtonTitle](#actionbuttontitle)
 * [activationType](#activationtype)
 * [actualDeliveryDate](#actualdeliverydate)
 * [alwaysPresent](#alwayspresent)
 * [autoWithdraw](#autowithdraw)
 * [contentImage](#contentimage)
 * [delivered](#delivered)
 * [getFunctionTag](#getfunctiontag)
 * [hasActionButton](#hasactionbutton)
 * [informativeText](#informativetext)
 * [otherButtonTitle](#otherbuttontitle)
 * [presented](#presented)
 * [release](#release)
 * [schedule](#schedule)
 * [send](#send)
 * [setIdImage](#setidimage)
 * [soundName](#soundname)
 * [subTitle](#subtitle)
 * [title](#title)
 * [withdraw](#withdraw)

## API Documentation

### Constants

#### [activationTypes](#activationtypes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.notify.activationTypes[]` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Convenience array of the possible activation types for a notification, and their reverse for reference.                                                                                         |
| **Notes**                                            | <ul><li>Count starts at zero. (implemented in Objective-C)</li></ul>                |

#### [defaultNotificationSound](#defaultnotificationsound)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.notify.defaultNotificationSound` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The string representation of the default notification sound. Use `hs.notify:soundName()` or set the `soundName` attribute in `hs:notify.new()`, to this constant, if you want to use the default sound                                                                                         |

### Variables

#### [registry](#registry)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.notify.registry[]` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | A table containing the registered callback functions and their tags.                                                                                         |
| **Notes**                                            | <ul><li>This table should not be modified directly. Use the `hs.notify.register(tag, fn)` and `hs.notify.unregister(id)` functions.</li><li>This table has a __tostring metamethod so you can see the list of registered function tags in the console by typing `hs.notify.registry`</li><li>See [hs.notify.warnAboutMissingFunctionTag](#warnAboutMissingFunctionTag) for determining the behavior when a notification attempts to perform a callback to a function tag which is not present in this table. This occurrence is most common with notifications which are acted upon by the user after Hammerspoon has been reloaded.</li></ul>                |

#### [warnAboutMissingFunctionTag](#warnaboutmissingfunctiontag)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.notify.warnAboutMissingFunctionTag` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Variable                                                                                         |
| **Description**                                      | A value indicating whether or not a missing notification function tag should cause a warning.  Defaults to `true`.                                                                                         |

### Functions

#### [register](#register)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.notify.register(tag, fn) -> id` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Registers a function callback with the specified tag for a notification. The callback function will be invoked when the user clicks on or interacts with a notification.                                                                                         |
| **Parameters**                                       | <ul><li>tag - a string tag to identify the registered callback function. Use this as the function tag in `hs.notify.new` and `hs.notify.show`</li><li>fn  - the function which should be invoked when a notification with this tag is interacted with.</li></ul> |
| **Returns**                                          | <ul><li>a numerical id representing the entry in `hs.notify.registry` for this function. This number can be used with `hs.notify.unregister` to unregister a function later if you wish.</li></ul>          |
| **Notes**                                            | <ul><li>If a function is already registered with the specified tag, it is replaced by with the new one.</li></ul>                |

#### [unregister](#unregister)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.notify.unregister(id|tag)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Unregisters a function callback so that it is no longer available as a callback when notifications corresponding to the specified entry are interacted with.                                                                                         |
| **Parameters**                                       | <ul><li>id or tag - the numerical id provided by `hs.notify.register` or string tag representing the callback function to be removed</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [unregisterall](#unregisterall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.notify.unregisterall()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Unregisters all functions registered as callbacks.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |
| **Notes**                                            | <ul><li>This does not remove the notifications from the User Notification Center, it just removes their callback function for when the user interacts with them. To remove all notifications, see `hs.notify.withdrawAll` and `hs.notify.withdrawAllScheduled`</li></ul>                |

#### [withdrawAll](#withdrawall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.notify.withdrawAll()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Withdraw all delivered notifications from Hammerspoon                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |
| **Notes**                                            | <ul><li>This will withdraw all notifications for Hammerspoon, including those not sent by this module or that linger from a previous load of Hammerspoon.</li></ul>                |

#### [withdrawAllScheduled](#withdrawallscheduled)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.notify.withdrawAllScheduled()` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Withdraw all scheduled notifications from Hammerspoon                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.notify.new([fn,][attributes]) -> notification` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Creates a new notification object                                                                                         |
| **Parameters**                                       | <ul><li>fn - An optional function or function-tag, which will be called when the user interacts with notifications. The notification object will be passed as an argument to the function. If you leave this parameter out or specify nil, then no callback will be attached to the notification.</li><li>attributes - An optional table for applying attributes to the notification. Possible keys are:</li></ul> |
| **Returns**                                          | <ul><li>A notification object</li></ul>          |
| **Notes**                                            | <ul><li>A function-tag is a string key which corresponds to a function stored in the `hs.notify.registry` table with the `hs.notify.register()` function.</li><li>If a notification does not have a `title` attribute set, OS X will not display it, so by default it will be set to "Notification". You can use the `title` key in the attributes table, or call `hs.notify:title()` before displaying the notification to change this.</li></ul>                |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.notify.show(title, subTitle, information[, tag]) -> notfication` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor                                                                                         |
| **Description**                                      | Shorthand constructor to create and show simple notifications                                                                                         |
| **Parameters**                                       | <ul><li>title       - the title for the notification</li><li>subTitle    - the subtitle, or second line, of the notification</li><li>information - the main textual body of the notification</li><li>tag         - a function tag corresponding to a function registered with `hs.notify.register`</li></ul> |
| **Returns**                                          | <ul><li>a notification object</li></ul>          |
| **Notes**                                            | <ul><li>All three textual parameters are required, though they can be empty strings</li><li>This function is really a shorthand for `hs.notify.new(...):send()`</li></ul>                |

### Methods

#### [actionButtonTitle](#actionbuttontitle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.notify:actionButtonTitle([buttonTitle]) -> notificationObject | current-setting` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set the label of a notification's action button                                                                                         |
| **Parameters**                                       | <ul><li>buttonTitle - An optional string containing the title for the notification's action button.  If no parameter is provided, then the current setting is returned.</li></ul> |
| **Returns**                                          | <ul><li>The notification object, if buttonTitle is present; otherwise the current setting.</li></ul>          |
| **Notes**                                            | <ul><li>The affects of this method only apply if the user has set Hammerspoon notifications to `Alert` in the Notification Center pane of System Preferences</li></ul>                |

#### [activationType](#activationtype)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.notify:activationType() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns how the notification was activated by the user.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>the integer value corresponding to how the notification was activated by the user.  See the table `hs.notify.activationTypes[]` for more information.</li></ul>          |

#### [actualDeliveryDate](#actualdeliverydate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.notify:actualDeliveryDate() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the date and time when a notification was delivered                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A number containing the delivery date/time of the notification, in seconds since the epoch (i.e. 1970-01-01 00:00:00 +0000)</li></ul>          |
| **Notes**                                            | <ul><li>You can turn epoch times into a human readable string or a table of date elements with the `os.date()` function.</li></ul>                |

#### [alwaysPresent](#alwayspresent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.notify:alwaysPresent([alwaysPresent]) -> notificationObject | current-setting` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set whether a notification should be presented even if this overrides Notification Center's decision process.                                                                                         |
| **Parameters**                                       | <ul><li>alwaysPresent - An optional boolean parameter indicating whether the notification should override Notification Center's decision about whether to present the notification or not. Defaults to true.  If no parameter is provided, then the current setting is returned.</li></ul> |
| **Returns**                                          | <ul><li>The notification object, if alwaysPresent is provided; otherwise the current setting.</li></ul>          |
| **Notes**                                            | <ul><li>This does not affect the return value of `hs.notify:presented()` -- that will still reflect the decision of the Notification Center</li><li>Examples of why the users Notification Center would choose not to display a notification would be if Hammerspoon is the currently focussed application, being attached to a projector, or the user having set Do Not Disturb.</li></ul>                |

#### [autoWithdraw](#autowithdraw)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.notify:autoWithdraw([shouldWithdraw]) -> notificationObject | current-setting` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set whether a notification should automatically withdraw once activated                                                                                         |
| **Parameters**                                       | <ul><li>shouldWithdraw - An optional boolean indicating whether the notification should automatically withdraw. Defaults to true.  If no parameter is provided, then the current setting is returned.</li></ul> |
| **Returns**                                          | <ul><li>The notification object, if shouldWithdraw is present; otherwise the current setting.</li></ul>          |

#### [contentImage](#contentimage)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.notify:contentImage([image]) -> notificationObject | current-setting` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set a notification's content image.                                                                                         |
| **Parameters**                                       | <ul><li>image - An optional hs.image parameter containing the image to display. Defaults to nil. If no parameter is provided, then the current setting is returned.</li></ul> |
| **Returns**                                          | <ul><li>The notification object, if image is provided; otherwise the current setting.</li></ul>          |
| **Notes**                                            | <ul><li>See hs.image for details on how to specify or define an image</li><li>This method is only supported in OS X 10.9 or greater. A warning will be displayed in the console and the method will be treated as a no-op if used on an unsupported system.</li></ul>                |

#### [delivered](#delivered)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.notify:delivered() -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns whether the notification has been delivered to the Notification Center                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A boolean indicating whether the notification has been delivered to the users Notification Center</li></ul>          |

#### [getFunctionTag](#getfunctiontag)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.notify:getFunctionTag() -> functiontag` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Return the name of the function tag the notification will call when activated.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The function tag for this notification as a string.</li></ul>          |
| **Notes**                                            | <ul><li>This tag should correspond to a function in `hs.notify.registry` and can be used to either add a replacement with `hs.notify.register(...)` or remove it with `hs.notify.unregister(...)`</li></ul>                |

#### [hasActionButton](#hasactionbutton)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.notify:hasActionButton([hasButton]) -> notificationObject | current-setting` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set the presence of an action button in a notification                                                                                         |
| **Parameters**                                       | <ul><li>hasButton - An optional boolean indicating whether an action button should be present.  If no parameter is provided, then the current setting is returned.</li></ul> |
| **Returns**                                          | <ul><li>The notification object, if hasButton is present; otherwise the current setting.</li></ul>          |
| **Notes**                                            | <ul><li>The affects of this method only apply if the user has set Hammerspoon notifications to `Alert` in the Notification Center pane of System Preferences</li></ul>                |

#### [informativeText](#informativetext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.notify:informativeText([informativeText]) -> notificationObject | current-setting` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set the informative text of a notification                                                                                         |
| **Parameters**                                       | <ul><li>informativeText - An optional string containing the informative text to be set on the notification object. This can be an empty string. If `nil` is passed, any existing informative text will be removed.  If no parameter is provided, then the current setting is returned.</li></ul> |
| **Returns**                                          | <ul><li>The notification object, if informativeText is present; otherwise the current setting.</li></ul>          |

#### [otherButtonTitle](#otherbuttontitle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.notify:otherButtonTitle([buttonTitle]) -> notificationObject | current-setting` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set the label of a notification's other button                                                                                         |
| **Parameters**                                       | <ul><li>buttonTitle - An optional string containing the title for the notification's other button.  If no parameter is provided, then the current setting is returned.</li></ul> |
| **Returns**                                          | <ul><li>The notification object, if buttonTitle is present; otherwise the current setting.</li></ul>          |
| **Notes**                                            | <ul><li>The affects of this method only apply if the user has set Hammerspoon notifications to `Alert` in the Notification Center pane of System Preferences</li><li>Due to OSX limitations, it is NOT possible to get a callback for this button.</li></ul>                |

#### [presented](#presented)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.notify:presented() -> bool` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns whether the users Notification Center decided to display the notification                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A boolean indicating whether the users Notification Center decided to display the notification</li></ul>          |
| **Notes**                                            | <ul><li>Examples of why the users Notification Center would choose not to display a notification would be if Hammerspoon is the currently focussed application, being attached to a projector, or the user having set Do Not Disturb.</li></ul>                |

#### [release](#release)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.notify:release() -> notificationObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | This is a no-op included for backwards compatibility.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The notification object</li></ul>          |
| **Notes**                                            | <ul><li>This is no longer required during garbage collection as function tags can be re-established after a reload.</li><li>The proper way to release a notifications callback is to remove its tag from the `hs.notify.registry` with `hs.notify.unregister`.</li><li>This is included for backwards compatibility.</li></ul>                |

#### [schedule](#schedule)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.notify:schedule(date) -> notificationObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Schedules a notification for delivery in the future.                                                                                         |
| **Parameters**                                       | <ul><li>date - the date the notification should be delivered to the users Notification Center specified as the number of seconds since 1970-01-01 00:00:00Z or as a string in rfc3339 format: "YYYY-MM-DD[T]HH:MM:SS[Z]".</li></ul> |
| **Returns**                                          | <ul><li>The notification object</li></ul>          |
| **Notes**                                            | <ul><li>See also hs.notify:send()</li><li>hs.settings.dateFormat specifies a lua format string which can be used with `os.date()` to properly present the date and time as a string for use with this method.</li></ul>                |

#### [send](#send)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.notify:send() -> notificationObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Delivers the notification immediately to the users Notification Center.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The notification object</li></ul>          |
| **Notes**                                            | <ul><li>See also hs.notify:schedule()</li><li>If a notification has been modified, then this will resend it.</li><li>You can invoke this multiple times if you wish to repeat the same notification.</li></ul>                |

#### [setIdImage](#setidimage)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.notify:setIdImage(image[, withBorder]) -> notificationObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Set a notification's identification image (replace the Hammerspoon icon with a custom image)                                                                                         |
| **Parameters**                                       | <ul><li>image - An `hs.image` object, a string containing an image path, or a string defining an ASCIImage</li><li>withBorder - An optional boolean to give the notification image a border. Defaults to `false`</li></ul> |
| **Returns**                                          | <ul><li>The notification object</li></ul>          |
| **Notes**                                            | <ul><li>See hs.image for details on how to specify or define an image</li><li>**WARNING**: This method uses a private API. It could break at any time. Please file an issue if it does</li></ul>                |

#### [soundName](#soundname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.notify:soundName([soundName]) -> notificationObject | current-setting` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set the sound for a notification                                                                                         |
| **Parameters**                                       | <ul><li>soundName - An optional string containing the name of a sound to play with the notification. If `nil`, no sound will be played. Defaults to `nil`.  If no parameter is provided, then the current setting is returned.</li></ul> |
| **Returns**                                          | <ul><li>The notification object, if soundName is present; otherwise the current setting.</li></ul>          |
| **Notes**                                            | <ul><li>Sounds will first be matched against the names of system sounds. If no matches can be found, they will then be searched for in the following paths, in order:</li><li> `~/Library/Sounds`</li><li> `/Library/Sounds`</li><li> `/Network/Sounds`</li><li> `/System/Library/Sounds`</li></ul>                |

#### [subTitle](#subtitle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.notify:subTitle([subtitleText]) -> notificationObject | current-setting` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set the subtitle of a notification                                                                                         |
| **Parameters**                                       | <ul><li>subtitleText - An optional string containing the subtitle to be set on the notification object. This can be an empty string. If `nil` is passed, any existing subtitle will be removed.  If no parameter is provided, then the current setting is returned.</li></ul> |
| **Returns**                                          | <ul><li>The notification object, if subtitleText is present; otherwise the current setting.</li></ul>          |

#### [title](#title)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.notify:title([titleText]) -> notificationObject | current-setting` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Get or set the title of a notification                                                                                         |
| **Parameters**                                       | <ul><li>titleText - An optional string containing the title to be set on the notification object.  The default value is "Notification".  If `nil` is passed, then the title is set to the empty string.  If no parameter is provided, then the current setting is returned.</li></ul> |
| **Returns**                                          | <ul><li>The notification object, if titleText is present; otherwise the current setting.</li></ul>          |

#### [withdraw](#withdraw)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.notify:withdraw() -> notificationObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Withdraws a delivered notification from the Notification Center.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The notification object</li></ul>          |

