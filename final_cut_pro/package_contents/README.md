# Final Cut Pro Package Contents
---

This document is a random collection of notes, thoughts and comments as we start to research the "inside workings" of Apple's Final Cut Pro package.

To get an overview of how Final Cut Pro works, it's worth checking out the original parent as a [PDF with images](http://pimg-fpiw.uspto.gov/fdd/25/750/088/0.pdf) or as [searchable plain text](http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO1&Sect2=HITOFF&d=PALL&p=1&u=%2Fnetahtml%2FPTO%2Fsrchnum.htm&r=1&f=G&l=50&s1=8,875,025.PN.&OS=PN/8,875,025&RS=PN/8,875,025).

Here's one of the screenshots from the patent:

![Patent Screenshot](https://dev.commandpost.io/images/patent.png)

---

## Handy Tools

Here are some handy "research" tools we use to explore Final Cut Pro:

- [Hopper Disassembler](https://www.hopperapp.com)
- [NibDecompiler](https://github.com/akahan/Nib-Decompiler)
- [Asset Catalog Tinkerer](https://github.com/insidegui/AssetCatalogTinkerer)

---

## Plugins

Internally, Final Cut Pro supports and contains a number of different plugin types and formats:

---

### Compressor

Contains `CompressorKit.bundle` - which can also be found in Compressor and Motion - it's basically the Compressor engine.

---

### FCP-DAL

Contains `ACD.plugin` - some kind of CoreMediaIO plugin - not exactly sure what it does.

The CoreMediaIO Device Abstraction Layer (DAL) is analogous to CoreAudio’s Hardware Abstraction Layer (HAL). Just as the HAL deals with audio streams from audio hardware, the DAL handles video (and muxed) streams from video devices.

You can download sample DAL code [here](https://developer.apple.com/library/content/samplecode/CoreMediaIO/Introduction/Intro.html).

---

### FxPlug

[The FxPlug SDK is a compact yet powerful image processing plug-in architecture that lets you create new effects for Final Cut Pro and Motion. ](https://developer.apple.com/library/content/documentation/AppleApplications/Conceptual/FXPlug_overview/FXPlugSDKOverview/FXPlugSDKOverview.html)

This folder contains two plugins:
- `FiltersLegacyPath.bundle` - I believe this contains older Filters (such as the Primatte keyer) still used by Motion & Final Cut Pro.
- `PAECIAdaptor.fxplug` - I have no idea what a PAECI is, or what this FxPlug does.

---

### InternalFiltersXPC.pluginkit

Internal filters used by Final Cut Pro & Motion.

---

### MediaProviders

`MotionEffect.fxp` - Contains Motion Particle Images, Materials and Text Styles.

---

### RADPlugins

Plugins for 3rd Party codecs:

- `Archive.RADPlug`
- `AVCHD.RADPlug`
- `MPEG2.RADPlug`
- `MPEG4.RADPlug`
- `P2.RADPlug`
- `P2AVF.RADPlug`
- `XDCAM.RADPlug`
- `XDCAMFormat.RADPlug`

---

## Frameworks

---

### Bloodhound

I'm not exactly sure what this is but I'm ASSUMING it has something to do with the more complex side of Apple Motion (possibly rendering?) - due to the following string found in the executable:

`PROGRAM:Bloodhound  PROJECT:Motion-29551.8.52`

I don't think this is much help to CommandPost.

---

### CoreMedia

[Represent time-based audio-visual assets with essential data types.](https://developer.apple.com/reference/coremedia)

---

### CoreMediaIO

The [CoreMediaIO](https://developer.apple.com/library/content/samplecode/CoreMediaIO/Introduction/Intro.html#//apple_ref/doc/uid/DTS40012293-Intro-DontLinkElementID_2) Device Abstraction Layer (DAL) is analogous to CoreAudio’s Hardware Abstraction Layer (HAL). Just as the HAL deals with audio streams from audio hardware, the DAL handles video (and muxed) streams from video devices.

---

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

---

### FxPlug

[The FxPlug SDK is a compact yet powerful image processing plug-in architecture that lets you create new effects for Final Cut Pro and Motion. ](https://developer.apple.com/library/content/documentation/AppleApplications/Conceptual/FXPlug_overview/FXPlugSDKOverview/FXPlugSDKOverview.html)

---

### Helium

Helium looks like it's the video processing engine for Final Cut Pro, and other ProApps (i.e. there's references to Shake in some of the frameworks).

It looks like it's using [OpenGL's ARB Vertex](http://www.nvidia.com/docs/IO/8228/GDC2003_OGL_ARBVertexProgram.pdf) Programming language?

It contains two "Plug-ins":

- `HCache`
- `HConverter`

It contains several internal Frameworks:

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

---

### Lithium

Looks like another Framework for doing processing on the GPU using the [OpenGL Shading Language](https://en.wikipedia.org/wiki/OpenGL_Shading_Language). It has references to [Metal](https://developer.apple.com/metal/) as well. I'm ASSUMING that this the main Shader code.

Has two .glsl files inside:

- `shadow.glsl`
- `ShadowBlurFragShader.glsl`

---

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

---

### MediaToolbox

[Contains interfaces for playing video and audio content.](https://developer.apple.com/library/content/releasenotes/General/APIDiffsMacOSX10_10_3/modules/MediaToolbox.html)

---

### MIO

Not sure what MIO stands for (maybe MediaIO or [CoreMediaIO](https://developer.apple.com/library/content/samplecode/CoreMediaIO/Introduction/Intro.html#//apple_ref/doc/uid/DTS40012293-Intro-DontLinkElementID_2)?) but seems to be something to do with the reading and processing of video & audio files. Possibly also has something to do with the controlling of FireWire DV devices?

---

### Ozone

Ozone looks like it's the Apple Motion render engine. This Framework is identical in both Final Cut Pro & Motion.

This framework is quite big in terms of file size as it contains things like Environment Map's and Physical Layer Assets (all in OpenEXR format).

It contains one internal Framework:

#### AudioMixEngine

As the name suggests, this looks like a Framework that handles audio mixing.

It also contains several internal Plugins:

- `Behaviors.ozp`
- `Navigator.ozp`
- `Particles.ozp`
- `Text.ozp`

---

### PluginManager

As the name suggests, this looks like the Plugin Manager for Final Cut Pro.

Interestingly, it contains a property list file called `6B9D8D3C-D3BF-4276-828F-2212D24B11CE.plist` which contains a list of 3rd party plugins that can only run certain versions of the plugin on certain versions of Final Cut Pro.

---

### ProAppsFxSupport

I'm not exactly sure what this Framework is, but given it contains a whole bunch of files such as:

- `BlueNoise1.tiff`, `BlueNoise2.tiff`, `BlueNoise3.tiff`
- `GaussianNoise1.tiff`, `GaussianNoise2.tiff`, `GaussianNoise3.tiff`
- `PinkNoise1.tiff`, `PinkNoise2.tiff`, `PinkNoise3.tiff`
- `TVStatic1.tiff`, `TVStatic2.tiff`, `TVStatic3.tiff`
- `WhiteNoise1.tiff`, `WhiteNoise2.tiff`, `WhiteNoise3.tiff`

...and the fact it's called "ProAppsFxSupport", one can only assume it's a support library for some of the internal effects Apple's ProApp's take advantage of.

This Framework also exists in Motion.

---

### ProChannel

A shared Framework between Motion & Final Cut Pro, I assume this is something to do with colour processing.

---

### ProCore

Another shared Framework between Motion & Final Cut Pro, I believe this Framework also has to do with colour processing - such as blend modes, and colour space conversion.

---

### ProCurveEditor

I believe this Framework contains the Curve Editor used by Apple Motion.

---

### ProGL

The Framework that handles the OpenGL processing. I believe this creates an [`NSOpenGLContext`](https://developer.apple.com/documentation/appkit/nsopenglcontext) (i.e. an object that represents an OpenGL graphics context, into which all OpenGL calls are rendered).

---

### ProGraphics

A shared Framework between Motion & Final Cut Pro, I assume this is something to do with graphics processing.

---

### ProInspector

The Inspector UI used by Motion.

---

### ProMedia

This Framework looks like it handles support for things like RAW images and OpenEXR. It looks like it uses Metal 1.0.

---

### ProOSC

This looks like Motion's Framework for handling On-screen Controls.

It looks like it's doing processing on the GPU using the [OpenGL Shading Language](https://en.wikipedia.org/wiki/OpenGL_Shading_Language).

It has several .glsl files inside:

- `GammaLineFragment.glsl`
- `RGBBackgroundFragment.glsl`
- `RGBForegroundFragment.glsl`
- `RGBMaskFillBackgroundFragment.glsl`
- `RGBMaskFillForegroundFragment.glsl`
- `RGBMaskFillVertex.glsl`
- `RGBVertex.glsl`
- `ShapeDashFragment.glsl`
- `ShapeDashVertex.glsl`
- `ShapeSmoothFragment.glsl`
- `ShapeSmoothVertex.glsl`

---

### ProShapes

Motion's framework for handling Shapes.

Looks like it uses Metal 1.0, and makes uses of the Helium Renderer.

---

### RetimingMath

Looks like it's used by Motion to do some kind of complex retiming algorithm's.

---

### Stalgo

[STALGO](https://www.sthu.org/code/stalgo/) is an industrial-strength C++ software package for computing straight skeletons and mitered offset-curves.

---

### StudioSharedResources

This Framework just looks like it's mainly a collection of UI images used by both Motion and Final Cut Pro.

---

### TextFramework

Text Tools used by both Motion & Final Cut Pro.

Looks like it uses Metal 1.0.

---

### TLKEventDispatcher

TimeLineKit Event Dispatcher.

This looks like it's the "backend" to the magnetic timeline - i.e. the framework that translates user interactions (such as mouse clicks and drags) to actions with Final Cut Pro's timeline.

It looks like you register "events" for the timeline, and this Framework handles these requests.

---

### TLKit

The TimeLineKit Framework. This is the Framework that makes up the Magnetic Timeline, and also the timelines for iMovie & Motion.

It contains a bunch of `.caar` files, which are binary plists.

The `CornerRadius.plist` file allows you to adjust the corner radius of clips in the timeline.

I believe filenames that say "SimpleMode" refer to iMovie.

---

### VideoToolbox

I think this is the Framework that communicates with AV Foundations, CoreMedia, and handles video decoding, codecs, etc.