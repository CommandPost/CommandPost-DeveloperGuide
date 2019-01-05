# [docs](index.md) » cp.apple.fcpxml
---

This extension adds functions and methods that simplify the creation
and management of the FCPXML document structure. It allows you to load FCPXML files
from file, or build them from scratch using Lua - which you can then export back to a
FCPXML file.

With the Final Cut Pro X XML (FCPXML) format, you can transfer the details of your
events and projects between Final Cut Pro X and third-party applications, devices,
and media asset management tools that do not natively recognize Final Cut Pro X events
or projects. FCPXML 1.8 requires Final Cut Pro X 10.4.1 or later.

FCPXML describes certain aspects of projects and events that are useful for other
applications. It does not describe all possible data, and therefore is not a substitute
for the native project and event data organized in a library bundle.

You can use Final Cut Pro X to export and import FCPXML documents to accomplish the following tasks:
 * Exchange Final Cut Pro X event and project data with other applications.
 * Create new Final Cut Pro X events and projects.

The Key Features of this extension include:
 * Access an FCPXML document’s resources, events, clips, and projects through simple object properties.
 * Create and modify resources, events, clips, and projects with included properties and methods.
 * Easily manipulate timing values.
 * Output FCPXML files with proper text formatting.
 * Validate FCPXML documents with the DTD.

Here is a list of Final Cut Pro X terms used in this extension:

 * A clip is a reference to media, such as a video, audio, or still image file, that allows
   you to edit and annotate the media without directly modifying it. A clip controls which
   portions of the media you would like to use, and it allows you to organize the media based
   on keywords you have applied. Clips can also contain other clips to represent composite media.
 * Use a Final Cut Pro X project and its primary container, a sequence, to build a finished movie.
   The sequence defines your movie’s final appearance. You build a sequence by bringing clips into
   it from one or more events, or by creating new clips within the sequence. You adjust and arrange
   the clips, along with other story elements in the sequence, to produce your movie. Every clip in
   a project is unique to that project (not shared), but referenced media always resides in an event
   and may be shared across more than one project.
 * Use a Final Cut Pro X event to store and organize clips and projects. You can import media files
   into a new or existing event. You can copy these files into an event’s own media folder, or reference
   them in their original locations. Final Cut Pro X tracks each imported file as an asset and ensures
   your event contains at least one clip per asset.
 * Use a Final Cut Pro X library to organize your events. The library is a container that you use to
   keep track of all events, projects, and media related to your work.

This extension was inspired and uses code based on [Pipeline](https://github.com/reuelk/pipeline).
Thank you Reuel Kim for making something truly awesome, and releasing it as Open Source!

## Submodules
 * [cp.apple.fcpxml.compoundClip](cp.apple.fcpxml.compoundClip.md)
 * [cp.apple.fcpxml.event](cp.apple.fcpxml.event.md)
 * [cp.apple.fcpxml.gap](cp.apple.fcpxml.gap.md)
 * [cp.apple.fcpxml.multicamClip](cp.apple.fcpxml.multicamClip.md)
 * [cp.apple.fcpxml.multicamResource](cp.apple.fcpxml.multicamResource.md)
 * [cp.apple.fcpxml.project](cp.apple.fcpxml.project.md)
 * [cp.apple.fcpxml.resource](cp.apple.fcpxml.resource.md)
 * [cp.apple.fcpxml.secondaryStoryline](cp.apple.fcpxml.secondaryStoryline.md)
 * [cp.apple.fcpxml.title](cp.apple.fcpxml.title.md)

## API Overview
* Constants - Useful values which cannot be changed
 * [ANCHOR_ITEMS](#anchor_items)
 * [AUDIO_FADE_TYPE](#audio_fade_type)
 * [AUDIO_OUTPUT_CHANNEL](#audio_output_channel)
 * [AUDIO_SAMPLE_RATE](#audio_sample_rate)
 * [CLIP_ITEMS](#clip_items)
 * [COLLECTION_TYPES](#collection_types)
 * [COLOR_SPACE](#color_space)
 * [COLOR_SPACE_OVERRIDE](#color_space_override)
 * [EQ_MODE](#eq_mode)
 * [EVENT_ITEM_TYPES](#event_item_types)
 * [FIELD_ORDER](#field_order)
 * [MARKER_ITEMS](#marker_items)
 * [METADATA_TYPES](#metadata_types)
 * [PROJECTION](#projection)
 * [PROJECTION_OVERRIDE](#projection_override)
 * [RESOURCE_TYPES](#resource_types)
 * [STEREOSCOPIC](#stereoscopic)
 * [STEREOSCOPIC_OVERRIDE](#stereoscopic_override)
 * [TIMECODE_FORMAT](#timecode_format)
* Functions - API calls offered directly by the extension
 * [latestDTDVersion](#latestdtdversion)
 * [supportedDTDs](#supporteddtds)
* Constructors - API calls which return an object, typically one that offers API methods
 * [new](#new)
 * [newCompoundClip](#newcompoundclip)
 * [newEvent](#newevent)
 * [newGap](#newgap)
 * [newMulticamClip](#newmulticamclip)
 * [newMulticamResource](#newmulticamresource)
 * [newProject](#newproject)
 * [newResource](#newresource)
 * [newSecondaryStoryline](#newsecondarystoryline)
 * [newTitle](#newtitle)
 * [open](#open)
* Methods - API calls which can only be made on an object returned by a constructor
 * [add](#add)
 * [allClips](#allclips)
 * [allEventItemNames](#alleventitemnames)
 * [allEventItems](#alleventitems)
 * [allProjectNames](#allprojectnames)
 * [allProjects](#allprojects)
 * [assetResources](#assetresources)
 * [compoundResources](#compoundresources)
 * [effectResources](#effectresources)
 * [eventNames](#eventnames)
 * [events](#events)
 * [formatResources](#formatresources)
 * [lastResourceID](#lastresourceid)
 * [lastTextStyleID](#lasttextstyleid)
 * [library](#library)
 * [multicamResources](#multicamresources)
 * [remove](#remove)
 * [removeAllEvents](#removeallevents)
 * [removeAllResources](#removeallresources)
 * [resource](#resource)
 * [resources](#resources)
 * [roles](#roles)
 * [saveToFile](#savetofile)
 * [valid](#valid)
 * [xmlVersion](#xmlversion)

## API Documentation

### Constants

#### [ANCHOR_ITEMS](#anchor_items)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml.ANCHOR_ITEMS -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Supported Anchor Item Values. The 'anchor_item' entity declares the valid anchorable story elements. When present, anchored items must have a non-zero 'lane' value. |

#### [AUDIO_FADE_TYPE](#audio_fade_type)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml.AUDIO_FADE_TYPE -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Supported Audio Fade Type Values. |

#### [AUDIO_OUTPUT_CHANNEL](#audio_output_channel)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml.AUDIO_OUTPUT_CHANNEL -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Supported Audio Output Channel Values. |

#### [AUDIO_SAMPLE_RATE](#audio_sample_rate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml.AUDIO_SAMPLE_RATE -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Supported Audio Sample Rate values. |

#### [CLIP_ITEMS](#clip_items)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml.CLIP_ITEMS -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Supported Clip Item Values. The 'clip_item' entity declares the primary story elements that may appear inside a clip. |

#### [COLLECTION_TYPES](#collection_types)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml.COLLECTION_TYPES -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Supported Collection Types in FCPXML Documents. |

#### [COLOR_SPACE](#color_space)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml.COLOR_SPACE -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Supported Field Order values. |

#### [COLOR_SPACE_OVERRIDE](#color_space_override)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml.COLOR_SPACE_OVERRIDE -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Supported Color Space Override values. |

#### [EQ_MODE](#eq_mode)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml.EQ_MODE -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Supported EQ Mode Values. |

#### [EVENT_ITEM_TYPES](#event_item_types)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml.EVENT_ITEM_TYPES -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Supported Event Item Types in FCPXML Documents. |

#### [FIELD_ORDER](#field_order)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml.FIELD_ORDER -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Supported Field Order values. |

#### [MARKER_ITEMS](#marker_items)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml.MARKER_ITEMS -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Supported Marker Item Values. |

#### [METADATA_TYPES](#metadata_types)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml.METADATA_TYPES -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Supported Metadata Types in FCPXML Documents. |

#### [PROJECTION](#projection)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml.PROJECTION -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Supported Projection values. |

#### [PROJECTION_OVERRIDE](#projection_override)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml.PROJECTION_OVERRIDE -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Supported Projection Override values. |

#### [RESOURCE_TYPES](#resource_types)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml.RESOURCE_TYPES -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Supported Resource Types in FCPXML Documents. |

#### [STEREOSCOPIC](#stereoscopic)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml.STEREOSCOPIC -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Supported Stereoscopic values. |

#### [STEREOSCOPIC_OVERRIDE](#stereoscopic_override)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml.STEREOSCOPIC_OVERRIDE -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Supported Stereoscopic Override values. |

#### [TIMECODE_FORMAT](#timecode_format)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml.TIMECODE_FORMAT -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Supported Timecode Format values. |

### Functions

#### [latestDTDVersion](#latestdtdversion)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml.latestDTDVersion() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets the latest supported FCPXML DTD version. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The latest DTD version as a string, for example: "1.8".</li></ul> |

#### [supportedDTDs](#supporteddtds)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml.supportedDTDs() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a table containing the version numbers of all the DTD documents included in this extension. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table of supported DTD versions as strings.</li></ul> |

### Constructors

#### [new](#new)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml.new() -> fcpxmlDocument Object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Create a new empty FCPXML Document object. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A new FCPXML object.</li></ul> |

#### [newCompoundClip](#newcompoundclip)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml.newCompoundClip(name, ref, offset, duration, startTimecode, useAudioSubroles) -> fcpxmlCompoundClip Object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new ref-clip FCPXML Document object. |
| **Parameters**                                       | <ul><li>name - The name of the Compound Clip as string.</li><li>ref - The reference ID of the compound clip as string.</li><li>offset - The offset of the compound clip in flicks.</li><li>duration - The duration of the compound clip in flicks.</li><li>startTimecode - The start timecode in flicks.</li><li>useAudioSubroles - A boolean.</li></ul> |
| **Returns**                                          | <ul><li>A new Compound Clip object.</li></ul> |

#### [newEvent](#newevent)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml.newEvent(name[, items]) -> fcpxmlEvent Object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new event object. |
| **Parameters**                                       | <ul><li>name - The name of the event.</li><li>items - An optional table of items to add to the event.</li></ul> |
| **Returns**                                          | <ul><li>A new event object.</li></ul> |

#### [newGap](#newgap)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml.newGap(offset, duration, startTimecode) -> fcpxmlGap Object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new gap to be used in a timeline. |
| **Parameters**                                       | <ul><li>offset - The offset of the Gap clip in flicks.</li><li>duration - The duration of the Gap clip in flicks.</li><li>startTimecode - The start timecode of the Gap clip in flicks.</li></ul> |
| **Returns**                                          | <ul><li>A new Gap Clip object.</li></ul> |

#### [newMulticamClip](#newmulticamclip)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml.newMulticamClip(name, refID, offset, startTimecode, duration, mcSources) -> fcpxmlMulticamClip Object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new multicam event clip FCPXML Document object. |
| **Parameters**                                       | <ul><li>name - The name of the Multicam Clip as a string.</li><li>refID - The reference ID of the Multicam Clip.</li><li>offset - The offset of the Multicam clip in flicks.</li><li>startTimecode - The start timecode in flicks.</li><li>duration - The duration of the Multicam clip.</li><li>mcSources - A table of multicam sources.</li></ul> |
| **Returns**                                          | <ul><li>A new Multicam Clip object.</li></ul> |

#### [newMulticamResource](#newmulticamresource)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml.newMulticamResource(name, id, formatRef, startTimecode, timecodeFormat, renderColorSpace, angles) -> fcpxmlMulticamResource Object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new FCPXML multicam reference FCPXML Document object. |
| **Parameters**                                       | <ul><li>name - The name of the Multicam Resource as a string.</li><li>id - The ID of the Multicam Resource as a string.</li><li>formatRef - The format of the Multicam Resource.</li><li>startTimecode - The start timecode in flicks.</li><li>timecodeFormat - The timecode format (see: <code>cp.apple.fcpxml.TIMECODE_FORMAT</code>).</li><li>renderColorSpace - The render color space (see: <code>cp.apple.fcpxml.COLOR_SPACE</code>).</li><li>angles - A table of angle objects.</li></ul> |
| **Returns**                                          | <ul><li>A new Multicam Resource object.</li></ul> |

#### [newProject](#newproject)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml.newProject(name, format, duration, timecodeStart, timecodeFormat, audioLayout, audioRate, renderColorSpace[, clips]) -> fcpxmlProject Object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new project FCPXML object and optionally adds clips to it. |
| **Parameters**                                       | <ul><li>name - The name of the project as a string.</li><li>format - The format of the project.</li><li>duration - The duration of the project.</li><li>timecodeStart - The start timecode of the project.</li><li>timecodeFormat - The timecode format of the project.</li><li>audioLayout - The audio layout of the project.</li><li>audioRate - The audio sample rate of the project.</li><li>renderColorSpace - The render color space of the project.</li><li>clips - An optional table of clips you want to add to the project.</li></ul> |
| **Returns**                                          | <ul><li>A new project object.</li></ul> |

#### [newResource](#newresource)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml.newResource() -> fcpxmlResource Object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new resource object. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A new resource object.</li></ul> |

#### [newSecondaryStoryline](#newsecondarystoryline)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml.newSecondaryStoryline(lane, offset, formatRef, clips) -> fcpxmlSecondaryStoryline Object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new secondary storyline FCPXML Document object. |
| **Parameters**                                       | <ul><li>lane - The lane you want the secondary storyline to appear.</li><li>offset - The offset of the secondary storyline in flicks.</li><li>formatRef - The format of the secondary storyline.</li><li>clips - A table of clips.</li></ul> |
| **Returns**                                          | <ul><li>A new Secondary Storyline object.</li></ul> |

#### [newTitle](#newtitle)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml.newTitle(titleName, lane, offset, ref, duration, start, role, titleText, textStyleID, newTextStyle, newTextStyleAttributes) -> fcpxmlTitle Object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new title to be used in a timeline. |
| **Parameters**                                       | <ul><li>titleName</li><li>lane</li><li>offset</li><li>ref</li><li>duration</li><li>start</li><li>role</li><li>titleText</li><li>textStyleID</li><li>newTextStyle</li><li>newTextStyleAttributes</li></ul> |
| **Returns**                                          | <ul><li>A new Title object.</li></ul> |
| **Notes**                                            | <ul><li><code>newTextStyleAttributes</code> is only used if <code>newTextStyle</code> is set to <code>true</code>.</li><li>When <code>newTextStyle</code> is set to <code>true</code>, the following atttributes can be used   within the <code>newTextStyleAttributes</code> table:<ul><li>font - The font name as string (defaults to "Helvetica").</li><li>fontSize - The font size a number (defaults to 62).</li><li>fontFace - The font face as a string (defaults to "Regular").</li><li>fontColor - The font color as a <code>hs.drawing.color</code> object (defaults to black).</li><li>strokeColor - The stroke color as a <code>hs.drawing.color</code> object (defaults to <code>nil</code>).</li><li>strokeWidth - The stroke width as a number (defaults to 2).</li><li>shadowColor - The stroke color as a <code>hs.drawing.color</code> object (defaults to <code>nil</code>).</li><li>shadowDistance - The shadow distance as a number (defaults to 5).</li><li>shadowAngle - The shadow angle as a number (defaults to 315).</li><li>shadowBlurRadius - The shadow blur radius as a number (defaults to 1).</li><li>alignment - The text alignment as a string (defaults to "center").</li><li>xPosition - The x position of the title (defaults to 0).</li><li>yPosition - The y position of the title (defaults to 0).</li></ul></li></ul> |

#### [open](#open)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml.open(file) -> fcpxmlDocument Object` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Create a new FCPXML Document object from the specified file. |
| **Parameters**                                       | <ul><li>file - An FCPXML document you want to read from an external file.</li></ul> |
| **Returns**                                          | <ul><li>A new FCPXML object.</li></ul> |

### Methods

#### [add](#add)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml:add(resources) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Adds one or more resources to the FCPXML document. |
| **Parameters**                                       | <ul><li>resources - A single <code>resourceObject</code> or a table of <code>resourceObject</code>'s to add to the FCPXML document.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successfully added, otherwise <code>false</code>.</li></ul> |

#### [allClips](#allclips)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml:allClips() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | An table of all clips in all events in the FCPXML document. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table</li></ul> |

#### [allEventItemNames](#alleventitemnames)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml:allEventItemNames() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The names of all items from all events. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table</li></ul> |

#### [allEventItems](#alleventitems)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml:allEventItems() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | All items from all events. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table</li></ul> |

#### [allProjectNames](#allprojectnames)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml:allProjectNames() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The names of all projects from all events. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table</li></ul> |

#### [allProjects](#allprojects)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml:allProjects() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | An table of all projects in all events in the FCPXML document. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table</li></ul> |

#### [assetResources](#assetresources)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml:assetResources(file) -> table | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns asset resources that match the given file. |
| **Parameters**                                       | <ul><li>file - The file path.</li></ul> |
| **Returns**                                          | <ul><li>A table of resource objects or <code>nil</code> if no assets match.</li></ul> |

#### [compoundResources](#compoundresources)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml:compoundResources() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | An table of all compound clip resources in the FCPXML document. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table</li></ul> |

#### [effectResources](#effectresources)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml:effectResources() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | An table of all effect resources in the FCPXML document. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table</li></ul> |

#### [eventNames](#eventnames)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml:eventNames() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The names of all events as strings in a table. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table containing all of the event names as strings.</li></ul> |

#### [events](#events)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml:events() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | An table of all event elements in the FCPXML document. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table</li></ul> |

#### [formatResources](#formatresources)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml:formatResources() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | An table of all format resources in the FCPXML document. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table</li></ul> |

#### [lastResourceID](#lastresourceid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml:lastResourceID() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The highest resource ID number used in the FCPXML document. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A number</li></ul> |

#### [lastTextStyleID](#lasttextstyleid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml:lastTextStyleID() -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | The highest text style ID number used in the FCPXML document. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A number</li></ul> |

#### [library](#library)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml:library() -> libraryObject` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets the Final Cut Pro Library. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A <code>libraryObject</code></li></ul> |

#### [multicamResources](#multicamresources)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml:multicamResources() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | An table of all multicam resources in the FCPXML document. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table</li></ul> |

#### [remove](#remove)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml:remove(resources) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Removes one or more resources from the FCPXML document. |
| **Parameters**                                       | <ul><li>resources - A single <code>resourceObject</code> or a table of <code>resourceObject</code>'s to add to the FCPXML document.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successfully removed, otherwise <code>false</code>.</li></ul> |

#### [removeAllEvents](#removeallevents)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml:removeAllEvents() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Removes all events from the library. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful, otherwise <code>false</code>.</li></ul> |

#### [removeAllResources](#removeallresources)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml:removeAllResources() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Removes all resources from the FCPXML document. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful, otherwise <code>false</code>.</li></ul> |

#### [resource](#resource)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml:resource(id) -> resourceObject | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the resource that matches the given ID string. |
| **Parameters**                                       | <ul><li>id - The ID string of the resource you want to access.</li></ul> |
| **Returns**                                          | <ul><li>A resource object or <code>nil</code> if the resource does not exist.</li></ul> |

#### [resources](#resources)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml:resources() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | An table of all resources in the FCPXML document. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table</li></ul> |

#### [roles](#roles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml:roles() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | An table of all roles used in the FCPXML document. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A table</li></ul> |

#### [saveToFile](#savetofile)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml:saveToFile(filename) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Saves the FCPML Document to the specified filename. |
| **Parameters**                                       | <ul><li>filename - the path and name of the file to save.</li></ul> |
| **Returns**                                          | <ul><li>Status - a boolean value indicating success (<code>true</code>) or failure (<code>false</code>).</li></ul> |

#### [valid](#valid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml:valid(filename[, version]) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Validates an FCPXML document against a document type definition (DTD). |
| **Parameters**                                       | <ul><li>filename - The path and filename of the FCPXML document you want to validate.</li><li>version - The optional FCPXML version you want to validate against.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if valid, otherwise <code>false</code>.</li></ul> |

#### [xmlVersion](#xmlversion)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.fcpxml:xmlVersion([version]) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Gets or sets the FCPXML version of the FCPXML document. |
| **Parameters**                                       | <ul><li>version - An optional string to set the version of the FCPXML document (for example: "1.8").</li></ul> |
| **Returns**                                          | <ul><li>A string containing the XML version of the FCPXML document.</li></ul> |

