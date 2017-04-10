# Hammerspoon docs: hs.mjomatic

tmuxomatic-like window management

## API Overview
* Functions - API calls offered directly by the extension</li>
  * go

## API Documentation

### Functions

#### go
  * Signature: hs.mjomatic.go(cfg)
  * Type: Function
  * Description: Applies a configuration to the currently open windows
  ~~~lua
    mjomatic.go({
    "CCCCCCCCCCCCCiiiiiiiiiii      # <-- The windowgram, it defines the shapes and positions of windows",
    "CCCCCCCCCCCCCiiiiiiiiiii",
    "SSSSSSSSSSSSSiiiiiiiiiii",
    "SSSSSSSSSSSSSYYYYYYYYYYY",
    "SSSSSSSSSSSSSYYYYYYYYYYY",
    "",
    "C Google Chrome            # <-- window C has application():title() 'Google Chrome'",
    "i iTerm",
    "Y YoruFukurou",
    "S Sublime Text 2"})
    ~~~
  * Parameters:
     * cfg - A table containing a series of strings, representing the desired window layout
  * Returns:
     * None
  * Notes:
     * An example use:
