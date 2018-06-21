# [docs](index.md) » hs.canvas.drawing
---

An wrapper to replace `hs.drawing` with `hs.canvas`.

The intention is for this wrapper to provide all of the same functionality that `hs.drawing` does without requiring any additional changes to your currently existing code.

### Known issues/differences between the wrapper and `hs.drawing`:

 * images which are "template images" (i.e. some of the images with names in `hs.image.systemImageNames` and any image retrieved from an `hs.menubar` object) are displayed with an implicit `imageAlpha` of 0.5.  This closely mimics the NSImageView behavior observed with `hs.drawing`, but since Apple has not provided full details on how a template image is rendered when it is *not* used as a template, this is just a guess.

 * image frames from `hs.drawing` are approximated with additional canvas elements inserted into the canvas; since this module now allows you to create as complex a frame as you like... consider these as "examples".

The wrapper is not enabled by default.  See the `hs.canvas.drawingWrapper` function for details on how to enable or disable this wrapper.

## API Overview
* Functions - API calls offered directly by the extension
 * [drawingWrapper](#drawingwrapper)

## API Documentation

### Functions

#### [drawingWrapper](#drawingwrapper)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.canvas.drawingWrapper([state]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Get or set whether or not `hs.drawing` is replaced by a wrapper which uses this module.                                                                                         |
| **Parameters**                                       | <ul markdown="1"><li markdown="1">`state` - an optional boolean specifying whether or not `hs.drawing` should be replaced with a wrapper using this module.</li></ul> |
| **Returns**                                          | <ul markdown="1"><li markdown="1">the current, possibly newly changed, state.</li></ul>          |
| **Notes**                                            | <ul markdown="1"><li markdown="1">This module was designed to address some of the limitations found with the `hs.drawing` module.  It is expected that at some point this module may completely replace the existing `hs.drawing` as it provides more flexibility and will be easier to extend with future additions. This function allows you to choose whether or not you wish to migrate fully to this new drawing model now to facilitate the testing of the wrapper or not.</li><li markdown="1">This wrapper was designed to fully mimic the current `hs.drawing` functions and methods -- you should not need to change your existing code in any way once this wrapper is enabled.  If you find that you do need to make adjustments or that something in the wrapper does not work as expected, please log an issue at https://github.com/Hammerspoon/hammerspoon/issues.</li></ul>                |

