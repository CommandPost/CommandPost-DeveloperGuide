# [docs](index.md) » cp.apple.fcpxml.title
---

FCPXML Document Title Object.

This extension was inspired and uses code based on [Pipeline](https://github.com/reuelk/pipeline).
Thank you Reuel Kim for making something truly awesome, and releasing it as Open Source!

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)

## API Documentation

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml.title.new(titleName, lane, offset, ref, duration, start, role, titleText, textStyleID, newTextStyle, newTextStyleAttributes) -> fcpxmlTitle Object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new title to be used in a timeline. |
| **Parameters**                                       | <ul><li>titleName</li><li>lane</li><li>offset</li><li>ref</li><li>duration</li><li>start</li><li>role</li><li>titleText</li><li>textStyleID</li><li>newTextStyle</li><li>newTextStyleAttributes</li></ul> |
| **Returns**                                          | <ul><li>A new Title object.</li></ul> |
| **Notes**                                            | <ul><li><code>newTextStyleAttributes</code> is only used if <code>newTextStyle</code> is set to <code>true</code>.</li><li>When <code>newTextStyle</code> is set to <code>true</code>, the following atttributes can be used   within the <code>newTextStyleAttributes</code> table:<ul><li>font - The font name as string (defaults to "Helvetica").</li><li>fontSize - The font size a number (defaults to 62).</li><li>fontFace - The font face as a string (defaults to "Regular").</li><li>fontColor - The font color as a <code>hs.drawing.color</code> object (defaults to black).</li><li>strokeColor - The stroke color as a <code>hs.drawing.color</code> object (defaults to <code>nil</code>).</li><li>strokeWidth - The stroke width as a number (defaults to 2).</li><li>shadowColor - The stroke color as a <code>hs.drawing.color</code> object (defaults to <code>nil</code>).</li><li>shadowDistance - The shadow distance as a number (defaults to 5).</li><li>shadowAngle - The shadow angle as a number (defaults to 315).</li><li>shadowBlurRadius - The shadow blur radius as a number (defaults to 1).</li><li>alignment - The text alignment as a string (defaults to "center").</li><li>xPosition - The x position of the title (defaults to 0).</li><li>yPosition - The y position of the title (defaults to 0).</li></ul></li></ul> |

