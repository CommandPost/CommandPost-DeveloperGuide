# [docs](index.md) » hs.host.locale
---

Retrieve information about the user's Language and Region settings.

Locales encapsulate information about linguistic, cultural, and technological conventions and standards. Examples of information encapsulated by a locale include the symbol used for the decimal separator in numbers and the way dates are formatted. Locales are typically used to provide, format, and interpret information about and according to the user’s customs and preferences.

## API Overview
* Functions - API calls offered directly by the extension
 * [availableLocales](#availablelocales)
 * [current](#current)
 * [details](#details)
 * [preferredLanguages](#preferredlanguages)
 * [registerCallback](#registercallback)
 * [unregisterCallback](#unregistercallback)

## API Documentation

### Functions

#### [availableLocales](#availablelocales)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.host.locale.availableLocales() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns an array table containing the identifiers for the locales available on the system. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>an array table of strings specifying the locale identifiers recognized by this system.</li></ul> |
| **Notes**                                            | <ul><li>these values can be used with <a href="#details">hs.host.locale.details</a> to get details for a specific locale.</li></ul> |

#### [current](#current)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.host.locale.current() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns an string specifying the user's currently selected locale identifier. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>a string specifying the identifier of the user's currently selected locale.</li></ul> |
| **Notes**                                            | <ul><li>this value can be used with <a href="#details">hs.host.locale.details</a> to get details for the returned locale.</li></ul> |

#### [details](#details)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.host.locale.details([identifier]) -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns a table containing information about the current or specified locale. |
| **Parameters**                                       | <ul><li><code>identifier</code> - an optional string, specifying the locale to display information about.  If you do not specify an identifier, information about eh user's currently selected locale is returned.</li></ul> |
| **Returns**                                          | <ul><li>a table containing one or more of the following key-value pairs:   * <code>alternateQuotationBeginDelimiterKey</code> - A string containing the alternating begin quotation symbol associated with the locale. In some locales, when quotations are nested, the quotation characters alternate.   * <code>alternateQuotationEndDelimiterKey</code>   - A string containing the alternate end quotation symbol associated with the locale. In some locales, when quotations are nested, the quotation characters alternate.   * <code>calendar</code>                            - A table containing key-value pairs describing for calendar associated with the locale. The table will contain one or more of the following pairs:     * <code>AMSymbol</code>                          - The AM symbol for time in the locale's calendar.     * <code>calendarIdentifier</code>                - A string representing the calendar identity.     * <code>eraSymbols</code>                        - An array table of strings specifying the names of the eras as recognized in the locale's calendar.     * <code>firstWeekday</code>                      - The index in <code>weekdaySymbols</code> of the first weekday in the locale's calendar.     * <code>longEraSymbols</code>                    - An array table of strings specifying long names of the eras as recognized in the locale's calendar.     * <code>minimumDaysInFirstWeek</code>            - The minimum number of days, an integer value, in the first week in the locale's calendar.     * <code>monthSymbols</code>                      - An array table of strings for the months of the year in the locale's calendar.     * <code>PMSymbol</code>                          - The PM symbol for time in the locale's calendar.     * <code>quarterSymbols</code>                    - An array table of strings for the quarters of the year in the locale's calendar.     * <code>shortMonthSymbols</code>                 - An array table of short strings for the months of the year in the locale's calendar.     * <code>shortQuarterSymbols</code>               - An array table of short strings for the quarters of the year in the locale's calendar.     * <code>shortStandaloneMonthSymbols</code>       - An array table of short standalone strings for the months of the year in the locale's calendar.     * <code>shortStandaloneQuarterSymbols</code>     - An array table of short standalone strings for the quarters of the year in the locale's calendar.     * <code>shortStandaloneWeekdaySymbols</code>     - An array table of short standalone strings for the days of the week in the locale's calendar.     * <code>shortWeekdaySymbols</code>               - An array table of short strings for the days of the week in the locale's calendar.     * <code>standaloneMonthSymbols</code>            - An array table of standalone strings for the months of the year in the locale's calendar.     * <code>standaloneQuarterSymbols</code>          - An array table of standalone strings for the quarters of the year in the locale's calendar.     * <code>standaloneWeekdaySymbols</code>          - An array table of standalone strings for the days of the week in the locale's calendar.     * <code>veryShortMonthSymbols</code>             - An array table of very short strings for the months of the year in the locale's calendar.     * <code>veryShortStandaloneMonthSymbols</code>   - An array table of very short standalone strings for the months of the year in the locale's calendar.     * <code>veryShortStandaloneWeekdaySymbols</code> - An array table of very short standalone strings for the days of the week in the locale's calendar.     * <code>veryShortWeekdaySymbols</code>           - An array table of very short strings for the days of the week in the locale's calendar.     * <code>weekdaySymbols</code>                    - An array table of strings for the days of the week in the locale's calendar.   * <code>collationIdentifier</code>                 - A string containing the collation associated with the locale.   * <code>collatorIdentifier</code>                  - A string containing the collation identifier for the locale.   * <code>countryCode</code>                         - A string containing the locale country code.   * <code>currencyCode</code>                        - A string containing the currency code associated with the locale.   * <code>currencySymbol</code>                      - A string containing the currency symbol associated with the locale.   * <code>decimalSeparator</code>                    - A string containing the decimal separator associated with the locale.   * <code>exemplarCharacterSet</code>                - An array table of strings which make up the exemplar character set for the locale.   * <code>groupingSeparator</code>                   - A string containing the numeric grouping separator associated with the locale.   * <code>identifier</code>                          - A string containing the locale identifier.   * <code>languageCode</code>                        - A string containing the locale language code.   * <code>measurementSystem</code>                   - A string containing the measurement system associated with the locale.   * <code>quotationBeginDelimiterKey</code>          - A string containing the begin quotation symbol associated with the locale.   * <code>quotationEndDelimiterKey</code>            - A string containing the end quotation symbol associated with the locale.   * <code>scriptCode</code>                          - A string containing the locale script code.   * <code>temperatureUnit</code>                     - A string containing the preferred measurement system for temperature.   * <code>timeFormatIs24Hour</code>                  - A boolean specifying whether time is expressed in a 24 hour format (true) or 12 hour format (false).   * <code>usesMetricSystem</code>                    - A boolean specifying whether or not the locale uses the metric system.   * <code>variantCode</code>                         - A string containing the locale variant code.</li></ul> |
| **Notes**                                            | <ul><li>If you specify a locale identifier as an argument, it should be based on one of the strings returned by <a href="#availableLocales">hs.host.locale.availableLocales</a>.  Use of an arbitrary string may produce unreliable or inconsistent results.</li></ul> |

#### [preferredLanguages](#preferredlanguages)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.host.locale.preferredLanguages() -> table` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the user's language preference order as an array of strings. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>an array table of strings specifying the user's preferred languages as string identifiers.</li></ul> |

#### [registerCallback](#registercallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.host.locale.registerCallback(function) -> uuidString` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Registers a function to be invoked when anything in the user's locale settings change |
| **Parameters**                                       | <ul><li><code>fn</code> - the function to be invoked when a setting changes</li></ul> |
| **Returns**                                          | <ul><li>a uuid string which can be used to unregister a callback function when you no longer require notification of changes</li></ul> |
| **Notes**                                            | <ul><li>The callback function will not receive any arguments and should return none.  You can retrieve the new locale settings with <a href="#localeInformation">hs.host.locale.localeInformation</a> and check its keys to determine if the change is of interest.</li></ul> |

#### [unregisterCallback](#unregistercallback)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.host.locale.unregisterCallback(uuidString) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Unregister a callback function when you no longer care about changes to the user's locale |
| **Parameters**                                       | <ul><li><code>uuidString</code> - the uuidString returned by <a href="#registerCallback">hs.host.locale.registerCallback</a> when you registered the callback function</li></ul> |
| **Returns**                                          | <ul><li>true if the callback was successfully unregistered or false if it was not, usually because the uuidString does not correspond to a current callback function.</li></ul> |

