# [docs](index.md) » hs.fs
---

Access/inspect the filesystem

Home: http://keplerproject.github.io/luafilesystem

This module is produced by the Kepler Project under the name "Lua File System"

## Submodules
 * [hs.fs.volume](hs.fs.volume.md)

## API Overview
* Functions - API calls offered directly by the extension
 * [attributes](#attributes)
 * [chdir](#chdir)
 * [currentDir](#currentdir)
 * [dir](#dir)
 * [fileUTI](#fileuti)
 * [fileUTIalternate](#fileutialternate)
 * [link](#link)
 * [lock](#lock)
 * [lockDir](#lockdir)
 * [mkdir](#mkdir)
 * [pathToAbsolute](#pathtoabsolute)
 * [rmdir](#rmdir)
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
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.fs.attributes(filepath [, aName]) -> table or string or nil,error` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the attributes of a file                                                                                         |
| **Parameters**                                       | <ul><li>filepath - A string containing the path of a file to inspect</li><li>aName - An optional attribute name. If this value is specified, only the attribute requested, is returned</li></ul> |
| **Returns**                                          | <ul><li>A table with the file attributes corresponding to filepath (or nil followed by an error message in case of error). If the second optional argument is given, then a string is returned with the value of the named attribute. attribute mode is a string, all the others are numbers, and the time related attributes use the same time reference of os.time:</li><li> dev - A number containing the device the file resides on</li><li> ino - A number containing the inode of the file</li><li> mode - A string containing the type of the file (possible values are: file, directory, link, socket, named pipe, char device, block device or other)</li><li> nlink - A number containing a count of hard links to the file</li><li> uid - A number containing the user-id of owner</li><li> gid - A number containing the group-id of owner</li><li> rdev - A number containing the type of device, for files that are char/block devices</li><li> access - A number containing the time of last access modification (as seconds since the UNIX epoch)</li><li> change - A number containing the time of last file status change (as seconds since the UNIX epoch)</li><li> modification - A number containing the time of the last file contents change (as seconds since the UNIX epoch)</li><li> creation - A number containing the time the file was created (as seconds since the UNIX epoch)</li><li> size - A number containing the file size, in bytes</li><li> blocks - A number containing the number of blocks allocated for file</li><li> blksize - A number containing the optimal file system I/O blocksize</li></ul>          |
| **Notes**                                            | <ul><li>This function uses `stat()` internally thus if the given filepath is a symbolic link, it is followed (if it points to another link the chain is followed recursively) and the information is about the file it refers to. To obtain information about the link itself, see function `hs.fs.symlinkAttributes()`</li></ul>                |

#### [chdir](#chdir)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.fs.chdir(path) -> true or (nil,error)` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Changes the current working directory to the given path.                                                                                         |
| **Parameters**                                       | <ul><li>path - A string containing the path to change working directory to</li></ul> |
| **Returns**                                          | <ul><li>If successful, returns true, otherwise returns nil and an error string</li></ul>          |

#### [currentDir](#currentdir)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.fs.currentDir() -> string or (nil,error)` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the current working directory                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>A string containing the current working directory, or if an error occured, nil and an error string</li></ul>          |

#### [dir](#dir)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.fs.dir(path) -> iter_fn, dir_obj` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates an iterator for walking a filesystem path                                                                                         |
| **Parameters**                                       | <ul><li>path - A string containing a directory to iterate</li></ul> |
| **Returns**                                          | <ul><li>An iterator function</li><li>A data object to pass to the iterator function</li></ul>          |
| **Notes**                                            | <ul><li>The data object should be passed to the iterator function. Each call will return either a string containing the name of an entry in the directory, or nil if there are no more entries.</li><li>Iteration can also be performed by calling `:next()` on the data object. Note that if you do this, you must call `:close()` on the object when you have finished</li><li>This function will raise a Lua error if it cannot iterate the supplied path</li></ul>                |

#### [fileUTI](#fileuti)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.fs.fileUTI(path) -> string or nil` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the Uniform Type Identifier for the file location specified.                                                                                         |
| **Parameters**                                       | <ul><li>path - the path to the file to return the UTI for.</li></ul> |
| **Returns**                                          | <ul><li>a string containing the Uniform Type Identifier for the file location specified or nil if an error occured</li></ul>          |

#### [fileUTIalternate](#fileutialternate)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.fs.fileUTIalternate(fileUTI, type) -> string` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the fileUTI's equivalent form in an alternate type specification format.                                                                                         |
| **Parameters**                                       | <ul><li>a string containing a file UTI, such as one returned by `hs.fs.fileUTI`.</li><li>a string specifying the alternate format for the UTI.  This string may be one of the following:</li><li>   `extension`  - as a file extension, commonly used for platform independant file sharing when file metadata can't be guaranteed to be cross-platform compatible.  Generally considered unreliable when other file type identification methods are available.</li><li>  `mime`       - as a mime-type, commonly used by Internet applications like web browsers and email applications.</li><li>  `pasteboard` - as an NSPasteboard type (see `hs.pasteboard`).</li><li>  `ostype`     - four character file type, most common pre OS X, but still used in some legacy APIs.</li></ul> |
| **Returns**                                          | <ul><li>the file UTI in the alternate format or nil if the UTI does not have an alternate of the specified type.</li></ul>          |

#### [link](#link)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.fs.link(old, new[, symlink]) -> true or (nil,error)` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates a link                                                                                         |
| **Parameters**                                       | <ul><li>old - A string containing a path to a filesystem object to link from</li><li>new - A string containing a path to create the link at</li><li>symlink - An optional boolean, true to create a symlink, false to create a hard link. Defaults to false</li></ul> |
| **Returns**                                          | <ul><li>True if the link was created, otherwise nil and an error string</li></ul>          |

#### [lock](#lock)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.fs.lock(filehandle, mode[, start[, length]]) -> true or (nil,error)` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Locks a file, or part of it                                                                                         |
| **Parameters**                                       | <ul><li>filehandle - An open file</li><li>mode - A string containing either "r" for a shared read lock, or "w" for an exclusive write lock</li><li>start - An optional number containing an offset into the file to start the lock at. Defaults to 0</li><li>length - An optional number containing the length of the file to lock. Defaults to the full size of the file</li></ul> |
| **Returns**                                          | <ul><li>True if the lock was obtained successfully, otherwise nil and an error string</li></ul>          |

#### [lockDir](#lockdir)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.fs.lockDir(path, [seconds_stale]) -> lock or (nil,error)` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Locks a directory                                                                                         |
| **Parameters**                                       | <ul><li>path - A string containing the path to a directory</li><li>seconds_stale - An optional number containing an age (in seconds) beyond which to consider an existing lock as stale. Defaults to INT_MAX (which is, broadly speaking, equivalent to "never")</li></ul> |
| **Returns**                                          | <ul><li>If successful, a lock object, otherwise nil and an error string</li></ul>          |
| **Notes**                                            | <ul><li>This is not a low level OS feature, the lock is actually a file created in the path, called `lockfile.lfs`, so the directory must be writable for this function to succeed</li><li>The returned lock object can be freed with ```lock:free()```</li><li>If the lock already exists and is not stale, the error string returned will be "File exists"</li></ul>                |

#### [mkdir](#mkdir)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.fs.mkdir(dirname) -> true or (nil,error)` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Creates a new directory                                                                                         |
| **Parameters**                                       | <ul><li>dirname - A string containing the path of a directory to create</li></ul> |
| **Returns**                                          | <ul><li>True if the directory was created, otherwise nil and an error string</li></ul>          |

#### [pathToAbsolute](#pathtoabsolute)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.fs.pathToAbsolute(filepath) -> string` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the absolute path of a given path                                                                                         |
| **Parameters**                                       | <ul><li>filepath - Any kind of file or directory path, be it relative or not; or nil if an error occured</li></ul> |
| **Returns**                                          | <ul><li>A string containing the absolute path of `filepath` (i.e. one that doesn't intolve `.`, `..` or symlinks)</li><li>Note that symlinks will be resolved to their target file</li></ul>          |

#### [rmdir](#rmdir)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.fs.rmdir(dirname) -> true or (nil,error)` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Removes an existing directory                                                                                         |
| **Parameters**                                       | <ul><li>dirname - A string containing the path to a directory to remove</li></ul> |
| **Returns**                                          | <ul><li>True if the directory was removed, otherwise nil and an error string</li></ul>          |

#### [symlinkAttributes](#symlinkattributes)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.fs.symlinkAttributes (filepath [, aname]) -> table or string or nil,error` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the attributes of a symbolic link                                                                                         |
| **Parameters**                                       | <ul><li>filepath - A string containing the path of a link to inspect</li><li>aName - An optional attribute name. If this value is specified, only the attribute requested, is returned</li></ul> |
| **Returns**                                          | <ul><li>A table or string if the values could be found, otherwise nil and an error string.</li></ul>          |
| **Notes**                                            | <ul><li>The return values for this function are identical to those provided by `hs.fs.attributes()`</li></ul>                |

#### [tagsAdd](#tagsadd)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.fs.tagsAdd(filepath, tags)` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Adds one or more tags to the Finder tags of a file                                                                                         |
| **Parameters**                                       | <ul><li>filepath - A string containing the path of a file</li><li>tags - A table containing one or more strings, each containing a tag name</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [tagsGet](#tagsget)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.fs.tagsGet(filepath) -> table or nil` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Gets the Finder tags of a file                                                                                         |
| **Parameters**                                       | <ul><li>filepath - A string containing the path of a file</li></ul> |
| **Returns**                                          | <ul><li>A table containing the list of the file's tags, or nil if an error occurred</li></ul>          |

#### [tagsRemove](#tagsremove)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.fs.tagsRemove(filepath, tags)` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Removes Finder tags from a file                                                                                         |
| **Parameters**                                       | <ul><li>filepath - A string containing the path of a file</li><li>tags - A table containing one or more strings, each containing a tag name</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [tagsSet](#tagsset)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.fs.tagsSet(filepath, tags)` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Sets the Finder tags of a file, removing any that are already set                                                                                         |
| **Parameters**                                       | <ul><li>filepath - A string containing the path of a file</li><li>tags - A table containing zero or more strings, each containing a tag name</li></ul> |
| **Returns**                                          | <ul><li>None</li></ul>          |

#### [temporaryDirectory](#temporarydirectory)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.fs.temporaryDirectory() -> string` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Returns the path of the temporary directory for the current user.                                                                                         |
| **Parameters**                                       | <ul><li>None</li></ul> |
| **Returns**                                          | <ul><li>The path to the system designated temporary directory for the current user.</li></ul>          |

#### [touch](#touch)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.fs.touch(filepath [, atime [, mtime]]) -> true or (nil,error)` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Updates the access and modification times of a file                                                                                         |
| **Parameters**                                       | <ul><li>filepath - A string containing the path of a file to touch</li><li>atime - An optional number containing the new access time of the file to set (as seconds since the Epoch). Defaults to now</li><li>mtime - An optional number containing the new modification time of the file to set (as seconds since the Epoch). Defaults to the value of atime</li></ul> |
| **Returns**                                          | <ul><li>True if the operation was successful, otherwise nil and an error string</li></ul>          |

#### [unlock](#unlock)
| <span style="font-align: left;">**Signature**</span> | <span style="font-align: left;">`hs.fs.unlock(filehandle[, start[, length]]) -> true or (nil,error)` </span>                                                |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Unlocks a file or a part of it.                                                                                         |
| **Parameters**                                       | <ul><li>filehandle - An open file</li><li>start - An optional number containing an offset from the start of the file, to unlock. Defaults to 0</li><li>length - An optional number containing the length of file to unlock. Defaults to the full size of the file</li></ul> |
| **Returns**                                          | <ul><li>True if the unlock succeeded, otherwise nil and an error string</li></ul>          |

