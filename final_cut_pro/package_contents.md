This document is a random collection of notes, thoughts and comments as we start to experiment and play with the "insides" of Final Cut Pro.

***

## Frameworks

### Bloodhound

I'm not exactly sure what this is but I'm ASSUMING it has something to do with the more complex side of Apple Motion (possibly rendering?) - due to the following string found in the executable:

`PROGRAM:Bloodhound  PROJECT:Motion-29551.8.52`

I don't think this is much help to FCPX Hacks.

### CoreMedia

[Represent time-based audio-visual assets with essential data types.](https://developer.apple.com/reference/coremedia)

### CoreMediaIO

The [CoreMediaIO](https://developer.apple.com/library/content/samplecode/CoreMediaIO/Introduction/Intro.html#//apple_ref/doc/uid/DTS40012293-Intro-DontLinkElementID_2) Device Abstraction Layer (DAL) is analogous to CoreAudio’s Hardware Abstraction Layer (HAL). Just as the HAL deals with audio streams from audio hardware, the DAL handles video (and muxed) streams from video devices.

### Flexo

This seems to be one of the most important frameworks for iMovie & Final Cut Pro.

It contains:

* All the default `.audio.effectBundle` and `.effectBundle` files.
* The FCPX Document Type Definition's (version 1.0 to 1.6)
* Compressor settings for FCPX Bundles, Library XMLs and Project XMLs
* 72 Fonts used internally by Final Cut Pro & iMovie
* 3D Luts (`VLog_to_V709_forV35_ver100.3dlut` & `VLog_to_V2020_forV35_20160707.3dlut`)
* Files for `Trailers`, `Themes`, `Titles` and `Maps`
* Metadata Definitions (`DPPEditorialServices`, `DPPMedia` & `MXFMetadata`)
* Color Presets (in the `.cboard` format)
* [Nib files](https://developer.apple.com/library/content/documentation/Cocoa/Conceptual/LoadingResources/CocoaNibs/CocoaNibs.html) for a huge range of different Final Cut Pro & iMovie Windows & Modules.
* `FFLocalizable.strings` which contains a huge range of different UI strings for both iMovie and Final Cut Pro
* `ProMSRendererTool` seems to be both a video and audio rendering engine based on the `ProMSRendererLocalizable.strings` file.

It also contains the following Frameworks:

#### DeepSkyLite

This framework seems to be the database engine for Final Cut Pro?

#### FaceCoreEmbedded

FaceCore is Apple's Face Recognition framework, which was [acquired from Polar Rose](http://www.darkreading.com/risk-management/apple-to-acquire-polar-rose-face-recognition-firm/d/d-id/1092644?).

### FxPlug

[The FxPlug SDK is a compact yet powerful image processing plug-in architecture that lets you create new effects for Final Cut Pro and Motion. ](https://developer.apple.com/library/content/documentation/AppleApplications/Conceptual/FXPlug_overview/FXPlugSDKOverview/FXPlugSDKOverview.html)

### Helium

Helium looks like it's the video processing engine for Final Cut Pro, and other ProApps (i.e. there's references to Shake in some of the frameworks).

It looks like it's using [OpenGL's ARB Vertex](http://www.nvidia.com/docs/IO/8228/GDC2003_OGL_ARBVertexProgram.pdf) Programming language?

It contains two "Plug-ins":

- HCache
- HConverter

It contains several Frameworks:

#### HeliumFilters

Looks like it contains a bunch of OpenGL Shaders. Assuming it's a bunch of filters for Helium?

#### HeliumRender

Looks like it contains a bunch of OpenGL Shaders. Assuming it's the "render" engine for Helium?

#### HeliumSenso

Senso looks like the Optical Flow engine (possibly the same that originally came from Shake?).

#### HeliumSensoCore

Looks like more Optical Flow OpenGL functions.

#### HeliumSensoCore2

More Optical Flow code - but this looks less like OpenGL functions, and more like some kind of "interface"

### Lithium

Looks like another Framework for doing processing on the GPU using the [OpenGL Shading Language](https://en.wikipedia.org/wiki/OpenGL_Shading_Language). It has references to [Metal](https://developer.apple.com/metal/) as well. I'm ASSUMING that this the main Shader code.

Has two .glsl files inside:

- shadow.glsl
- ShadowBlurFragShader.glsl

### LunaKit

This looks like the Framework that contains all of the ProApps UI elements - from Windows, to Audio Meters, to Toolbars and the Browser.

It contains a bunch of `.car` (CoreUI Archives) files, which can be extracted using [Asset Catalog Tinkerer](https://github.com/insidegui/AssetCatalogTinkerer):

- **AppThemeBits.car:** contains LOTS of PSDs of UI elements.
- **AppThemeBitsB.car:** looks like a duplicate of `AppThemeBits.car`, but maybe at higher resolution (Retina version?)
- **Assets.car:** looks like it contains all of the mouse cursors.
- **NOX.car:** UI Elements such as Checkboxes, Buttons, Steppers, Text Fields, etc.
- **NOXConsumer.car**: Assuming it's the same as `NOX.car`, except for iMovie?
- **NOXHud_MOTION.car:** Assuming it's all the UI graphics for the HUD in Motion?
- **NOXHud.car:** UI graphics for Final Cut Pro's HUD?
- **NOXInspector.car:** - UI graphics for Final Cut Pro's Inspector?
- **NOXRevealed.car:** Not sure what these graphics are? Segmented Control?
- **NOXToken.car:** This bundle looks empty?
- **NOXToolbar.car**: Looks like it just has two loading animations?
- **NOXViewer.car** UI graphics for Final Cut Pro's Viewer?
- **WideSliderIconAppearance.car:** Not sure what these graphics are for?

It contains a human-readible plist file called `Container.moduleLayout`.

It contains a bunch of other interesting plain-text plist files:

- **LKColor.plist:** Colour settings for a huge range of different UI elements (for things like HUDs, etc.)
- **LKCursor.plist:** Hotspot Locations for various mouse cursors.
- **SRColor.plist:** Colour settings for a huge range of different UI elements (for things like Audio Waveforms, etc.)
- **SRCursor.plist:** Hotspot Locations for various mouse cursors.
- **TLKColor.plist:** Colour settings for various timeline elements.

It also contains a Perl script called `viddiagnose.pl`. I'm ASSUMING this is a script that creates Diagnostic reports for Apple to help debug FCPX?

There are also localised files in LOTS of different languages. In the `English.lproj` folder for example, it contains:

- **Commands.strings:** A binary plist of Command Editor strings.
- Several `.nib` files for what looks like the Command Editor?
- **LKLocalizable.strings:** Binary plist which contains a few basic strings for when you trash Final Cut Pro's preferences, and copyright messages.
- **LunaKit.strings**: Binary plist containing a list of colours (probably for the Command Editor).
- **ModuleKit.strings:** Binary plist containing text for Window Layouts.
- **NSProCommandDescriptions.strings:** Binary plist containing a single key (`ChangeWindowLayout`).
- **NSProCommandNames.strings:** Binary plist containing a single key (`ChangeWindowLayout`).

### MediaToolbox

[Contains interfaces for playing video and audio content.](https://developer.apple.com/library/content/releasenotes/General/APIDiffsMacOSX10_10_3/modules/MediaToolbox.html)

### MIO

Not sure what MIO stands for (maybe MediaIO or [CoreMediaIO](https://developer.apple.com/library/content/samplecode/CoreMediaIO/Introduction/Intro.html#//apple_ref/doc/uid/DTS40012293-Intro-DontLinkElementID_2)?) but seems to be something to do with the reading and processing of video & audio files. Possibly also has something to do with the controlling of FireWire DV devices?

### Ozone

TBC

### PluginManager

TBC

### ProAppsFxSupport

TBC

### ProChannel

TBC

### ProCore

TBC

### ProCurveEditor

TBC

### ProGL

TBC

### ProGraphics

TBC

### ProInspector

TBC

### ProKit

TBC

### ProMedia

TBC

### ProOSC

TBC

### ProShapes

TBC

### RetimingMath

TBC

### Stalgo

TBC

### StudioSharedResources

TBC

### TextFramework

TBC

### TLKEventDispatcher

TBC

### TLKit

TBC

### VideoToolbox

TBC