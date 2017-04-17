# Translating CommandPost
---

CommandPost has been designed with internationalisation in mind.

We use [i18n.lua](https://github.com/kikito/i18n.lua) to handle translations.

We currently have a single translation file for each language, which covers both the Extensions & Plugins within CommandPost-App.

If you're developing a plugin, we recommend still using i18n, and doing your own translations within the plugin.

To translate CommandPost to another language, simply download [en.lua](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/resources/languages/en.lua), rename the file (using [these naming conventions](http://www.unicode.org/cldr/charts/latest/supplemental/territory_language_information.html)), then translate!

The first line of the document is the Language name that's used in CommandPost Preferences dropdown. For example:

```lua
-- LANGUAGE: English
```

Once you've finished translating, you can either fork the CommandPost repository and submit a pull request with your translated file, or simply attach the translated file to a new [issue](https://github.com/CommandPost/CommandPost/issues).