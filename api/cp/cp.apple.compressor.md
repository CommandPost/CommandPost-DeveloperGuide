# [docs](index.md) » cp.apple.compressor
---

Represents the Compressor application, providing functions that allow different tasks to be accomplished.

## Submodules
 * [cp.apple.compressor.app](cp.apple.compressor.app.md)

## API Overview
* Constants - Useful values which cannot be changed
 * [ALLOWED_IMPORT_ALL_EXTENSIONS](#allowed_import_all_extensions)
 * [ALLOWED_IMPORT_AUDIO_EXTENSIONS](#allowed_import_audio_extensions)
 * [ALLOWED_IMPORT_IMAGE_EXTENSIONS](#allowed_import_image_extensions)
 * [ALLOWED_IMPORT_VIDEO_EXTENSIONS](#allowed_import_video_extensions)
 * [BUNDLE_ID](#bundle_id)
 * [EARLIEST_SUPPORTED_VERSION](#earliest_supported_version)
* Methods - API calls which can only be made on an object returned by a constructor
 * [bundleID](#bundleid)
 * [getVersion](#getversion)
 * [hide](#hide)
 * [launch](#launch)
 * [notifier](#notifier)
 * [path](#path)
 * [quit](#quit)
 * [restart](#restart)
 * [show](#show)

## API Documentation

### Constants

#### [ALLOWED_IMPORT_ALL_EXTENSIONS](#allowed_import_all_extensions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor.ALLOWED_IMPORT_ALL_EXTENSIONS` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Table of all file extensions Final Cut Pro can import.                                                                                         |

#### [ALLOWED_IMPORT_AUDIO_EXTENSIONS](#allowed_import_audio_extensions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor.ALLOWED_IMPORT_AUDIO_EXTENSIONS` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Table of audio file extensions Final Cut Pro can import.                                                                                         |

#### [ALLOWED_IMPORT_IMAGE_EXTENSIONS](#allowed_import_image_extensions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor.ALLOWED_IMPORT_IMAGE_EXTENSIONS` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Table of image file extensions Final Cut Pro can import.                                                                                         |

#### [ALLOWED_IMPORT_VIDEO_EXTENSIONS](#allowed_import_video_extensions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor.ALLOWED_IMPORT_VIDEO_EXTENSIONS` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Table of video file extensions Final Cut Pro can import.                                                                                         |

#### [BUNDLE_ID](#bundle_id)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor.BUNDLE_ID` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | Compressor's Bundle ID                                                                                         |

#### [EARLIEST_SUPPORTED_VERSION](#earliest_supported_version)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor.EARLIEST_SUPPORTED_VERSION <semver>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant                                                                                         |
| **Description**                                      | The earliest version this API supports.                                                                                         |

### Methods

#### [bundleID](#bundleid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor:bundleID() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns the Compressor Bundle ID                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A string of the Compressor Bundle ID                                                |

#### [getVersion](#getversion)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor:getVersion() -> string | nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Version of Compressor                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * Version as string or nil if an error occurred                                                |
| **Notes**                                            |  * If Compressor is running it will get the version of the active Compressor application, otherwise, it will use hs.application.infoForBundleID() to find the version.                                                      |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor:hide() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Hides Compressor                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The compressor instance.                                                |

#### [launch](#launch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor:launch([waitSeconds]) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Launches Compressor, or brings it to the front if it was already running.                                                                                         |
| **Parameters**                                       |  * waitSeconds      - if provided, we will wait for up to the specified seconds for the launch to complete.                                       |
| **Returns**                                          |  * `true` if Compressor was either launched or focused, otherwise false (e.g. if Compressor doesn't exist)                                                |

#### [notifier](#notifier)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor:notifier() -> cp.ui.notifier` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Returns a notifier that is tracking the application UI element. It has already been started.                                                                                         |
| **Parameters**                                       | * None                                       |
| **Returns**                                          | * The notifier.                                                |

#### [path](#path)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor:path() -> string or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Path to Compressor Application                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * A string containing Compressor's filesystem path, or `nil` if the bundle identifier could not be located                                                |

#### [quit](#quit)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor:quit([waitSeconds]) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Quits Compressor                                                                                         |
| **Parameters**                                       |  * waitSeconds  - if provided, we will wait for the specified time for the quit to complete before returning.                                       |
| **Returns**                                          |  * The `compressor` instance.                                                |

#### [restart](#restart)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor:restart([waitSeconds]) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Restart the application.                                                                                         |
| **Parameters**                                       |  * waitSeconds  - if provided, we will wait for up to the specified seconds for the restart to complete before returning.                                       |
| **Returns**                                          |  * `true` if the application was running and restarted successfully.                                                |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor:show() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method                                                                                         |
| **Description**                                      | Activate Compressor                                                                                         |
| **Parameters**                                       |  * None                                       |
| **Returns**                                          |  * The compressor instance.                                                |

