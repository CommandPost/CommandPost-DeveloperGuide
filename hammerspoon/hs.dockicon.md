# Hammerspoon docs: hs.dockicon

Control Hammerspoon's dock icon

This module is based primarily on code from the previous incarnation of Mjolnir by [Steven Degutis](https://github.com/sdegutis/).

## API Overview
* Functions - API calls offered directly by the extension</li>
  * bounce
  * hide
  * setBadge
  * show
  * visible

## API Documentation

### Functions

#### bounce
  * Signature: hs.dockicon.bounce(indefinitely)
  * Type: Function
  * Description: Bounce Hammerspoon's dock icon
  * Parameters:
     * indefinitely - A boolean value, true if the dock icon should bounce until the dock icon is clicked, false if the dock icon should only bounce briefly

#### hide
  * Signature: hs.dockicon.hide()
  * Type: Function
  * Description: Hide Hammerspoon's dock icon
  * Parameters:
     * None
  * Returns:
     * None

#### setBadge
  * Signature: hs.dockicon.setBadge(badge)
  * Type: Function
  * Description: Set Hammerspoon's dock icon badge
  * Parameters:
     * badge - A string containing the label to place inside the dock icon badge. If the string is empty, the badge will be cleared

#### show
  * Signature: hs.dockicon.show()
  * Type: Function
  * Description: Make Hammerspoon's dock icon visible
  * Parameters:
     * None
  * Returns:
     * None

#### visible
  * Signature: hs.dockicon.visible() -> bool
  * Type: Function
  * Description: Determine whether Hammerspoon's dock icon is visible
  * Parameters:
     * None
  * Returns:
     * A boolean, true if the dock icon is visible, false if not
