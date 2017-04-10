# Hammerspoon docs: hs.image

A module for capturing and manipulating image objects from other modules for use with hs.drawing.


## API Overview
* Constants - Useful values which cannot be changed</li>
  * additionalImageNames[]
  * systemImageNames[]
* Constructors - API calls which return an object, typically one that offers API methods</li>
  * iconForFile
  * iconForFileType
  * imageFromASCII
  * imageFromAppBundle
  * imageFromMediaFile
  * imageFromName
  * imageFromPath
  * imageFromURL
* Methods - API calls which can only be made on an object returned by a constructor</li>
  * copy
  * croppedImage
  * name
  * saveToFile
  * setName
  * setSize
  * size
  * template

## API Documentation

### Constants

#### additionalImageNames[]
  * Signature: hs.image.additionalImageNames[]
  * Type: Constant
  * Description: Table of arrays containing the names of additional internal system images which may also be available for use with `hs.drawing.image` and [hs.image.imageFromName](#imageFromName).
  * Notes:
     * The list of these images was pulled from a collection located in the repositories at https://github.com/hetima?tab=repositories.  As these image names are (for the most part) not formally listed in Apple's documentation or published APIs, their use cannot be guaranteed across all OS X versions.  If you identify any images which may be missing or could be added, please file an issue at https://github.com/Hammerspoon/hammerspoon.

#### systemImageNames[]
  * Signature: hs.image.systemImageNames[]
  * Type: Constant
  * Description: Table containing the names of internal system images for use with hs.drawing.image
  * Notes:
     * Image names pulled from NSImage.h
     * This table has a __tostring() metamethod which allows listing it's contents in the Hammerspoon console by typing `hs.image.systemImageNames`.

### Constructors

#### iconForFile
  * Signature: hs.image.iconForFile(file) -> object
  * Type: Constructor
  * Description: Creates an `hs.image` object for the file or files specified
  * Parameters:
     * file - the path to a file or an array of files to generate an icon for.
  * Returns:
     * An `hs.image` object or nil, if there was an error.  The image will be the icon for the specified file or an icon representing multiple files if an array of multiple files is specified.

#### iconForFileType
  * Signature: hs.image.iconForFileType(fileType) -> object
  * Type: Constructor
  * Description: Creates an `hs.image` object of the icon for the specified file type.
  * Parameters:
     * fileType - the file type, specified as a filename extension or a universal type identifier (UTI).
  * Returns:
     * An `hs.image` object or nil, if there was an error

#### imageFromASCII
  * Signature: hs.image.imageFromASCII(ascii[, context]) -> object
  * Type: Constructor
  * Description: Creates an image from an ASCII representation with the specified context.
  * Parameters:
     * ascii - A string containing a representation of an image
     * context - An optional table containing the context for each shape in the image.  A shape is considered a single drawing element (point, ellipse, line, or polygon) as defined at https://github.com/cparnot/ASCIImage and http://cocoamine.net/blog/2015/03/20/replacing-photoshop-with-nsstring/.
       * The context table is an optional (possibly sparse) array in which the index represents the order in which the shapes are defined.  The last (highest) numbered index in the sparse array specifies the default settings for any unspecified index and any settings which are not explicitly set in any other given index.
       * Each index consists of a table which can contain one or more of the following keys:
         * fillColor - the color with which the shape will be filled (defaults to black)  Color is defined in a table containing color component values between 0.0 and 1.0 for each of the keys:
           * red (default 0.0)
           * green (default 0.0)
           * blue (default 0.0)
           * alpha (default 1.0)
         * strokeColor - the color with which the shape will be stroked (defaults to black)
         * lineWidth - the line width (number) for the stroke of the shape (defaults to 1 if anti-aliasing is on or (√2)/2 if it is off -- approximately 0.7)
         * shouldClose - a boolean indicating whether or not the shape should be closed (defaults to true)
         * antialias - a boolean indicating whether or not the shape should be antialiased (defaults to true)
  * Returns:
     * An `hs.image` object, or nil if an error occured
  * Notes:
     * To use the ASCII diagram image support, see https://github.com/cparnot/ASCIImage and http://cocoamine.net/blog/2015/03/20/replacing-photoshop-with-nsstring
     * The default for lineWidth, when antialiasing is off, is defined within the ASCIImage library. Geometrically it represents one half of the hypotenuse of the unit right-triangle and is a more accurate representation of a "real" point size when dealing with arbitrary angles and lines than 1.0 would be.

#### imageFromAppBundle
  * Signature: hs.image.imageFromAppBundle(bundleID) -> object
  * Type: Constructor
  * Description: Creates an `hs.image` object using the icon from an App
  * Parameters:
     * bundleID - A string containing the bundle identifier of an application
  * Returns:
     * An `hs.image` object or nil, if no app icon was found

#### imageFromMediaFile
  * Signature: hs.image.imageFromMediaFile(file) -> object
  * Type: Constructor
  * Description: Creates an `hs.image` object from a video file or the album artwork of an audio file or directory
  * Parameters:
     * file - A string containing the path to an audio or video file or an album directory
  * Returns:
     * An `hs.image` object
  * Notes:
     * If a thumbnail can be generated for a video file, it is returned as an `hs.image` object, otherwise the filetype icon
     * For audio files, this function first determines the containing directory (if not already a directory)
     * It checks if any of the following common filenames for album art are present:
      * cover.jpg
      * front.jpg
      * art.jpg
      * album.jpg
      * folder.jpg
     * If one of the common album art filenames is found, it is returned as an `hs.image` object
     * This is faster than extracting image metadata and allows for obtaining artwork associated with file formats such as .flac/.ogg
     * If no common album art filenames are found, it attempts to extract image metadata from the file. This works for .mp3/.m4a files
     * If embedded image metadata is found, it is returned as an `hs.image` object, otherwise the filetype icon

#### imageFromName
  * Signature: hs.image.imageFromName(string) -> object
  * Type: Constructor
  * Description: Returns the hs.image object for the specified name, if it exists.
  * Parameters:
     * Name - the name of the image to return.
  * Returns:
     * An hs.image object or nil, if no image was found with the specified name.
  * Notes:
     * Some predefined labels corresponding to OS X System default images can be found in `hs.image.systemImageNames`.
     * Names are not required to be unique: The search order is as follows, and the first match found is returned:
        * an image whose name was explicitly set with the `setName` method since the last full restart of Hammerspoon
        * Hammerspoon's main application bundle
        * the Application Kit framework (this is where most of the images listed in `hs.image.systemImageNames` are located)
     * Image names can be assigned by the image creator or by calling the `hs.image:setName` method on an hs.image object.

#### imageFromPath
  * Signature: hs.image.imageFromPath(path) -> object
  * Type: Constructor
  * Description: Loads an image file
  * Parameters:
     * path - A string containing the path to an image file on disk
  * Returns:
     * An `hs.image` object, or nil if an error occured

#### imageFromURL
  * Signature: hs.image.imageFromURL(url) -> object
  * Type: Constructor
  * Description: Creates an `hs.image` object from the contents of the specified URL.
  * Parameters:
     * url - a web url specifying the location of the image to retrieve
  * Returns:
     * An `hs.image` object or nil, if the url does not specify image contents or is unreachable

### Methods

#### copy
  * Signature: hs.image:copy() -> imageObject
  * Type: Method
  * Description: Returns a copy of the image
  * Parameters:
     * None
  * Returns:
     * a new hs.image object

#### croppedImage
  * Signature: hs.image:croppedImage(rectangle) -> object
  * Type: Method
  * Description: Returns a copy of the portion of the image specified by the rectangle specified.
  * Parameters:
     * rectangle - a table with 'x', 'y', 'h', and 'w' keys specifying the portion of the image to return in the new image.
  * Returns:
     * a copy of the portion of the image specified

#### name
  * Signature: hs.image:name([name]) -> imageObject | string
  * Type: Method
  * Description: Get or set the name of the image represented by the hs.image object.
  * Parameters:
     * `name` - an optional string specifying the new name for the hs.image object.
  * Returns:
     * if no argument is provided, returns the current name.  If a new name is specified, returns the hs.image object or nil if the name cannot be changed.
  * Notes:
     * see also [hs.image:setName](#setName) for a variant that returns a boolean instead.

#### saveToFile
  * Signature: hs.image:saveToFile(filename[, filetype]) -> boolean
  * Type: Method
  * Description: Save the hs.image object as an image of type `filetype` to the specified filename.
  * Parameters:
     * filename - the path and name of the file to save.
     * filetype - optional case-insensitive string paramater specifying the file type to save (default PNG)
       * PNG  - save in Portable Network Graphics (PNG) format
       * TIFF - save in Tagged Image File Format (TIFF) format
       * BMP  - save in Windows bitmap image (BMP) format
       * GIF  - save in Graphics Image Format (GIF) format
       * JPEG - save in Joint Photographic Experts Group (JPEG) format
  * Returns:
     * Status - a boolean value indicating success (true) or failure (false)
  * Notes:
     * Saves image at its original size.

#### setName
  * Signature: hs.image:setName(Name) -> boolean
  * Type: Method
  * Description: Assigns the name assigned to the hs.image object.
  * Parameters:
     * Name - the name to assign to the hs.image object.
  * Returns:
     * Status - a boolean value indicating success (true) or failure (false) when assigning the specified name.
  * Notes:
     * This method is included for backwards compatibility and is considered deprecated.  It is equivalent to `hs.image:name(name) and true or false`.

#### setSize
  * Signature: hs.image:setSize(size [, absolute]) -> object
  * Type: Method
  * Description: Returns a copy of the image resized to the height and width specified in the size table.
  * Parameters:
     * size     - a table with 'h' and 'w' keys specifying the size for the new image.
     * absolute - an optional boolean specifying whether or not the copied image should be resized to the height and width specified (true), or whether the copied image should be scaled proportionally to fit within the height and width specified (false).  Defaults to false.
  * Returns:
     * a copy of the image object at the new size
  * Notes:
     * This method is included for backwards compatibility and is considered deprecated.  It is equivalent to `hs.image:copy():size(size, [absolute])`.

#### size
  * Signature: hs.image:size([size, [absolute]] ) -> imageObject | size
  * Type: Method
  * Description: Get or set the size of the image represented byt he hs.image object.
  * Parameters:
     * `size`     - an optional table with 'h' and 'w' keys specifying the size for the image.
     * `absolute` - when specifying a new size, an optional boolean, default false, specifying whether or not the image should be resized to the height and width specified (true), or whether the copied image should be scaled proportionally to fit within the height and width specified (false).
  * Returns:
     * If arguments are provided, return the hs.image object; otherwise returns the current size
  * Notes:
     * See also [hs.image:setSize](#setSize) for creating a copy of the image at a new size.

#### template
  * Signature: hs.image:template([state]) -> imageObject | boolean
  * Type: Method
  * Description: Get or set whether the image is considered a template image.
  * Parameters:
     * `state` - an optional boolean specifying whether or not the image should be a template.
  * Returns:
     * if a parameter is provided, returns the hs.image object; otherwise returns the current value
  * Notes:
     * Template images consist of black and clear colors (and an alpha channel). Template images are not intended to be used as standalone images and are usually mixed with other content to create the desired final appearance.
     * Images with this flag set to true usually appear lighter than they would with this flag set to false.
