# Installing CommandPost

CommandPost is made up of two seperate components:

* [CommandPost-App](https://github.com/CommandPost/CommandPost-App) contains the [Hammerspoon](http://www.hammerspoon.org) fork which makes up the main application.
* [CommandPost](https://github.com/CommandPost/CommandPost) contains all the [Lua](https://www.lua.org/about.html) scripts that drive the interface and feature set.

To build your own version of CommandPost, first download or clone this repository. You can then either link the `~/CommandPost` directory to the GitHub `src` directory, or copy the contents of GitHub `src` into said directory.

### Option 1: Link

1. Open a Terminal window.
2. Navigate to the CommandPost project root directory.
3. Execute `./scripts/link-cp`

### Option 2: Copy

1. Open a Terminal window.
2. Navigate to the CommandPost project root directory.
2. Execute `./scripts/install-cp`

Next download or clone, then build the [standalone app](https://github.com/CommandPost/CommandPost-App):

1. Create a self-signed Code Signing certificate named **Internal Code Signing** as explained [here](http://bd808.com/blog/2013/10/21/creating-a-self-signed-code-certificate-for-xcode/) - however, please make sure you label the certificate "Internal Code Signing" and not "Self-signed Applications".
2. Open a Terminal window.
3. Navigate to the CommandPost-App project root directory.
4. Install `pip` by following [these instructions](https://packaging.python.org/installing/#install-pip-setuptools-and-wheel).
5. Execute `pip install -r requirements.txt`
4. Execute `./scripts/build_commandpost.sh`

On load, the standalone app will try to load `~/CommandPost/init.lua` first, and if that fails, it will then load the Lua scripts within the Application Bundle. This means you can keep developing by modifying the files within `~/CommandPost`, and then when you're done, simply execute `./scripts/build_commandpost.sh` again for distribution.