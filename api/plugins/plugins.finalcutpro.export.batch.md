# [docs](index.md) » plugins.finalcutpro.export.batch
---

Timeline Batch Export Plugin.

## Submodules
 * [plugins.finalcutpro.export.batch.manager](plugins.finalcutpro.export.batch.manager.md)

## API Overview
* Constants - Useful values which cannot be changed
 * [DEFAULT_CUSTOM_FILENAME](#default_custom_filename)
* Functions - API calls offered directly by the extension
 * [batchExport](#batchexport)
 * [batchExportTimelineClips](#batchexporttimelineclips)
 * [changeCustomFilename](#changecustomfilename)
 * [changeExportDestinationFolder](#changeexportdestinationfolder)
 * [changeExportDestinationPreset](#changeexportdestinationpreset)
 * [getDestinationFolder](#getdestinationfolder)
 * [performBatchExport](#performbatchexport)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [customFilename](#customfilename)
 * [destinationPreset](#destinationpreset)
 * [ignoreInvalidCaptions](#ignoreinvalidcaptions)
 * [ignoreMissingEffects](#ignoremissingeffects)
 * [ignoreProxies](#ignoreproxies)
 * [replaceExistingFiles](#replaceexistingfiles)
 * [useCustomFilename](#usecustomfilename)

## API Documentation

### Constants

#### [DEFAULT_CUSTOM_FILENAME](#default_custom_filename)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.DEFAULT_CUSTOM_FILENAME -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Default Custom Filename |

### Functions

#### [batchExport](#batchexport)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.batchExport() -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Opens the Batch Export popup. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful otherwise <code>false</code></li></ul> |

#### [batchExportTimelineClips](#batchexporttimelineclips)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.batchExportTimelineClips(clips) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Batch Export Timeline Clips |
| **Parameters**                                       | <ul><li>clips - table of selected Clips</li><li>sendToCompressor - <code>true</code> if sending to Compressor, otherwise <code>false</code></li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if successful otherwise <code>false</code></li></ul> |

#### [changeCustomFilename](#changecustomfilename)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.changeCustomFilename() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Change Custom Filename String. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [changeExportDestinationFolder](#changeexportdestinationfolder)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.changeExportDestinationFolder() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Change Export Destination Folder. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [changeExportDestinationPreset](#changeexportdestinationpreset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.changeExportDestinationPreset() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Change Export Destination Preset. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [getDestinationFolder](#getdestinationfolder)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.getDestinationFolder() -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets the destination preset. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The destination preset as a string, or <code>nil</code> if no preset is set.</li></ul> |

#### [performBatchExport](#performbatchexport)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.performBatchExport() -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Performs the Browser Batch Export function. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

### Fields

#### [customFilename](#customfilename)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.customFilename <cp.prop: string>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Custom Filename for Batch Export. |

#### [destinationPreset](#destinationpreset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.destinationPreset <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Destination Preset. |

#### [ignoreInvalidCaptions](#ignoreinvalidcaptions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.ignoreInvalidCaptions <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Defines whether or not a Batch Export should Ignore Invalid Captions. |

#### [ignoreMissingEffects](#ignoremissingeffects)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.ignoreMissingEffects <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Defines whether or not a Batch Export should Ignore Missing Effects. |

#### [ignoreProxies](#ignoreproxies)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.ignoreProxies <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Defines whether or not a Batch Export should Ignore Proxies. |

#### [replaceExistingFiles](#replaceexistingfiles)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.replaceExistingFiles <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Defines whether or not a Batch Export should Replace Existing Files. |

#### [useCustomFilename](#usecustomfilename)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.export.batch.useCustomFilename <cp.prop: boolean>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | Defines whether or not the Batch Export tool should override the clipname with a custom filename. |

