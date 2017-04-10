# [docs](index.md) » hs.notify
---

This module allows you to create on screen notifications in the User Notification Center located at the right of the users screen.

Notifications can be sent immediately or scheduled for delivery at a later time, even if that scheduled time occurs when Hammerspoon is not currently running. Currently, if you take action on a notification while Hammerspoon is not running, the callback function is not honored for the first notification clicked upon -- This is expected to be fixed in a future release.

When setting up a callback function, you have the option of specifying it with the creation of the notification (hs.notify.new) or by pre-registering it with hs.notify.register and then referring it to by the tag name specified with hs.notify.register. If you use this registration method for defining your callback functions, and make sure to register all expected callback functions within your init.lua file or files it includes, then callback functions will remain available for existing notifications in the User Notification Center even if Hammerspoon's configuration is reloaded or if Hammerspoon is restarted. If the callback tag is not present when the user acts on the notification, the Hammerspoon console will be raised as a default action.

A shorthand, based upon the original inspiration for this module from Hydra and Mjolnir, hs.notify.show, is provided if you just require a quick and simple informative notification without the bells and whistles.

This module is based in part on code from the previous incarnation of Mjolnir by [Steven Degutis](https://github.com/sdegutis/).

## API Overview
* Constants - Useful values which cannot be changed
 * [activationTypes[]](#activationTypes[])
 * [defaultNotificationSound](#defaultNotificationSound)
* Variables - Configurable values
 * [registry[]](#registry[])
 * [warnAboutMissingFunctionTag](#warnAboutMissingFunctionTag)
* Functions - API calls offered directly by the extension
 * [register](#register)
 * [unregister](#unregister)
 * [unregisterall](#unregisterall)
 * [withdrawAll](#withdrawAll)
 * [withdrawAllScheduled](#withdrawAllScheduled)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
 * [show](#show)
* Methods - API calls which can only be made on an object returned by a constructor
 * [actionButtonTitle](#actionButtonTitle)
 * [activationType](#activationType)
 * [actualDeliveryDate](#actualDeliveryDate)
 * [alwaysPresent](#alwaysPresent)
 * [autoWithdraw](#autoWithdraw)
 * [contentImage](#contentImage)
 * [delivered](#delivered)
 * [getFunctionTag](#getFunctionTag)
 * [hasActionButton](#hasActionButton)
 * [informativeText](#informativeText)
 * [otherButtonTitle](#otherButtonTitle)
 * [presented](#presented)
 * [release](#release)
 * [schedule](#schedule)
 * [send](#send)
 * [setIdImage](#setIdImage)
 * [soundName](#soundName)
 * [subTitle](#subTitle)
 * [title](#title)
 * [withdraw](#withdraw)

## API Documentation
### Constants

#### [activationTypes[]](#activationTypes[])
|             |                 |
| ------------|-----------------|
| Signature   | hs.notify.activationTypes[]  |
| Type        | Constant |
| Description | Convenience array of the possible activation types for a notification, and their reverse for reference. |
| Notes |  * Count starts at zero. (implemented in Objective-C)

#### [defaultNotificationSound](#defaultNotificationSound)
|             |                 |
| ------------|-----------------|
| Signature   | hs.notify.defaultNotificationSound  |
| Type        | Constant |
| Description | The string representation of the default notification sound. Use `hs.notify:soundName()` or set the `soundName` attribute in `hs:notify.new()`, to this constant, if you want to use the default sound |
 |

### Variables

#### [registry[]](#registry[])
|             |                 |
| ------------|-----------------|
| Signature   | hs.notify.registry[]  |
| Type        | Variable |
| Description | A table containing the registered callback functions and their tags. |
| Notes |  * This table should not be modified directly. Use the `hs.notify.register(tag, fn)` and `hs.notify.unregister(id)` functions. * This table has a __tostring metamethod so you can see the list of registered function tags in the console by typing `hs.notify.registry` * If a notification attempts to perform a callback to a function tag which is not present in this table, a warning will be printed in the console.

#### [warnAboutMissingFunctionTag](#warnAboutMissingFunctionTag)
|             |                 |
| ------------|-----------------|
| Signature   | hs.notify.warnAboutMissingFunctionTag  |
| Type        | Variable |
| Description | A boolean value indicating whether or not a missing notification function tag should cause a warning to be printed to the console during activation callback. Defaults to true. |
 |

### Functions

#### [register](#register)
|             |                 |
| ------------|-----------------|
| Signature   | hs.notify.register(tag, fn) -> id  |
| Type        | Function |
| Description | Registers a function callback with the specified tag for a notification. The callback function will be invoked when the user clicks on or interacts with a notification. |
| Parameters |  * tag - a string tag to identify the registered callback function. Use this as the function tag in `hs.notify.new` and `hs.notify.show` * fn  - the function which should be invoked when a notification with this tag is interacted with. |
| Returns |  * a numerical id representing the entry in `hs.notify.registry` for this function. This number can be used with `hs.notify.unregister` to unregister a function later if you wish. |
| Notes |  * If a function is already registered with the specified tag, it is replaced by with the new one.

#### [unregister](#unregister)
|             |                 |
| ------------|-----------------|
| Signature   | hs.notify.unregister(id|tag)  |
| Type        | Function |
| Description | Unregisters a function callback so that it is no longer available as a callback when notifications corresponding to the specified entry are interacted with. |
| Parameters |  * id or tag - the numerical id provided by `hs.notify.register` or string tag representing the callback function to be removed |
| Returns |  * None |


#### [unregisterall](#unregisterall)
|             |                 |
| ------------|-----------------|
| Signature   | hs.notify.unregisterall()  |
| Type        | Function |
| Description | Unregisters all functions registered as callbacks. |
| Parameters |  * None |
| Returns |  * None |
| Notes |  * This does not remove the notifications from the User Notification Center, it just removes their callback function for when the user interacts with them. To remove all notifications, see `hs.notify.withdrawAll` and `hs.notify.withdrawAllScheduled`

#### [withdrawAll](#withdrawAll)
|             |                 |
| ------------|-----------------|
| Signature   | hs.notify.withdrawAll()  |
| Type        | Function |
| Description | Withdraw all delivered notifications from Hammerspoon |
| Parameters |  * None |
| Returns |  * None |
| Notes |  * This will withdraw all notifications for Hammerspoon, including those not sent by this module or that linger from a previous load of Hammerspoon.

#### [withdrawAllScheduled](#withdrawAllScheduled)
|             |                 |
| ------------|-----------------|
| Signature   | hs.notify.withdrawAllScheduled()  |
| Type        | Function |
| Description | Withdraw all scheduled notifications from Hammerspoon |
| Parameters |  * None |
| Returns |  * None |
 |

### Constructors

#### [new](#new)
|             |                 |
| ------------|-----------------|
| Signature   | hs.notify.new([fn,][attributes]) -> notification  |
| Type        | Constructor |
| Description | Creates a new notification object |
| Parameters |  * fn - An optional function or function-tag, which will be called when the user interacts with notifications. The notification object will be passed as an argument to the function. If you leave this parameter out or specify nil, then no callback will be attached to the notification. * attributes - An optional table for applying attributes to the notification. Possible keys are: |
| Returns |  * A notification object |
| Notes |  * A function-tag is a string key which corresponds to a function stored in the `hs.notify.registry` table with the `hs.notify.register()` function. * If a notification does not have a `title` attribute set, OS X will not display it, so by default it will be set to "Notification". You can use the `title` key in the attributes table, or call `hs.notify:title()` before displaying the notification to change this.

#### [show](#show)
|             |                 |
| ------------|-----------------|
| Signature   | hs.notify.show(title, subTitle, information[, tag]) -> notfication  |
| Type        | Constructor |
| Description | Shorthand constructor to create and show simple notifications |
| Parameters |  * title       - the title for the notification * subTitle    - the subtitle, or second line, of the notification * information - the main textual body of the notification * tag         - a function tag corresponding to a function registered with `hs.notify.register` |
| Returns |  * a notification object |
| Notes |  * All three textual parameters are required, though they can be empty strings * This function is really a shorthand for `hs.notify.new(...):send()` |

### Methods

#### [actionButtonTitle](#actionButtonTitle)
|             |                 |
| ------------|-----------------|
| Signature   | hs.notify:actionButtonTitle([buttonTitle]) -> notificationObject | current-setting  |
| Type        | Method |
| Description | Get or set the label of a notification's action button |
| Parameters |  * buttonTitle - An optional string containing the title for the notification's action button.  If no parameter is provided, then the current setting is returned. |
| Returns |  * The notification object, if buttonTitle is present; otherwise the current setting. |
| Notes |  * The affects of this method only apply if the user has set Hammerspoon notifications to `Alert` in the Notification Center pane of System Preferences

#### [activationType](#activationType)
|             |                 |
| ------------|-----------------|
| Signature   | hs.notify:activationType() -> number  |
| Type        | Method |
| Description | Returns how the notification was activated by the user. |
| Parameters |  * None |
| Returns |  * the integer value corresponding to how the notification was activated by the user.  See the table `hs.notify.activationTypes[]` for more information. |


#### [actualDeliveryDate](#actualDeliveryDate)
|             |                 |
| ------------|-----------------|
| Signature   | hs.notify:actualDeliveryDate() -> number  |
| Type        | Method |
| Description | Returns the date and time when a notification was delivered |
| Parameters |  * None |
| Returns |  * A number containing the delivery date/time of the notification, in seconds since the epoch (i.e. 1970-01-01 00:00:00 +0000) |
| Notes |  * You can turn epoch times into a human readable string or a table of date elements with the `os.date()` function.

#### [alwaysPresent](#alwaysPresent)
|             |                 |
| ------------|-----------------|
| Signature   | hs.notify:alwaysPresent([alwaysPresent]) -> notificationObject | current-setting  |
| Type        | Method |
| Description | Get or set whether a notification should be presented even if this overrides Notification Center's decision process. |
| Parameters |  * alwaysPresent - An optional boolean parameter indicating whether the notification should override Notification Center's decision about whether to present the notification or not. Defaults to true.  If no parameter is provided, then the current setting is returned. |
| Returns |  * The notification object, if alwaysPresent is provided; otherwise the current setting. |
| Notes |  * This does not affect the return value of `hs.notify:presented()` -- that will still reflect the decision of the Notification Center * Examples of why the users Notification Center would choose not to display a notification would be if Hammerspoon is the currently focussed application, being attached to a projector, or the user having set Do Not Disturb.

#### [autoWithdraw](#autoWithdraw)
|             |                 |
| ------------|-----------------|
| Signature   | hs.notify:autoWithdraw([shouldWithdraw]) -> notificationObject | current-setting  |
| Type        | Method |
| Description | Get or set whether a notification should automatically withdraw once activated |
| Parameters |  * shouldWithdraw - An optional boolean indicating whether the notification should automatically withdraw. Defaults to true.  If no parameter is provided, then the current setting is returned. |
| Returns |  * The notification object, if shouldWithdraw is present; otherwise the current setting. |


#### [contentImage](#contentImage)
|             |                 |
| ------------|-----------------|
| Signature   | hs.notify:contentImage([image]) -> notificationObject | current-setting  |
| Type        | Method |
| Description | Get or set a notification's content image. |
| Parameters |  * image - An optional hs.image parameter containing the image to display. Defaults to nil. If no parameter is provided, then the current setting is returned. |
| Returns |  * The notification object, if image is provided; otherwise the current setting. |
| Notes |  * See hs.image for details on how to specify or define an image * This method is only supported in OS X 10.9 or greater. A warning will be displayed in the console and the method will be treated as a no-op if used on an unsupported system.

#### [delivered](#delivered)
|             |                 |
| ------------|-----------------|
| Signature   | hs.notify:delivered() -> bool  |
| Type        | Method |
| Description | Returns whether the notification has been delivered to the Notification Center |
| Parameters |  * None |
| Returns |  * A boolean indicating whether the notification has been delivered to the users Notification Center |


#### [getFunctionTag](#getFunctionTag)
|             |                 |
| ------------|-----------------|
| Signature   | hs.notify:getFunctionTag() -> functiontag  |
| Type        | Method |
| Description | Return the name of the function tag the notification will call when activated. |
| Parameters |  * None |
| Returns |  * The function tag for this notification as a string. |
| Notes |  * This tag should correspond to a function in `hs.notify.registry` and can be used to either add a replacement with `hs.notify.register(...)` or remove it with `hs.notify.unregister(...)`

#### [hasActionButton](#hasActionButton)
|             |                 |
| ------------|-----------------|
| Signature   | hs.notify:hasActionButton([hasButton]) -> notificationObject | current-setting  |
| Type        | Method |
| Description | Get or set the presence of an action button in a notification |
| Parameters |  * hasButton - An optional boolean indicating whether an action button should be present.  If no parameter is provided, then the current setting is returned. |
| Returns |  * The notification object, if hasButton is present; otherwise the current setting. |
| Notes |  * The affects of this method only apply if the user has set Hammerspoon notifications to `Alert` in the Notification Center pane of System Preferences

#### [informativeText](#informativeText)
|             |                 |
| ------------|-----------------|
| Signature   | hs.notify:informativeText([informativeText]) -> notificationObject | current-setting  |
| Type        | Method |
| Description | Get or set the informative text of a notification |
| Parameters |  * informativeText - An optional string containing the informative text to be set on the notification object. This can be an empty string. If `nil` is passed, any existing informative text will be removed.  If no parameter is provided, then the current setting is returned. |
| Returns |  * The notification object, if informativeText is present; otherwise the current setting. |


#### [otherButtonTitle](#otherButtonTitle)
|             |                 |
| ------------|-----------------|
| Signature   | hs.notify:otherButtonTitle([buttonTitle]) -> notificationObject | current-setting  |
| Type        | Method |
| Description | Get or set the label of a notification's other button |
| Parameters |  * buttonTitle - An optional string containing the title for the notification's other button.  If no parameter is provided, then the current setting is returned. |
| Returns |  * The notification object, if buttonTitle is present; otherwise the current setting. |
| Notes |  * The affects of this method only apply if the user has set Hammerspoon notifications to `Alert` in the Notification Center pane of System Preferences * Due to OSX limitations, it is NOT possible to get a callback for this button.

#### [presented](#presented)
|             |                 |
| ------------|-----------------|
| Signature   | hs.notify:presented() -> bool  |
| Type        | Method |
| Description | Returns whether the users Notification Center decided to display the notification |
| Parameters |  * None |
| Returns |  * A boolean indicating whether the users Notification Center decided to display the notification |
| Notes |  * Examples of why the users Notification Center would choose not to display a notification would be if Hammerspoon is the currently focussed application, being attached to a projector, or the user having set Do Not Disturb.

#### [release](#release)
|             |                 |
| ------------|-----------------|
| Signature   | hs.notify:release() -> notificationObject  |
| Type        | Method |
| Description | This is a no-op included for backwards compatibility. |
| Parameters |  * None |
| Returns |  * The notification object |
| Notes |  * This is no longer required during garbage collection as function tags can be re-established after a reload. * The proper way to release a notifications callback is to remove its tag from the `hs.notify.registry` with `hs.notify.unregister`. * This is included for backwards compatibility.

#### [schedule](#schedule)
|             |                 |
| ------------|-----------------|
| Signature   | hs.notify:schedule(date) -> notificationObject  |
| Type        | Method |
| Description | Schedules a notification for delivery in the future. |
| Parameters |  * date - the date the notification should be delivered to the users Notification Center specified as the number of seconds since 1970-01-01 00:00:00Z or as a string in rfc3339 format: "YYYY-MM-DD[T]HH:MM:SS[Z]". |
| Returns |  * The notification object |
| Notes |  * See also hs.notify:send() * hs.settings.dateFormat specifies a lua format string which can be used with `os.date()` to properly present the date and time as a string for use with this method.

#### [send](#send)
|             |                 |
| ------------|-----------------|
| Signature   | hs.notify:send() -> notificationObject  |
| Type        | Method |
| Description | Delivers the notification immediately to the users Notification Center. |
| Parameters |  * None |
| Returns |  * The notification object |
| Notes |  * See also hs.notify:schedule() * If a notification has been modified, then this will resend it. * You can invoke this multiple times if you wish to repeat the same notification.

#### [setIdImage](#setIdImage)
|             |                 |
| ------------|-----------------|
| Signature   | hs.notify:setIdImage(image[, withBorder]) -> notificationObject  |
| Type        | Method |
| Description | Set a notification's identification image (replace the Hammerspoon icon with a custom image) |
| Parameters |  * image - An `hs.image` object, a string containing an image path, or a string defining an ASCIImage * withBorder - An optional boolean to give the notification image a border. Defaults to `false` |
| Returns |  * The notification object |
| Notes |  * See hs.image for details on how to specify or define an image * **WARNING**: This method uses a private API. It could break at any time. Please file an issue if it does

#### [soundName](#soundName)
|             |                 |
| ------------|-----------------|
| Signature   | hs.notify:soundName([soundName]) -> notificationObject | current-setting  |
| Type        | Method |
| Description | Get or set the sound for a notification |
| Parameters |  * soundName - An optional string containing the name of a sound to play with the notification. If `nil`, no sound will be played. Defaults to `nil`.  If no parameter is provided, then the current setting is returned. |
| Returns |  * The notification object, if soundName is present; otherwise the current setting. |
| Notes |  * Sounds will first be matched against the names of system sounds. If no matches can be found, they will then be searched for in the following paths, in order:  * `~/Library/Sounds`  * `/Library/Sounds`  * `/Network/Sounds`  * `/System/Library/Sounds`

#### [subTitle](#subTitle)
|             |                 |
| ------------|-----------------|
| Signature   | hs.notify:subTitle([subtitleText]) -> notificationObject | current-setting  |
| Type        | Method |
| Description | Get or set the subtitle of a notification |
| Parameters |  * subtitleText - An optional string containing the subtitle to be set on the notification object. This can be an empty string. If `nil` is passed, any existing subtitle will be removed.  If no parameter is provided, then the current setting is returned. |
| Returns |  * The notification object, if subtitleText is present; otherwise the current setting. |


#### [title](#title)
|             |                 |
| ------------|-----------------|
| Signature   | hs.notify:title([titleText]) -> notificationObject | current-setting  |
| Type        | Method |
| Description | Get or set the title of a notification |
| Parameters |  * titleText - An optional string containing the title to be set on the notification object.  The default value is "Notification".  If `nil` is passed, then the title is set to the empty string.  If no parameter is provided, then the current setting is returned. |
| Returns |  * The notification object, if titleText is present; otherwise the current setting. |


#### [withdraw](#withdraw)
|             |                 |
| ------------|-----------------|
| Signature   | hs.notify:withdraw() -> notificationObject  |
| Type        | Method |
| Description | Withdraws a delivered notification from the Notification Center. |
| Parameters |  * None |
| Returns |  * The notification object |
 |
