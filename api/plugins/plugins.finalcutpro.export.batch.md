# [docs](index.md) » plugins.finalcutpro.export.batch
---

Batch Export Plugin

## Submodules
 * [plugins.finalcutpro.export.batch.manager](plugins.finalcutpro.export.batch.manager.md)

## API Overview
* Constants - Useful values which cannot be changed
 * [DEFAULT_CUSTOM_FILENAME](#default_custom_filename)
* Functions - API calls offered directly by the extension
 * [batchExport](#batchexport)
 * [batchExportBrowserClips](#batchexportbrowserclips)
 * [batchExportTimelineClips](#batchexporttimelineclips)
 * [changeCustomFilename](#changecustomfilename)
 * [changeExportDestinationFolder](#changeexportdestinationfolder)
 * [changeExportDestinationPreset](#changeexportdestinationpreset)
 * [getDestinationFolder](#getdestinationfolder)
 * [performBatchExport](#performbatchexport)
 * [sendBrowserClipsToCompressor](#sendbrowserclipstocompressor)
 * [sendTimelineClipsToCompressor](#sendtimelineclipstocompressor)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [customFilename](#customfilename)
 * [ignoreMissingEffects](#ignoremissingeffects)
 * [ignoreProxies](#ignoreproxies)
 * [replaceExistingFiles](#replaceexistingfiles)
 * [useCustomFilename](#usecustomfilename)

## API Documentation

### Constants

#### [DEFAULT_CUSTOM_FILENAME](#default_custom_filename)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.DEFAULT_CUSTOM_FILENAME -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Default Custom Filename                                                                                         |

### Functions

#### [batchExport](#batchexport)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.batchExport() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Opens the Batch Export popup.                                                                                         |
| **Parameters**                                       |  * mode - "timeline" or "browser". If no mode is specified then we will determine          the mode based off the mouse location.                                       |
| **Returns**                                          |  * `true` if successful otherwise `false`                                                |

#### [batchExportBrowserClips](#batchexportbrowserclips)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.batchExportBrowserClips(clips) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Batch Export Clips                                                                                         |
| **Parameters**                                       |  * clips - table of selected Clips                                       |
| **Returns**                                          |  * `true` if successful otherwise `false`                                                |

#### [batchExportTimelineClips](#batchexporttimelineclips)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.batchExportTimelineClips(clips) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Batch Export Timeline Clips                                                                                         |
| **Parameters**                                       |  * clips - table of selected Clips                                       |
| **Returns**                                          |  * `true` if successful otherwise `false`                                                |

#### [changeCustomFilename](#changecustomfilename)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.changeCustomFilename() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Change Custom Filename String.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `true` if successful otherwise `false`                                                |

#### [changeExportDestinationFolder](#changeexportdestinationfolder)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.changeExportDestinationFolder() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Change Export Destination Folder.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `true` if successful otherwise `false`                                                |

#### [changeExportDestinationPreset](#changeexportdestinationpreset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.changeExportDestinationPreset() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Change Export Destination Preset.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * `true` if successful otherwise `false`                                                |

#### [getDestinationFolder](#getdestinationfolder)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.getDestinationFolder() -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the destination preset.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The destination preset as a string, or `nil` if no preset is set.                                                |

#### [performBatchExport](#performbatchexport)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.performBatchExport() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Performs the Browser Batch Export function.                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * None                                                |

#### [sendBrowserClipsToCompressor](#sendbrowserclipstocompressor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.sendBrowserClipsToCompressor(clips) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Send Clips to Compressor                                                                                         |
| **Parameters**                                       |  * clips - table of selected Clips                                       |
| **Returns**                                          |  * `true` if successful otherwise `false`                                                |

#### [sendTimelineClipsToCompressor](#sendtimelineclipstocompressor)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.sendTimelineClipsToCompressor(clips) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Send Timeline Clips to Compressor.                                                                                         |
| **Parameters**                                       |  * clips - table of selected Clips                                       |
| **Returns**                                          |  * `true` if successful otherwise `false`                                                |

### Fields

#### [customFilename](#customfilename)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.customFilename <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Custom Filename for Batch Export.                                                                                         |

#### [ignoreMissingEffects](#ignoremissingeffects)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.ignoreMissingEffects <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Defines whether or not a Batch Export should Ignore Missing Effects.                                                                                         |

#### [ignoreProxies](#ignoreproxies)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.ignoreProxies <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Defines whether or not a Batch Export should Ignore Proxies.                                                                                         |

#### [replaceExistingFiles](#replaceexistingfiles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.replaceExistingFiles <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Defines whether or not a Batch Export should Replace Existing Files.                                                                                         |

#### [useCustomFilename](#usecustomfilename)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.useCustomFilename <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field                                                                                         |
| **Description**                                      | Defines whether or not the Batch Export tool should override the clipname with a custom filename.                                                                                         |

