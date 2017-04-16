# [docs](index.md) » cp.web.generate
---

Functions for Generating HTML UI Items

## API Overview
* Functions - API calls offered directly by the extension
 * [button](#button)
 * [checkbox](#checkbox)
 * [dropdown](#dropdown)
 * [heading](#heading)
 * [init](#init)
 * [setWebviewLabel](#setWebviewLabel)
 * [text](#text)

## API Documentation

### Functions

| [button](#button)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.web.generate.button() -> string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Generates a HTML Button                                                                     |
| **Parameters**                              | <ul><li>data - Table containing the data you want to display on the Checkbox</li><li>customTrigger - Custom label used for JavaScript Callback</li><li>customWidth - Number to set the width of the button to</li><li>customID - Overrides the random HTML ID</li></ul> |
| **Returns**                                 | <ul><li>String containing the HTML</li></ul>          |

| [checkbox](#checkbox)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.web.generate.checkbox() -> string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Generates a HTML Checkbox                                                                     |
| **Parameters**                              | <ul><li>data - Table containing the data you want to display on the Checkbox</li><li>customTrigger - Custom label used for JavaScript Callback</li><li>customID - Custom ID used for the HTML objects</li></ul> |
| **Returns**                                 | <ul><li>String containing the HTML</li></ul>          |

| [dropdown](#dropdown)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.web.generate.dropdown() -> string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Generates a HTML Dropdown                                                                     |
| **Parameters**                              | <ul><li>title - Title to put in front of the Dropdown. Can be "".</li><li>data - Table containing the data you want to display on the Checkbox</li><li>customTrigger - Custom label used for JavaScript Callback</li></ul> |
| **Returns**                                 | <ul><li>String containing the HTML</li></ul>          |

| [heading](#heading)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.web.generate.heading() -> string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Generates a HTML Heading                                                                     |
| **Parameters**                              | <ul><li>data - Table containing the data you want to display on the Checkbox</li></ul> |
| **Returns**                                 | <ul><li>String containing the HTML</li></ul>          |

| [init](#init)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.web.generate.init() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Initialises the module                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>Table containing the module</li></ul>          |

| [setWebviewLabel](#setWebviewLabel)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.web.generate.setWebviewLabel() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Sets the WebView Label                                                                     |
| **Parameters**                              | <ul><li>value - WebView Label as string</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |

| [text](#text)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.web.generate.text() -> string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Generates a blank HTML                                                                     |
| **Parameters**                              | <ul><li>data - Table containing the data you want to display.</li></ul> |
| **Returns**                                 | <ul><li>String containing the HTML</li></ul>          |

