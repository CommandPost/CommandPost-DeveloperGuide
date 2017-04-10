# [docs](index.md) » hs.host
---

Inspect information about the machine Hammerspoon is running on

Notes:
 * The network/hostname calls can be slow, as network resolution calls can be called, which are synchronous and will block Hammerspoon until they complete.

## API Overview
* Functions - API calls offered directly by the extension
 * [addresses](#addresses)
 * [cpuUsage](#cpuUsage)
 * [cpuUsageTicks](#cpuUsageTicks)
 * [globallyUniqueString](#globallyUniqueString)
 * [interfaceStyle](#interfaceStyle)
 * [localizedName](#localizedName)
 * [names](#names)
 * [operatingSystemVersion](#operatingSystemVersion)
 * [operatingSystemVersionString](#operatingSystemVersionString)
 * [uuid](#uuid)
 * [vmStat](#vmStat)
 * [volumeInformation](#volumeInformation)

## API Documentation
### Functions

#### [addresses](#addresses)
|             |                 |
| ------------|-----------------|
| Signature   | hs.host.addresses() -> table  |
| Type        | Function |
| Description | Gets a list of network addresses for the current machine |
| Parameters |  * None |
| Returns |  * A table of strings containing the network addresses of the current machine |
| Notes |  * The results will include IPv4 and IPv6 addresses

#### [cpuUsage](#cpuUsage)
|             |                 |
| ------------|-----------------|
| Signature   | hs.host.cpuUsage([period], [callback]) -> table  |
| Type        | Function |
| Description | Query CPU usage statistics for a given time interval using [hs.host.cpuUsageTicks](#cpuUsageTicks) and return the results as percentages. |
| Parameters |  * `period`    - an optional value specifying the time between samples collected for calculating CPU usage statistics.   * If `callback` is not provided, this is an optional integer, default 100000, specifying the number of microseconds to block between samples collected.  Note that Hammerspoon will block for this period of time during execution of this function.   * If `callback` is provided, this is an optional number, default 1.0, specifying the number of seconds between samples collected.  Hammerspoon will *not* block during this time period. * `callback` - an optional callback function which will receive the cpu usage statistics in a table, described below, as its sole argument. |
| Returns |  * If a callback function is not provided, this function will return a table containing the following:   * Individual tables, indexed by the core number, for each CPU core with the following keys in each subtable:     * user   -- percentage of CPU time occupied by user level processes.     * system -- percentage of CPU time occupied by system (kernel) level processes.     * nice   -- percentage of CPU time occupied by user level processes with a positive nice value. (See notes below)     * active -- For convenience, when you just want the total CPU usage, this is the sum of user, system, and nice.     * idle   -- percentage of CPU time spent idle   * The key `overall` containing the same keys as described above but based upon the average of all cores combined.   * The key `n` containing the number of cores detected. * If a callback function is provided, this function will return a placeholder table with the following metamethods:   * `hs.host.cpuUsage:finished()` - returns a boolean indicating if the second CPU sample has been collected yet (true) or not (false).   * `hs.host.cpuUsage:stop()`     - abort the sample collection.  The callback function will not be invoked.   * The results of the cpu statistics will be submitted as a table, described above, to the callback function. |
| Notes |  * If no callback function is provided, Hammerspoon will block (i.e. no other Hammerspoon activity can occur) during execution of this function for `period` microseconds (1 second = 1,000,000 microseconds).  The default period is 1/10 of a second. If `period` is too small, it is possible that some of the CPU statistics may result in `nan` (not-a-number).

#### [cpuUsageTicks](#cpuUsageTicks)
|             |                 |
| ------------|-----------------|
| Signature   | hs.host.cpuUsageTicks() -> table  |
| Type        | Function |
| Description | Returns a table containing the current cpu usage information for the system in `ticks` since the most recent system boot. |
| Parameters |  * None |
| Returns |  * A table containing the following:   * Individual tables, indexed by the core number, for each CPU core with the following keys in each subtable:     * user   -- number of ticks the cpu core has spent in user mode since system startup.     * system -- number of ticks the cpu core has spent in system mode since system startup.     * nice        * active -- For convenience, when you just want the total CPU usage, this is the sum of user, system, and nice.     * idle   -- number of ticks the cpu core has spent idle   * The key `overall` containing the same keys as described above but based upon the combined total of all cpu cores for the system.   * The key `n` containing the number of cores detected. |
| Notes |  * CPU mode ticks are updated during system interrupts and are incremented based upon the mode the CPU is in at the time of the interrupt. By its nature, this is always going to be approximate, and a single call to this function will return the current tick values since the system was last rebooted. * To generate a snapshot of the system's usage "at this moment", you must take two samples and calculate the difference between them.  The [hs.host.cpuUsage](#cpuUsage) function is a wrapper which does this for you and returns the cpu usage statistics as a percentage of the total number of ticks which occurred during the sample period you specify when invoking `hs.host.cpuUsage`.

#### [globallyUniqueString](#globallyUniqueString)
|             |                 |
| ------------|-----------------|
| Signature   | hs.host.globallyUniqueString() -> string  |
| Type        | Function |
| Description | Returns a newly generated global unique identifier as a string |
| Parameters |  * None |
| Returns |  * a newly generated global unique identifier as a string |
| Notes |  * See also `hs.host.uuid` * The global unique identifier for a process includes the host name, process ID, and a time stamp, which ensures that the ID is unique for the network. This property generates a new string each time it is invoked, and it uses a counter to guarantee that strings are unique. * This is often used as a file or directory name in conjunction with `hs.host.temporaryDirectory()` when creating temporary files.

#### [interfaceStyle](#interfaceStyle)
|             |                 |
| ------------|-----------------|
| Signature   | hs.host.interfaceStyle() -> string  |
| Type        | Function |
| Description | Returns the OS X interface style for the current user. |
| Parameters |  * None |
| Returns |  * A string representing the current user interface style, or nil if the default style is in use. |
| Notes |  * As of OS X 10.10.4, other than the default style, only "Dark" is recognized as a valid style.

#### [localizedName](#localizedName)
|             |                 |
| ------------|-----------------|
| Signature   | hs.host.localizedName() -> string  |
| Type        | Function |
| Description | Gets the name of the current machine, as displayed in the Finder sidebar |
| Parameters |  * None |
| Returns |  * A string containing the name of the current machine |


#### [names](#names)
|             |                 |
| ------------|-----------------|
| Signature   | hs.host.names() -> table  |
| Type        | Function |
| Description | Gets a list of network names for the current machine |
| Parameters |  * None |
| Returns |  * A table of strings containing the network names of the current machine |
| Notes |  * This function should be used sparingly, as it may involve blocking network access to resolve hostnames

#### [operatingSystemVersion](#operatingSystemVersion)
|             |                 |
| ------------|-----------------|
| Signature   | hs.host.operatingSystemVersion() -> table  |
| Type        | Function |
| Description | The operating system version as a table containing the major, minor, and patch numbers. |
| Parameters |  * None |
| Returns |  * The operating system version as a table containing the keys major, minor, and patch corresponding to the version number determined and a key named "exact" or "approximation" depending upon the method used to determine the OS Version information. |
| Notes |  * Prior to 10.10 (Yosemite), there was no definitive way to reliably get an exact OS X version number without either mapping it to the Darwin kernel version, mapping it to the AppKitVersionNumber (the recommended method), or parsing the result of NSProcessingInfo's `operatingSystemVersionString` selector, which Apple states is not guaranteed to be reliably parseable.   * for OS X versions prior to 10.10, the version number is approximately determined by evaluating the AppKitVersionNumber.  For these operating systems, the `approximate` key is defined and set to true, as the exact patch level cannot be definitively determined.   * for OS X Versions starting at 10.10 and going forward, an exact value for the version number can be determined with NSProcessingInfo's `operatingSystemVersion` selector and the `exact` key is defined and set to true if this method is used.

#### [operatingSystemVersionString](#operatingSystemVersionString)
|             |                 |
| ------------|-----------------|
| Signature   | hs.host.operatingSystemVersionString() -> string  |
| Type        | Function |
| Description | The operating system version as a human readable string. |
| Parameters |  * None |
| Returns |  * The operating system version as a human readable string. |
| Notes |  * According to the OS X Developer documentation, "The operating system version string is human readable, localized, and is appropriate for displaying to the user. This string is not appropriate for parsing."

#### [uuid](#uuid)
|             |                 |
| ------------|-----------------|
| Signature   | hs.host.uuid() -> string  |
| Type        | Function |
| Description | Returns a newly generated UUID as a string |
| Parameters |  * None |
| Returns |  * a newly generated UUID as a string |
| Notes |  * See also `hs.host.globallyUniqueString` * UUIDs (Universally Unique Identifiers), also known as GUIDs (Globally Unique Identifiers) or IIDs (Interface Identifiers), are 128-bit values. UUIDs created by NSUUID conform to RFC 4122 version 4 and are created with random bytes.

#### [vmStat](#vmStat)
|             |                 |
| ------------|-----------------|
| Signature   | hs.host.vmStat() -> table  |
| Type        | Function |
| Description | Returns a table containing virtual memory statistics for the current machine, as well as the page size (in bytes) and physical memory size (in bytes). |
| Parameters |  * None |
| Returns |  * A table containing the following keys:   * anonymousPages          -- the total number of pages that are anonymous   * cacheHits               -- number of object cache hits   * cacheLookups            -- number of object cache lookups   * fileBackedPages         -- the total number of pages that are file-backed (non-swap)   * memSize                 -- physical memory size in bytes   * pageIns                 -- the total number of requests for pages from a pager (such as the inode pager).   * pageOuts                -- the total number of pages that have been paged out.   * pageSize                -- page size in bytes   * pagesActive             -- the total number of pages currently in use and pageable.   * pagesCompressed         -- the total number of pages that have been compressed by the VM compressor.   * pagesCopyOnWrite        -- the number of faults that caused a page to be copied (generally caused by copy-on-write faults).   * pagesDecompressed       -- the total number of pages that have been decompressed by the VM compressor.   * pagesFree               -- the total number of free pages in the system.   * pagesInactive           -- the total number of pages on the inactive list.   * pagesPurgeable          -- the total number of purgeable pages.   * pagesPurged             -- the total number of pages that have been purged.   * pagesReactivated        -- the total number of pages that have been moved from the inactive list to the active list (reactivated).   * pagesSpeculative        -- the total number of pages on the speculative list.   * pagesThrottled          -- the total number of pages on the throttled list (not wired but not pageable).   * pagesUsedByVMCompressor -- the number of pages used to store compressed VM pages.   * pagesWiredDown          -- the total number of pages wired down. That is, pages that cannot be paged out.   * pagesZeroFilled         -- the total number of pages that have been zero-filled on demand.   * swapIns                 -- the total number of compressed pages that have been swapped out to disk.   * swapOuts                -- the total number of compressed pages that have been swapped back in from disk.   * translationFaults       -- the number of times the "vm_fault" routine has been called.   * uncompressedPages       -- the total number of pages (uncompressed) held within the compressor |
| Notes |  * The table returned has a __tostring() metamethod which allows listing it's contents in the Hammerspoon console by typing `hs.host.vmStats()`. * Except for the addition of cacheHits, cacheLookups, pageSize and memSize, the results for this function should be identical to the OS X command `vm_stat`. * Adapted primarily from the source code to Apple's vm_stat command located at http://www.opensource.apple.com/source/system_cmds/system_cmds-643.1.1/vm_stat.tproj/vm_stat.c

#### [volumeInformation](#volumeInformation)
|             |                 |
| ------------|-----------------|
| Signature   | hs.host.volumeInformation([showHidden]) -> table  |
| Type        | Function |
| Description | Returns a table of information about disk volumes attached to the system |
| Parameters |  * showHidden - An optional boolean, true to show hidden volumes, false to not show hidden volumes. Defaults to false. |
| Returns |  * A table of information, where the keys are the paths of disk volumes |
| Notes |  * The possible keys in the table are:  * NSURLVolumeTotalCapacityKey - Size of the volume in bytes  * NSURLVolumeAvailableCapacityKey - Available space on the volume in bytes  * NSURLVolumeIsAutomountedKey - Boolean indicating if the volume was automounted  * NSURLVolumeIsBrowsableKey - Boolean indicating if the volume can be browsed  * NSURLVolumeIsEjectableKey - Boolean indicating if the volume can be ejected  * NSURLVolumeIsInternalKey - Boolean indicating if the volume is an internal drive or an external drive  * NSURLVolumeIsLocalKey - Boolean indicating if the volume is a local or remote drive  * NSURLVolumeIsReadOnlyKey - Boolean indicating if the volume is read only  * NSURLVolumeIsRemovableKey - Boolean indicating if the volume is removable  * NSURLVolumeMaximumFileSizeKey - Maximum file size the volume can support, in bytes  * NSURLVolumeUUIDStringKey - The UUID of volume's filesystem  * NSURLVolumeURLForRemountingKey - For remote volumes, the network URL of the volume  * NSURLVolumeLocalizedNameKey - Localized version of the volume's name  * NSURLVolumeNameKey - The volume's name  * NSURLVolumeLocalizedFormatDescriptionKey - Localized description of the volume* Not all keys will be present for all volumes |
