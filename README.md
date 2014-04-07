# Markdown Style Guide
This document contains formatting standards for creating readable, consistent files using Markdown - without wasting time changing formatting.

## Basic conventions for Markdown files
- Denote **bold** text using the asterisk format: `**bold text**`.
- Denote _italic_ text using the underscore format: `_emphasized text_`.
- Never leave trailing whitespace. Force linebreaks by using a blank line between paragraphs, not trailing spaces (it's much easier to read in an editor anyway).
- End files with a newline (see [this explanation](http://robots.thoughtbot.com/no-newline-at-end-of-file)).
- Never use consecutive blank lines outside of code samples. A single blank line is always enough in Markdown.

## Headings
- Header text must use the `atx-style` with no closing `#` character.
- Include a single space between the `#` and the text of the Header^[1](#1).

  ```
  # Header 1

  ## Header 2

  ### Header 3
  ```

- Headers spanning more than 80 characters should be re-evaluated.
- Headers must be preceded a newline except at the beginning of a file.
- Headers should not be followed by a newline unless the element following it requires a preceding newline
- The first header in a file should be an `h1`.
- Headers should never increase by more than one "level" from one header to the next. Think of higher-level headers as though they are nested within their parent, forming a hierarchy like the Table of Contents.

  ```
  This is wrong.

  # Header 1

  ### Header 3
  ```

  ```
  This is correct.

  # Header 1

  ## Header 2
  ```

## Lists
- Unordered lists are denoted with a `- ` (a hyphen and a space). Hyphens tend to be consistent across monospace fonts (being displayed at half of the line height) and seem to be the most common "list character" anyway.
- Nested list items must be indented 2 spaces further than their parent.

  ```
  This is arbitrary text, an unordered list begins on the next line.
  - list item 1
  - list item 2
    - sub-list item
  ```

- Lists should not be preceded by a newline, unless it follows an item that needs a newline after it (like code or another list).
- Lists must be followed by newlines.

  ```
  This text precedes a list of things.
  - list item 1
  - list item 2
    1. sub-list item 1
    2. sub-list item 2

  - list item 3
  - list item 4

  This is text of any kind that follows a list.
  ```

## Code
- **Inline code** must use single backticks and must not have spaces between the backtick characters and the code.

  ```
  # Bad
  ` .this-is-wrong `

  # Good
  `.this-is-good`
  ```

- **Fenced code blocks** must be preceded and followed by a newline.
- When used inside _list items_, **fenced code blocks** must be indented as if they were one level deeper that the list item that contains them.

  ```
  - This list item contains a fenced code block.
  - Let's show how it might interact with a list.

    ```
    .code-example {
      property: value;
    }
    ```

  There is a newline above this paragraph because it is both the end of a list and because it follows a fenced code block.
  ```

- As long as the parser supports it; code blocks should not be denoted with indentation. Using back-ticks is much more explicit than 4 spaces or 1 tab.

## Tables
Like fenced code blocks, tables in Markdown are provided by Markdown Extra which seems to be pretty widely implemented.

- Pipe characters must be preceded and followed by spaces for readability.
- Table column width should be determined by the longest cell in the column.
- Always format tables so they are readable in pre-processing.

  ```
  # This is completely unreadable, although it is technically valid.
  table header | other table header
  --- | ---
  table data | other table data
  ```

- Never use preceding or trailing pipes when writing tables.

  ```
  | table header | other table header |
  | ------------ | ------------------ |
  | table data   | table data         |
  ```

- Tables must always be preceded and followed by newlines.

### Table example:
_This table meets all the criteria:_

```
Group                     | Domain          | First Appearance
------------------------- | --------------- | ----------------
ShinRa                    | Mako Reactors   | FFVII
Moogles                   | MogNet          | FFIII
Vana'diel Chocobo Society | Chocobo Raising | FFXI:TOAU
```

_A handsome table in pre-processed Markdown is also handsome when rendered:_

Group                     | Domain          | First Appearance
------------------------- | --------------- | ----------------
ShinRa                    | Mako Reactors   | FFVII
Moogles                   | MogNet          | FFIII
Vana'diel Chocobo Society | Chocobo Raising | FFXI:TOAU

## Footnotes
  <a name="1"><a>
  1. This is enforced locally through redcarpet2's configuration: `:space_after_headers`.

