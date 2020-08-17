# [docs](index.md) » cp.apple.finalcutpro.main.FindAndReplaceTitleText
---

Represents a "Find and Replace Title Text" dialogue box.

## API Overview
* Constructors - API calls which return an object, typically one that offers API methods
 * [FindAndReplaceTitleText](#findandreplacetitletext)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [findText](#findtext)
 * [loopSearch](#loopsearch)
 * [matchCase](#matchcase)
 * [next](#next)
 * [previous](#previous)
 * [replace](#replace)
 * [replaceAll](#replaceall)
 * [replaceAndFind](#replaceandfind)
 * [replaceText](#replacetext)
 * [searchIn](#searchin)
 * [wholeWords](#wholewords)
* Methods - API calls which can only be made on an object returned by a constructor
 * [doFindAndReplaceAll](#dofindandreplaceall)
 * [doHide](#dohide)
 * [doShow](#doshow)

## API Documentation

### Constructors

#### [FindAndReplaceTitleText](#findandreplacetitletext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.FindAndReplaceTitleText(cpApp, upProp)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Constructor |
| **Description**                                      | Creates a new "Find and Replace Title Text" [Dialog](cp.ui.Dialog.md) |

### Fields

#### [findText](#findtext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.FindAndReplaceTitleText.findText <cp.ui.TextField>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Find" search field, as a [TextField](cp.ui.TextField.md) |

#### [loopSearch](#loopsearch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.FindAndReplaceTitleText.loopSearch <cp.ui.CheckBox>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Loop search" [CheckBox](cp.ui.CheckBox.md). |

#### [matchCase](#matchcase)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.FindAndReplaceTitleText.matchCase <cp.ui.CheckBox>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Match case" [CheckBox](cp.ui.CheckBox.md). |

#### [next](#next)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.FindAndReplaceTitleText.next <cp.ui.Button>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Next" [Button](cp.ui.Button.md). |

#### [previous](#previous)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.FindAndReplaceTitleText.previous <cp.ui.Button>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Previous" [Button](cp.ui.Button.md). |

#### [replace](#replace)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.FindAndReplaceTitleText.replace <cp.ui.Button>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Replace" [Button](cp.ui.Button.md). |

#### [replaceAll](#replaceall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.FindAndReplaceTitleText.replaceAll <cp.ui.Button>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Replace All" [Button](cp.ui.Button.md). |

#### [replaceAndFind](#replaceandfind)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.FindAndReplaceTitleText.replaceAndFind <cp.ui.Button>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Replace & Find" [Button](cp.ui.Button.md). |

#### [replaceText](#replacetext)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.FindAndReplaceTitleText.replaceText <cp.ui.TextField>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Replace" search field, as a [TextField](cp.ui.TextField.md) |

#### [searchIn](#searchin)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.FindAndReplaceTitleText.searchIn <cp.ui.PopUpButton>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Search In" [PopUpButton](cp.ui.PopUpButton.md). |

#### [wholeWords](#wholewords)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.FindAndReplaceTitleText.wholeWords <cp.ui.CheckBox>` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Field |
| **Description**                                      | The "Whole words" [CheckBox](cp.ui.CheckBox.md). |

### Methods

#### [doFindAndReplaceAll](#dofindandreplaceall)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.FindAndReplaceTitleText:doFindAndReplaceAll(find, replace) -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will attempt to find all titles containing `find` and replace them with `replace`. |

#### [doHide](#dohide)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.FindAndReplaceTitleText:doHide() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will attempt to hide the "Find And Replace Title Text" dialog. |

#### [doShow](#doshow)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`cp.apple.finalcutpro.main.FindAndReplaceTitleText:doShow() -> cp.rx.go.Statement` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Method |
| **Description**                                      | A [Statement](cp.rx.go.Statement.md) that will attempt to show the "Find And Replace Title Text" dialog. |

