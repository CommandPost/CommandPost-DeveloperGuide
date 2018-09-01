# [docs](index.md) » hs.fs
---

Access/inspect the filesystem

Home: http://keplerproject.github.io/luafilesystem

This module is produced by the Kepler Project under the name "Lua File System"

## Submodules
 * [hs.fs.volume](hs.fs.volume.md)
 * [hs.fs.xattr](hs.fs.xattr.md)

## API Overview
* Functions - API calls offered directly by the extension
 * [attributes](#attributes)
 * [chdir](#chdir)
 * [currentDir](#currentdir)
 * [dir](#dir)
 * [displayName](#displayname)
 * [fileUTI](#fileuti)
 * [fileUTIalternate](#fileutialternate)
 * [getFinderComments](#getfindercomments)
 * [link](#link)
 * [lock](#lock)
 * [lockDir](#lockdir)
 * [mkdir](#mkdir)
 * [pathToAbsolute](#pathtoabsolute)
 * [rmdir](#rmdir)
 * [setFinderComments](#setfindercomments)
 * [symlinkAttributes](#symlinkattributes)
 * [tagsAdd](#tagsadd)
 * [tagsGet](#tagsget)
 * [tagsRemove](#tagsremove)
 * [tagsSet](#tagsset)
 * [temporaryDirectory](#temporarydirectory)
 * [touch](#touch)
 * [unlock](#unlock)

## API Documentation

### Functions

#### [attributes](#attributes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fs.attributes(filepath [, aName]) -> table or string or nil,error` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets the attributes of a file |
| **Parameters**                                       | <ul><li>filepath - A string containing the path of a file to inspect</li><li>aName - An optional attribute name. If this value is specified, only the attribute requested, is returned</li></ul> |
| **Returns**                                          | <ul><li>A table with the file attributes corresponding to filepath (or nil followed by an error message in case of error). If the second optional argument is given, then a string is returned with the value of the named attribute. attribute mode is a string, all the others are numbers, and the time related attributes use the same time reference of os.time:</li><li>dev - A number containing the device the file resides on</li><li>ino - A number containing the inode of the file</li><li>mode - A string containing the type of the file (possible values are: file, directory, link, socket, named pipe, char device, block device or other)</li><li>nlink - A number containing a count of hard links to the file</li><li>uid - A number containing the user-id of owner</li><li>gid - A number containing the group-id of owner</li><li>rdev - A number containing the type of device, for files that are char/block devices</li><li>access - A number containing the time of last access modification (as seconds since the UNIX epoch)</li><li>change - A number containing the time of last file status change (as seconds since the UNIX epoch)</li><li>modification - A number containing the time of the last file contents change (as seconds since the UNIX epoch)</li><li>creation - A number containing the time the file was created (as seconds since the UNIX epoch)</li><li>size - A number containing the file size, in bytes</li><li>blocks - A number containing the number of blocks allocated for file</li><li>blksize - A number containing the optimal file system I/O blocksize</li></ul> |
| **Notes**                                            | <ul><li>This function uses <code>stat()</code> internally thus if the given filepath is a symbolic link, it is followed (if it points to another link the chain is followed recursively) and the information is about the file it refers to. To obtain information about the link itself, see function <code>hs.fs.symlinkAttributes()</code></li></ul> |

#### [chdir](#chdir)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fs.chdir(path) -> true or (nil,error)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Changes the current working directory to the given path. |
| **Parameters**                                       | <ul><li>path - A string containing the path to change working directory to</li></ul> |
| **Returns**                                          | <ul><li>If successful, returns true, otherwise returns nil and an error string</li></ul> |

#### [currentDir](#currentdir)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fs.currentDir() -> string or (nil,error)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets the current working directory |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string containing the current working directory, or if an error occured, nil and an error string</li></ul> |

#### [dir](#dir)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fs.dir(path) -> iter_fn, dir_obj` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Creates an iterator for walking a filesystem path |
| **Parameters**                                       | <ul><li>path - A string containing a directory to iterate</li></ul> |
| **Returns**                                          | <ul><li>An iterator function or <code>nil</code> if the supplied path cannot be iterated</li><li>A data object to pass to the iterator function or an error message as a string</li></ul> |
| **Notes**                                            | <ul><li>The data object should be passed to the iterator function. Each call will return either a string containing the name of an entry in the directory, or <code>nil</code> if there are no more entries.</li><li>Iteration can also be performed by calling <code>:next()</code> on the data object. Note that if you do this, you must call <code>:close()</code> on the object when you have finished.</li><li>The iterator function will return <code>nil</code> if the supplied path cannot be iterated, as well as the error message as a string.</li><li>Example Usage:   <code>local iterFn, dirObj = hs.fs.dir("/Users/Guest/Documents")      if iterFn then         for file in iterFn, dirObj do            print(file)         end      else         print(string.format("The following error occurred: %s", dirObj))      end</code></li></ul> |

#### [displayName](#displayname)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fs.displayName(filepath) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the display name of the file or directory at a specified path. |
| **Parameters**                                       | <ul><li>filepath - The path to the file or directory</li></ul> |
| **Returns**                                          | <ul><li>a string containing the display name of the file or directory at a specified path; returns nil if no file with the specified path exists.</li></ul> |

#### [fileUTI](#fileuti)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fs.fileUTI(path) -> string or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the Uniform Type Identifier for the file location specified. |
| **Parameters**                                       | <ul><li>path - the path to the file to return the UTI for.</li></ul> |
| **Returns**                                          | <ul><li>a string containing the Uniform Type Identifier for the file location specified or nil if an error occured</li></ul> |

#### [fileUTIalternate](#fileutialternate)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fs.fileUTIalternate(fileUTI, type) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the fileUTI's equivalent form in an alternate type specification format. |
| **Parameters**                                       | <ul><li>a string containing a file UTI, such as one returned by <code>hs.fs.fileUTI</code>.</li><li>a string specifying the alternate format for the UTI.  This string may be one of the following:<ul><li><code>extension</code>  - as a file extension, commonly used for platform independant file sharing when file metadata can't be guaranteed to be cross-platform compatible.  Generally considered unreliable when other file type identification methods are available.</li></ul></li><li><code>mime</code>       - as a mime-type, commonly used by Internet applications like web browsers and email applications.</li><li><code>pasteboard</code> - as an NSPasteboard type (see <code>hs.pasteboard</code>).</li><li><code>ostype</code>     - four character file type, most common pre OS X, but still used in some legacy APIs.</li></ul> |
| **Returns**                                          | <ul><li>the file UTI in the alternate format or nil if the UTI does not have an alternate of the specified type.</li></ul> |

#### [getFinderComments](#getfindercomments)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fs.getFinderComments(path) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Get the Finder comments for the file or directory at the specified path |
| **Parameters**                                       | <ul><li>path - the path to the file or directory you wish to get the comments of</li></ul> |
| **Returns**                                          | <ul><li>a string containing the Finder comments for the file or directory specified.  If no comments have been set for the file, returns an empty string.  If an error occurs, most commonly an invalid path, this function will throw a Lua error.</li></ul> |
| **Notes**                                            | <ul><li>This function uses <code>hs.osascript</code> to access the file comments through AppleScript</li></ul> |

#### [link](#link)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fs.link(old, new[, symlink]) -> true or (nil,error)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Creates a link |
| **Parameters**                                       | <ul><li>old - A string containing a path to a filesystem object to link from</li><li>new - A string containing a path to create the link at</li><li>symlink - An optional boolean, true to create a symlink, false to create a hard link. Defaults to false</li></ul> |
| **Returns**                                          | <ul><li>True if the link was created, otherwise nil and an error string</li></ul> |

#### [lock](#lock)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fs.lock(filehandle, mode[, start[, length]]) -> true or (nil,error)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Locks a file, or part of it |
| **Parameters**                                       | <ul><li>filehandle - An open file</li><li>mode - A string containing either "r" for a shared read lock, or "w" for an exclusive write lock</li><li>start - An optional number containing an offset into the file to start the lock at. Defaults to 0</li><li>length - An optional number containing the length of the file to lock. Defaults to the full size of the file</li></ul> |
| **Returns**                                          | <ul><li>True if the lock was obtained successfully, otherwise nil and an error string</li></ul> |

#### [lockDir](#lockdir)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fs.lockDir(path, [seconds_stale]) -> lock or (nil,error)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Locks a directory |
| **Parameters**                                       | <ul><li>path - A string containing the path to a directory</li><li>seconds_stale - An optional number containing an age (in seconds) beyond which to consider an existing lock as stale. Defaults to INT_MAX (which is, broadly speaking, equivalent to "never")</li></ul> |
| **Returns**                                          | <ul><li>If successful, a lock object, otherwise nil and an error string</li></ul> |
| **Notes**                                            | <ul><li>This is not a low level OS feature, the lock is actually a file created in the path, called <code>lockfile.lfs</code>, so the directory must be writable for this function to succeed</li><li>The returned lock object can be freed with <code>lock:free()</code></li><li>If the lock already exists and is not stale, the error string returned will be "File exists"</li></ul> |

#### [mkdir](#mkdir)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fs.mkdir(dirname) -> true or (nil,error)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Creates a new directory |
| **Parameters**                                       | <ul><li>dirname - A string containing the path of a directory to create</li></ul> |
| **Returns**                                          | <ul><li>True if the directory was created, otherwise nil and an error string</li></ul> |

#### [pathToAbsolute](#pathtoabsolute)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fs.pathToAbsolute(filepath) -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets the absolute path of a given path |
| **Parameters**                                       | <ul><li>filepath - Any kind of file or directory path, be it relative or not</li></ul> |
| **Returns**                                          | <ul><li>A string containing the absolute path of <code>filepath</code> (i.e. one that doesn't intolve <code>.</code>, <code>..</code> or symlinks)</li><li>Note that symlinks will be resolved to their target file</li></ul> |

#### [rmdir](#rmdir)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fs.rmdir(dirname) -> true or (nil,error)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Removes an existing directory |
| **Parameters**                                       | <ul><li>dirname - A string containing the path to a directory to remove</li></ul> |
| **Returns**                                          | <ul><li>True if the directory was removed, otherwise nil and an error string</li></ul> |

#### [setFinderComments](#setfindercomments)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fs.setFinderComments(path, comment) -> boolean` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Set the Finder comments for the file or directory at the specified path to the comment specified |
| **Parameters**                                       | <ul><li>path    - the path to the file or directory you wish to set the comments of</li><li>comment - a string specifying the comment to set.  If this parameter is missing or is an explicit nil, the existing comment is cleared.</li></ul> |
| **Returns**                                          | <ul><li>true on success; on error, most commonly an invalid path, this function will throw a Lua error.</li></ul> |
| **Notes**                                            | <ul><li>This function uses <code>hs.osascript</code> to access the file comments through AppleScript</li></ul> |

#### [symlinkAttributes](#symlinkattributes)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fs.symlinkAttributes (filepath [, aname]) -> table or string or nil,error` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets the attributes of a symbolic link |
| **Parameters**                                       | <ul><li>filepath - A string containing the path of a link to inspect</li><li>aName - An optional attribute name. If this value is specified, only the attribute requested, is returned</li></ul> |
| **Returns**                                          | <ul><li>A table or string if the values could be found, otherwise nil and an error string.</li></ul> |
| **Notes**                                            | <ul><li>The return values for this function are identical to those provided by <code>hs.fs.attributes()</code></li></ul> |

#### [tagsAdd](#tagsadd)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fs.tagsAdd(filepath, tags)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Adds one or more tags to the Finder tags of a file |
| **Parameters**                                       | <ul><li>filepath - A string containing the path of a file</li><li>tags - A table containing one or more strings, each containing a tag name</li></ul> |
| **Returns**                                          | <ul><li>true if the tags were updated; throws a lua error if an error occurs updating the tags</li></ul> |

#### [tagsGet](#tagsget)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fs.tagsGet(filepath) -> table or nil` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Gets the Finder tags of a file |
| **Parameters**                                       | <ul><li>filepath - A string containing the path of a file</li></ul> |
| **Returns**                                          | <ul><li>A table containing the list of the file's tags, or nil if the file has no tags assigned; throws a lua error if an error accessing the file occurs</li></ul> |

#### [tagsRemove](#tagsremove)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fs.tagsRemove(filepath, tags)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Removes Finder tags from a file |
| **Parameters**                                       | <ul><li>filepath - A string containing the path of a file</li><li>tags - A table containing one or more strings, each containing a tag name</li></ul> |
| **Returns**                                          | <ul><li>true if the tags were updated; throws a lua error if an error occurs updating the tags</li></ul> |

#### [tagsSet](#tagsset)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fs.tagsSet(filepath, tags)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Sets the Finder tags of a file, removing any that are already set |
| **Parameters**                                       | <ul><li>filepath - A string containing the path of a file</li><li>tags - A table containing zero or more strings, each containing a tag name</li></ul> |
| **Returns**                                          | <ul><li>true if the tags were set; throws a lua error if an error occurs setting the new tags</li></ul> |

#### [temporaryDirectory](#temporarydirectory)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fs.temporaryDirectory() -> string` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Returns the path of the temporary directory for the current user. |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The path to the system designated temporary directory for the current user.</li></ul> |

#### [touch](#touch)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fs.touch(filepath [, atime [, mtime]]) -> true or (nil,error)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Updates the access and modification times of a file |
| **Parameters**                                       | <ul><li>filepath - A string containing the path of a file to touch</li><li>atime - An optional number containing the new access time of the file to set (as seconds since the Epoch). Defaults to now</li><li>mtime - An optional number containing the new modification time of the file to set (as seconds since the Epoch). Defaults to the value of atime</li></ul> |
| **Returns**                                          | <ul><li>True if the operation was successful, otherwise nil and an error string</li></ul> |

#### [unlock](#unlock)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.fs.unlock(filehandle[, start[, length]]) -> true or (nil,error)` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function |
| **Description**                                      | Unlocks a file or a part of it. |
| **Parameters**                                       | <ul><li>filehandle - An open file</li><li>start - An optional number containing an offset from the start of the file, to unlock. Defaults to 0</li><li>length - An optional number containing the length of file to unlock. Defaults to the full size of the file</li></ul> |
| **Returns**                                          | <ul><li>True if the unlock succeeded, otherwise nil and an error string</li></ul> |

