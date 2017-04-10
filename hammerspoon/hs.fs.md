# [docs](index.md) » hs.fs
---

Access/inspect the filesystem

Home: http://keplerproject.github.io/luafilesystem

This module is produced by the Kepler Project under the name "Lua File System"

## Submodules
 * [hs.fs.volume](hs.fs.volume.md)

## API Overview
* Functions - API calls offered directly by the extension
** [attributes](#attributes)
** [chdir](#chdir)
** [currentDir](#currentDir)
** [dir](#dir)
** [fileUTI](#fileUTI)
** [fileUTIalternate](#fileUTIalternate)
** [link](#link)
** [lock](#lock)
** [lockDir](#lockDir)
** [mkdir](#mkdir)
** [pathToAbsolute](#pathToAbsolute)
** [rmdir](#rmdir)
** [symlinkAttributes](#symlinkAttributes)
** [tagsAdd](#tagsAdd)
** [tagsGet](#tagsGet)
** [tagsRemove](#tagsRemove)
** [tagsSet](#tagsSet)
** [temporaryDirectory](#temporaryDirectory)
** [touch](#touch)
** [unlock](#unlock)

## API Documentation

### Functions

#### [attributes](#attributes)
| | |
|-|-|
| Signature   | hs.fs.attributes(filepath [, aName]) -> table or string or nil,error  |
| Type        | Function |
| Description | Gets the attributes of a file |
| Parameters |  * filepath - A string containing the path of a file to inspect * aName - An optional attribute name. If this value is specified, only the attribute requested, is returned | | Returns |  * A table with the file attributes corresponding to filepath (or nil followed by an error message in case of error). If the second optional argument is given, then a string is returned with the value of the named attribute. attribute mode is a string, all the others are numbers, and the time related attributes use the same time reference of os.time:  * dev - A number containing the device the file resides on  * ino - A number containing the inode of the file  * mode - A string containing the type of the file (possible values are: file, directory, link, socket, named pipe, char device, block device or other)  * nlink - A number containing a count of hard links to the file  * uid - A number containing the user-id of owner  * gid - A number containing the group-id of owner  * rdev - A number containing the type of device, for files that are char/block devices  * access - A number containing the time of last access modification (as seconds since the UNIX epoch)  * change - A number containing the time of last file status change (as seconds since the UNIX epoch)  * modification - A number containing the time of the last file contents change (as seconds since the UNIX epoch)  * creation - A number containing the time the file was created (as seconds since the UNIX epoch)  * size - A number containing the file size, in bytes  * blocks - A number containing the number of blocks allocated for file  * blksize - A number containing the optimal file system I/O blocksize | | Notes |  * This function uses `stat()` internally thus if the given filepath is a symbolic link, it is followed (if it points to another link the chain is followed recursively) and the information is about the file it refers to. To obtain information about the link itself, see function `hs.fs.symlinkAttributes()` | 
#### [chdir](#chdir)
| | |
|-|-|
| Signature   | hs.fs.chdir(path) -> true or (nil,error)  |
| Type        | Function |
| Description | Changes the current working directory to the given path. |
| Parameters |  * path - A string containing the path to change working directory to | | Returns |  * If successful, returns true, otherwise returns nil and an error string | 
#### [currentDir](#currentDir)
| | |
|-|-|
| Signature   | hs.fs.currentDir() -> string or (nil,error)  |
| Type        | Function |
| Description | Gets the current working directory |
| Parameters |  * None | | Returns |  * A string containing the current working directory, or if an error occured, nil and an error string | 
#### [dir](#dir)
| | |
|-|-|
| Signature   | hs.fs.dir(path) -> iter_fn, dir_obj  |
| Type        | Function |
| Description | Creates an iterator for walking a filesystem path |
| Parameters |  * path - A string containing a directory to iterate | | Returns |  * An iterator function * A data object to pass to the iterator function | | Notes |  * The data object should be passed to the iterator function. Each call will return either a string containing the name of an entry in the directory, or nil if there are no more entries. * Iteration can also be performed by calling `:next()` on the data object. Note that if you do this, you must call `:close()` on the object when you have finished * This function will raise a Lua error if it cannot iterate the supplied path | 
#### [fileUTI](#fileUTI)
| | |
|-|-|
| Signature   | hs.fs.fileUTI(path) -> string or nil  |
| Type        | Function |
| Description | Returns the Uniform Type Identifier for the file location specified. |
| Parameters |  * path - the path to the file to return the UTI for. | | Returns |  * a string containing the Uniform Type Identifier for the file location specified or nil if an error occured | 
#### [fileUTIalternate](#fileUTIalternate)
| | |
|-|-|
| Signature   | hs.fs.fileUTIalternate(fileUTI, type) -> string  |
| Type        | Function |
| Description | Returns the fileUTI's equivalent form in an alternate type specification format. |
| Parameters |  * a string containing a file UTI, such as one returned by `hs.fs.fileUTI`. * a string specifying the alternate format for the UTI.  This string may be one of the following:    * `extension`  - as a file extension, commonly used for platform independant file sharing when file metadata can't be guaranteed to be cross-platform compatible.  Generally considered unreliable when other file type identification methods are available.   * `mime`       - as a mime-type, commonly used by Internet applications like web browsers and email applications.   * `pasteboard` - as an NSPasteboard type (see `hs.pasteboard`).   * `ostype`     - four character file type, most common pre OS X, but still used in some legacy APIs. | | Returns |  * the file UTI in the alternate format or nil if the UTI does not have an alternate of the specified type. | 
#### [link](#link)
| | |
|-|-|
| Signature   | hs.fs.link(old, new[, symlink]) -> true or (nil,error)  |
| Type        | Function |
| Description | Creates a link |
| Parameters |  * old - A string containing a path to a filesystem object to link from * new - A string containing a path to create the link at * symlink - An optional boolean, true to create a symlink, false to create a hard link. Defaults to false | | Returns |  * True if the link was created, otherwise nil and an error string | 
#### [lock](#lock)
| | |
|-|-|
| Signature   | hs.fs.lock(filehandle, mode[, start[, length]]) -> true or (nil,error)  |
| Type        | Function |
| Description | Locks a file, or part of it |
| Parameters |  * filehandle - An open file * mode - A string containing either "r" for a shared read lock, or "w" for an exclusive write lock * start - An optional number containing an offset into the file to start the lock at. Defaults to 0 * length - An optional number containing the length of the file to lock. Defaults to the full size of the file | | Returns |  * True if the lock was obtained successfully, otherwise nil and an error string | 
#### [lockDir](#lockDir)
| | |
|-|-|
| Signature   | hs.fs.lockDir(path, [seconds_stale]) -> lock or (nil,error)  |
| Type        | Function |
| Description | Locks a directory |
| Parameters |  * path - A string containing the path to a directory * seconds_stale - An optional number containing an age (in seconds) beyond which to consider an existing lock as stale. Defaults to INT_MAX (which is, broadly speaking, equivalent to "never") | | Returns |  * If successful, a lock object, otherwise nil and an error string | | Notes |  * This is not a low level OS feature, the lock is actually a file created in the path, called `lockfile.lfs`, so the directory must be writable for this function to succeed * The returned lock object can be freed with ```lock:free()``` * If the lock already exists and is not stale, the error string returned will be "File exists" | 
#### [mkdir](#mkdir)
| | |
|-|-|
| Signature   | hs.fs.mkdir(dirname) -> true or (nil,error)  |
| Type        | Function |
| Description | Creates a new directory |
| Parameters |  * dirname - A string containing the path of a directory to create | | Returns |  * True if the directory was created, otherwise nil and an error string | 
#### [pathToAbsolute](#pathToAbsolute)
| | |
|-|-|
| Signature   | hs.fs.pathToAbsolute(filepath) -> string  |
| Type        | Function |
| Description | Gets the absolute path of a given path |
| Parameters |  * filepath - Any kind of file or directory path, be it relative or not; or nil if an error occured | | Returns |  * A string containing the absolute path of `filepath` (i.e. one that doesn't intolve `.`, `..` or symlinks) * Note that symlinks will be resolved to their target file | 
#### [rmdir](#rmdir)
| | |
|-|-|
| Signature   | hs.fs.rmdir(dirname) -> true or (nil,error)  |
| Type        | Function |
| Description | Removes an existing directory |
| Parameters |  * dirname - A string containing the path to a directory to remove | | Returns |  * True if the directory was removed, otherwise nil and an error string | 
#### [symlinkAttributes](#symlinkAttributes)
| | |
|-|-|
| Signature   | hs.fs.symlinkAttributes (filepath [, aname]) -> table or string or nil,error  |
| Type        | Function |
| Description | Gets the attributes of a symbolic link |
| Parameters |  * filepath - A string containing the path of a link to inspect * aName - An optional attribute name. If this value is specified, only the attribute requested, is returned | | Returns |  * A table or string if the values could be found, otherwise nil and an error string. | | Notes |  * The return values for this function are identical to those provided by `hs.fs.attributes()` | 
#### [tagsAdd](#tagsAdd)
| | |
|-|-|
| Signature   | hs.fs.tagsAdd(filepath, tags)  |
| Type        | Function |
| Description | Adds one or more tags to the Finder tags of a file |
| Parameters |  * filepath - A string containing the path of a file * tags - A table containing one or more strings, each containing a tag name | | Returns |  * None | 
#### [tagsGet](#tagsGet)
| | |
|-|-|
| Signature   | hs.fs.tagsGet(filepath) -> table or nil  |
| Type        | Function |
| Description | Gets the Finder tags of a file |
| Parameters |  * filepath - A string containing the path of a file | | Returns |  * A table containing the list of the file's tags, or nil if an error occurred | 
#### [tagsRemove](#tagsRemove)
| | |
|-|-|
| Signature   | hs.fs.tagsRemove(filepath, tags)  |
| Type        | Function |
| Description | Removes Finder tags from a file |
| Parameters |  * filepath - A string containing the path of a file * tags - A table containing one or more strings, each containing a tag name | | Returns |  * None | 
#### [tagsSet](#tagsSet)
| | |
|-|-|
| Signature   | hs.fs.tagsSet(filepath, tags)  |
| Type        | Function |
| Description | Sets the Finder tags of a file, removing any that are already set |
| Parameters |  * filepath - A string containing the path of a file * tags - A table containing zero or more strings, each containing a tag name | | Returns |  * None | 
#### [temporaryDirectory](#temporaryDirectory)
| | |
|-|-|
| Signature   | hs.fs.temporaryDirectory() -> string  |
| Type        | Function |
| Description | Returns the path of the temporary directory for the current user. |
| Parameters |  * None | | Returns |  * The path to the system designated temporary directory for the current user. | 
#### [touch](#touch)
| | |
|-|-|
| Signature   | hs.fs.touch(filepath [, atime [, mtime]]) -> true or (nil,error)  |
| Type        | Function |
| Description | Updates the access and modification times of a file |
| Parameters |  * filepath - A string containing the path of a file to touch * atime - An optional number containing the new access time of the file to set (as seconds since the Epoch). Defaults to now * mtime - An optional number containing the new modification time of the file to set (as seconds since the Epoch). Defaults to the value of atime | | Returns |  * True if the operation was successful, otherwise nil and an error string | 
#### [unlock](#unlock)
| | |
|-|-|
| Signature   | hs.fs.unlock(filehandle[, start[, length]]) -> true or (nil,error)  |
| Type        | Function |
| Description | Unlocks a file or a part of it. |
| Parameters |  * filehandle - An open file * start - An optional number containing an offset from the start of the file, to unlock. Defaults to 0 * length - An optional number containing the length of file to unlock. Defaults to the full size of the file | | Returns |  * True if the unlock succeeded, otherwise nil and an error string | 