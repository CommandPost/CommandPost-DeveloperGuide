# [docs](index.md) » hs.doc.markdown
---

Markdown to HTML and plaintext conversion support used by hs.doc

This module provides Github-Flavored-Markdown conversion support used by hs.doc.  This module is a Lua wrapper to the C code portion of the Ruby gem `github-markdown`, available at https://rubygems.org/gems/github-markdown/versions/0.6.9.

The Ruby gem `github-markdown` was chosen as the code base for this module because it is the tool used to generate the official Hammerspoon Dash docset.

The Lua wrapper portion is licensed under the MIT license by the Hammerspoon development team.  The C code portion of the Ruby gem is licensed under the MIT license by GitHub, Inc.

## API Overview
* Functions - API calls offered directly by the extension
 * [convert](#convert)

## API Documentation

### Functions

#### [convert](#convert)
| <span style="float: left;">**Signature**</span> | <span style="float: left;">`hs.doc.markdown.convert(markdown, [type]) -> output` </span>                                                          |
| -----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Type**                                             | Function                                                                                         |
| **Description**                                      | Converts markdown encoded text to html or plaintext.                                                                                         |
| **Parameters**                                       | <ul><br /><li>markdown - a string containing the input text encoded using markdown tags * type     - an optional string specifying the conversion options and output type.  Defaults to "gfm".  The currently recognized types are:   * "markdown"  - specfies that the output should be HTML with the standard GitHub/Markdown extensions enabled.   * "gfm"       - specifies that the output should be HTML with additional GitHub extensions enabled.   * "plaintext" - specifies that the output should plain text with the standard GitHub/Markdown extensions enabled.</li><br /></ul>                                        |
| **Returns**                                          | <ul><br /><li>an HTML or plaintext representation of the markdown encoded text provided.</li><br /></ul>                                           |
| **Notes**                                            | <ul><br /><li>The standard GitHub/Markdown extensions enabled for all conversions are:   * NO_INTRA_EMPHASIS -  disallow emphasis inside of words   * LAX_SPACING       - supports spacing like in Markdown 1.0.0 (i.e. do not require an empty line between two different blocks in a paragraph)   * STRIKETHROUGH     - support strikethrough with double tildes (~)   * TABLES            - support Markdown tables   * FENCED_CODE       - supports fenced code blocks surround by three back-ticks (`) or three tildes (~)   * AUTOLINK          - HTTP URL's are treated as links, even if they aren't marked as such with Markdown tags</li><br /></ul>                                             |

