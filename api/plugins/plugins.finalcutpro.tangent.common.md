# [docs](index.md) » plugins.finalcutpro.tangent.common
---

Common Final Cut Pro functions for Tangent

## API Overview
* Functions - API calls offered directly by the extension
 * [buttonParameter](#buttonparameter)
 * [checkboxParameter](#checkboxparameter)
 * [checkboxParameterByIndex](#checkboxparameterbyindex)
 * [checkboxSliderParameter](#checkboxsliderparameter)
 * [commandParameter](#commandparameter)
 * [doShortcut](#doshortcut)
 * [doShowParameter](#doshowparameter)
 * [dynamicPopupSliderParameter](#dynamicpopupsliderparameter)
 * [functionParameter](#functionparameter)
 * [menuParameter](#menuparameter)
 * [popupParameter](#popupparameter)
 * [popupParameters](#popupparameters)
 * [popupSliderParameter](#popupsliderparameter)
 * [radioButtonParameter](#radiobuttonparameter)
 * [shortcutParameter](#shortcutparameter)
 * [sliderParameter](#sliderparameter)
 * [volumeSliderParameter](#volumesliderparameter)
 * [xyParameter](#xyparameter)

## API Documentation

### Functions

#### [buttonParameter](#buttonparameter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.tangent.common.buttonParameter(group, param, id, label) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sets up a new Button Parameter for the Tangent |
| **Parameters**                                       | <ul><li>group - The Tangent Group.</li><li>param - The Parameter</li><li>id - The Tangent ID.</li><li>label - The label to be used by the Tangent. This can either be an i18n ID or           a plain string.</li></ul> |
| **Returns**                                          | <ul><li>An updated ID</li></ul> |

#### [checkboxParameter](#checkboxparameter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.tangent.common.checkboxParameter(group, param, id, label) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sets up a new Checkbox Parameter for the Tangent |
| **Parameters**                                       | <ul><li>group - The Tangent Group.</li><li>param - The Parameter</li><li>id - The Tangent ID.</li><li>label - The label to be used by the Tangent. This can either be an i18n ID or           a plain string.</li></ul> |
| **Returns**                                          | <ul><li>An updated ID</li></ul> |

#### [checkboxParameterByIndex](#checkboxparameterbyindex)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.tangent.common.checkboxParameterByIndex(group, section, nextSection, id, label, index) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sets up a new AXCheckBox object for the Tangent. |
| **Parameters**                                       | <ul><li>group - The Tangent Group.</li><li>section - The section as it appears in the FCPX Inspector.</li><li>nextSection - The next section as it appears in the FCPX Inspector.</li><li>id - The Tangent ID.</li><li>label - The label to be used by the Tangent. This can either be an i18n ID or           a plain string.</li><li>index - The index of the checkbox in the section.</li></ul> |
| **Returns**                                          | <ul><li>An updated ID</li></ul> |

#### [checkboxSliderParameter](#checkboxsliderparameter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.tangent.common.checkboxSliderParameter(group, id, label, options, resetIndex) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sets up a new Popup Slider parameter for the Tangent |
| **Parameters**                                       | <ul><li>group - The Tangent Group.</li><li>id - The Tangent ID.</li><li>label - The label to be used by the Tangent. This can either be an i18n ID or           a plain string.</li><li>options - A table of options. The key for each option should be a number ID             (in the order it appears in the UI), and the value should be another             table with keys for <code>flexoID</code> and <code>i18n</code> values.</li><li>resetIndex - An index of which item to use when "reset" is triggered.</li></ul> |
| **Returns**                                          | <ul><li>An updated ID</li></ul> |

#### [commandParameter](#commandparameter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.tangent.common.commandParameter(group, id, commandID) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sets up a new Command Parameter for the Tangent |
| **Parameters**                                       | <ul><li>group - The Tangent Group.</li><li>id - The Tangent ID.</li><li>commandID - The command ID.</li></ul> |
| **Returns**                                          | <ul><li>An updated ID</li></ul> |

#### [doShortcut](#doshortcut)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.tangent.common.doShortcut(id) -> none` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Triggers a shortcut via Rx. |
| **Parameters**                                       | <ul><li>id - The ID of the shortcut.</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul> |

#### [doShowParameter](#doshowparameter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.tangent.common.doShowParameter(group, param, id, label) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sets up a new `DoShow` Parameter for the Tangent |
| **Parameters**                                       | <ul><li>group - The Tangent Group.</li><li>param - The Parameter</li><li>id - The Tangent ID.</li><li>label - The label to be used by the Tangent. This can either be an i18n ID or           a plain string.</li></ul> |
| **Returns**                                          | <ul><li>An updated ID</li></ul> |

#### [dynamicPopupSliderParameter](#dynamicpopupsliderparameter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.tangent.common.dynamicPopupSliderParameter(group, param, id, label, defaultValue) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sets up a new Popup Slider parameter for the Tangent |
| **Parameters**                                       | <ul><li>group - The Tangent Group.</li><li>param - The Parameter</li><li>id - The Tangent ID.</li><li>label - The label to be used by the Tangent. This can either be an i18n ID or           a plain string.</li><li>defaultValue - The default value to use when the reset button is pressed.</li></ul> |
| **Returns**                                          | <ul><li>An updated ID</li></ul> |

#### [functionParameter](#functionparameter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.tangent.common.functionParameter(group, id, label, fn) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sets up a new Function Parameter for the Tangent. |
| **Parameters**                                       | <ul><li>group - The Tangent Group.</li><li>id - The Tangent ID.</li><li>label - The label to be used by the Tangent. This can either be an i18n ID or           a plain string.</li><li>path - The list of menu items you'd like to activate as a table.</li></ul> |
| **Returns**                                          | <ul><li>An updated ID</li></ul> |

#### [menuParameter](#menuparameter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.tangent.common.menuParameter(group, id, label, path) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sets up a new Final Cut Pro Menu Parameter for the Tangent. |
| **Parameters**                                       | <ul><li>group - The Tangent Group.</li><li>id - The Tangent ID.</li><li>label - The label to be used by the Tangent. This can either be an i18n ID or           a plain string.</li><li>path - The list of menu items you'd like to activate as a table.</li></ul> |
| **Returns**                                          | <ul><li>An updated ID</li></ul> |

#### [popupParameter](#popupparameter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.tangent.common.popupParameter(group, param, id, value, label) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sets up a new Popup Parameter for the Tangent |
| **Parameters**                                       | <ul><li>group - The Tangent Group.</li><li>param - The Parameter.</li><li>id - The Tangent ID.</li><li>value - The value to select as a string.</li><li>label - The label to be used by the Tangent. This can either be an i18n ID or           a plain string.</li></ul> |
| **Returns**                                          | <ul><li>An updated ID</li></ul> |

#### [popupParameters](#popupparameters)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.tangent.common.popupParameters(group, param, id, options) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sets up a new Popup Parameter for the Tangent |
| **Parameters**                                       | <ul><li>group - The Tangent Group.</li><li>param - The Parameter</li><li>id - The Tangent ID.</li><li>options - A table of options. The key for each option should be a number ID             (in the order it appears in the UI), and the value should be another             table with keys for <code>flexoID</code> and <code>i18n</code> values.</li></ul> |
| **Returns**                                          | <ul><li>An updated ID</li></ul> |

#### [popupSliderParameter](#popupsliderparameter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.tangent.common.popupSliderParameter(group, param, id, label, options, resetIndex) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sets up a new Popup Slider parameter for the Tangent |
| **Parameters**                                       | <ul><li>group - The Tangent Group.</li><li>param - The Parameter</li><li>id - The Tangent ID.</li><li>label - The label to be used by the Tangent. This can either be an i18n ID or           a plain string.</li><li>options - A table of options. The key for each option should be a number ID             (in the order it appears in the UI), and the value should be another             table with keys for <code>flexoID</code> and <code>i18n</code> values.</li><li>resetIndex - An index of which item to use when "reset" is triggered.</li></ul> |
| **Returns**                                          | <ul><li>An updated ID</li></ul> |

#### [radioButtonParameter](#radiobuttonparameter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.tangent.common.radioButtonParameter(group, param, id, label) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sets up a new Checkbox Parameter for the Tangent |
| **Parameters**                                       | <ul><li>group - The Tangent Group.</li><li>param - The Parameter</li><li>id - The Tangent ID.</li><li>label - The label to be used by the Tangent. This can either be an i18n ID or           a plain string.</li></ul> |
| **Returns**                                          | <ul><li>An updated ID</li></ul> |

#### [shortcutParameter](#shortcutparameter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.tangent.common.shortcutParameter(group, id, label, shortcutID) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sets up a new Final Cut Pro Shortcut Parameter for the Tangent. |
| **Parameters**                                       | <ul><li>group - The Tangent Group.</li><li>id - The Tangent ID.</li><li>label - The label to be used by the Tangent. This can either be an i18n ID or           a plain string.</li><li>shortcutID - The shortcut ID.</li></ul> |
| **Returns**                                          | <ul><li>An updated ID</li></ul> |

#### [sliderParameter](#sliderparameter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.tangent.common.sliderParameter(group, param, id, minValue, maxValue, stepSize, default, label, optionalParamA, optionalParamB) -> number, parameter` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sets up a new Slider Parameter |
| **Parameters**                                       | <ul><li>group - The Tangent Group</li><li>param - The Parameter</li><li>id - The Tangent ID</li><li>minValue - The minimum value</li><li>maxValue - The maximum value</li><li>stepSize - The step size</li><li>default - The default value</li><li>label - An optional label as an i18n ID or plain string. If no label is supplied the           <code>param</code> label will be used.</li><li>optionalParamA - An optional parameter. Useful if you need to link parameters.</li><li>optionalParamB - An optional parameter. Useful if you need to link parameters.</li></ul> |
| **Returns**                                          | <ul><li>An updated ID</li><li>The parameters value</li></ul> |

#### [volumeSliderParameter](#volumesliderparameter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.tangent.common.volumeSliderParameter(group, param, id, minValue, maxValue, stepSize, default, label) -> number, parameter` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sets up a new Volume Slider Parameter |
| **Parameters**                                       | <ul><li>group - The Tangent Group</li><li>param - The Parameter</li><li>id - The Tangent ID</li><li>minValue - The minimum value</li><li>maxValue - The maximum value</li><li>stepSize - The step size</li><li>default - The default value</li><li>label - An optional label as an i18n ID or plain string. If no label is supplied the           <code>param</code> label will be used.</li></ul> |
| **Returns**                                          | <ul><li>An updated ID</li><li>The parameters value</li></ul> |

#### [xyParameter](#xyparameter)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`plugins.finalcutpro.tangent.common.xyParameter(group, param, id, minValue, maxValue, stepSize) -> number` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sets up a new XY Parameter |
| **Parameters**                                       | <ul><li>group - The Tangent Group</li><li>param - The Parameter</li><li>id - The Tangent ID</li></ul> |
| **Returns**                                          | <ul><li>An updated ID</li><li>The <code>x</code> parameter value</li><li>The <code>y</code> parameter value</li><li>The xy binding</li></ul> |

