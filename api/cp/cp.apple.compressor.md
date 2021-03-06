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
 * [doRestart](#dorestart)
 * [hide](#hide)
 * [launch](#launch)
 * [notifier](#notifier)
 * [path](#path)
 * [quit](#quit)
 * [show](#show)

## API Documentation

### Constants

#### [ALLOWED_IMPORT_ALL_EXTENSIONS](#allowed_import_all_extensions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor.ALLOWED_IMPORT_ALL_EXTENSIONS` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Table of all file extensions Final Cut Pro can import. |

#### [ALLOWED_IMPORT_AUDIO_EXTENSIONS](#allowed_import_audio_extensions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor.ALLOWED_IMPORT_AUDIO_EXTENSIONS` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Table of audio file extensions Final Cut Pro can import. |

#### [ALLOWED_IMPORT_IMAGE_EXTENSIONS](#allowed_import_image_extensions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor.ALLOWED_IMPORT_IMAGE_EXTENSIONS` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Table of image file extensions Final Cut Pro can import. |

#### [ALLOWED_IMPORT_VIDEO_EXTENSIONS](#allowed_import_video_extensions)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor.ALLOWED_IMPORT_VIDEO_EXTENSIONS` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Table of video file extensions Final Cut Pro can import. |

#### [BUNDLE_ID](#bundle_id)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor.BUNDLE_ID` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | Compressor's Bundle ID |

#### [EARLIEST_SUPPORTED_VERSION](#earliest_supported_version)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor.EARLIEST_SUPPORTED_VERSION <semver>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constant |
| **Description**                                      | The earliest version this API supports. |

### Methods

#### [bundleID](#bundleid)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor:bundleID() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns the Compressor Bundle ID |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string of the Compressor Bundle ID</li></ul> |

#### [doRestart](#dorestart)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor:doRestart() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a [Statement](cp.rx.go.Statement.md) that will restart the application. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if the application was running and restarted successfully.</li></ul> |

#### [hide](#hide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor:hide() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Hides Compressor |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The compressor instance.</li></ul> |

#### [launch](#launch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor:launch([waitSeconds]) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Launches Compressor, or brings it to the front if it was already running. |
| **Parameters**                                       | <ul><li>waitSeconds      - if provided, we will wait for up to the specified seconds for the launch to complete.</li></ul> |
| **Returns**                                          | <ul><li><code>true</code> if Compressor was either launched or focused, otherwise false (e.g. if Compressor doesn't exist)</li></ul> |

#### [notifier](#notifier)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor:notifier() -> cp.ui.notifier` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Returns a notifier that is tracking the application UI element. It has already been started. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The notifier.</li></ul> |

#### [path](#path)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor:path() -> string or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Path to Compressor Application |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string containing Compressor's filesystem path, or <code>nil</code> if the bundle identifier could not be located</li></ul> |

#### [quit](#quit)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor:quit([waitSeconds]) -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Quits Compressor |
| **Parameters**                                       | <ul><li>waitSeconds  - if provided, we will wait for the specified time for the quit to complete before returning.</li></ul> |
| **Returns**                                          | <ul><li>The <code>compressor</code> instance.</li></ul> |

#### [show](#show)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.compressor:show() -> self` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | Activate Compressor |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The compressor instance.</li></ul> |

