# [docs](index.md) » hs.messages
---

Send messages via iMessage and SMS Relay (note, SMS Relay requires OS X 10.10 and an established SMS Relay pairing between your Mac and an iPhone running iOS8)

Note: This extension works by controlling the OS X "Messages" app via AppleScript, so you will need that app to be signed into an iMessage account

## API Overview
* Functions - API calls offered directly by the extension
* [SMS](#SMS)
* [iMessage](#iMessage)

## API Documentation

### Functions

#### [SMS](#SMS)
| Signature   | hs.messages.SMS(targetNumber, message)  |
| Type        | Function |
| Description | Sends an SMS using SMS Relay |
| Parameters |  * targetNumber - A string containing a phone number to send an SMS to * message - A string containing the message to send | | Returns |  * None | 
#### [iMessage](#iMessage)
| Signature   | hs.messages.iMessage(targetAddress, message)  |
| Type        | Function |
| Description | Sends an iMessage |
| Parameters |  * targetAddress - A string containing a phone number or email address registered with iMessage, to send the iMessage to * message - A string containing the message to send | | Returns |  * None | 