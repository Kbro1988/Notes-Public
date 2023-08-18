<!-- omit from toc -->
# Page Title

This will serve as our basic guideline for documentation layout as well as guide to some basic markdown syntax.

<!-- omit from toc -->
## Content

(Table of contents.)

If you have the extension '**Markdown All in One**,' run the command command "Create Table of Contents" (in the VS Code Command Palette) to insert a new table of contents.

- [Topic Header 1](#topic-header-1)
  - [Topic Subheader A](#topic-subheader-a)
  - [Topic Subheader B](#topic-subheader-b)
  - [Topic Subheader C](#topic-subheader-c)
  - [Topic Subheader D](#topic-subheader-d)
- [Topic Header 2](#topic-header-2)
  - [Links](#links)
  - [Images](#images)
- [Topic Header 3](#topic-header-3)
- [Topic Header 4](#topic-header-4)
- [Topic Header 5](#topic-header-5)

## Topic Header 1

(Please notes about Topic Header 1 here.) This example will be followed by some subheaders with markdown syntax notes:

### Topic Subheader A

This text is **bold**.

This text is *italic*.

This text is both ***bold and italic***.

This text is ~~strikethrough~~.

This text is `code`.

To ignore Markdown formatting characters, use \ before the character. Ex: `\*`

### Topic Subheader B

Table:
| Header 1 | Header 2 | Header 3 |
|--- |--- |--- |
| row 1 | column 2 | column 3 |
| row 2 | row 2 column 2 | row 2 column 3 |

### Topic Subheader C

You can also do `code` snippets:

```text
code snippet
```

You can define the language of the snippet:

```py
import math

x = 1
if x == 1:
    # indented four spaces
    print("x is 1.")
```

### Topic Subheader D

Numbered List:

1. This is step 1.
2. This is the next step.
3. This is yet another step, the third.

Bulleted List:

- Item A
- Item B
  - Item BA
  - Item BB
    - Item BBA
  - Item BC
- Item C

Task List:

- [ ] Task 1
- [ ] Task 2
- [ ] Task 3

Hybrid List:

1. One
   - Item A
   - Item B
2. Two

   Subtext with some `code`.
3. Three

   ```javascript
   function test() {
   console.log("notice the blank line before this function?");
   ```

4. Four

   | Hello | World |
   |---|---|
   | How | are you? |

At the end of a major section, it may be a nice idea to allow the user to jump back to the top of page via the main header:

**[- Back to Top -](#content)**

## Topic Header 2

### Links

The Markdown syntax for an inline link consists of the [link text] portion, which is the text that will be hyperlinked, followed by the (file-name.md) portion, which is the URL or file name that’s being linked to:

[link text](file-name.md)

[UCF IT](https://it.ucf.edu/)

For links to articles (cross-references) within the repository, use relative links. You can use all relative link operands, such as ./ (current directory), …/ (back one directory), and …/…/ (back two directories).

### Images

![UCF Icon](../assets/ucf-icon-01.png)

**[- Back to Top -](#content)**

## Topic Header 3

You can choose from these types of note blocks to draw attention to specific content:

- [!NOTE]
- [!TIP]
- [!IMPORTANT]
- [!CAUTION]
- [!WARNING]
- [!ADMINISTRATION]
- [!AVAILABILITY]
- [!PREREQUISITES]

In general, note blocks should be used sparingly because they can be disruptive. Although they also support code blocks, images, lists, and links, try to keep your note blocks simple and straightforward.

>[!NOTE]
>
>This is a standard NOTE block.

.

>[!TIP]
>
>This is a standard tip.

.

**[- Back to Top -](#content)**

## Topic Header 4

<details><summary>Click to expand</summary>

Many Markdown applications allow you to use HTML tags in Markdown-formatted text. This is helpful if you prefer certain HTML tags to Markdown syntax. For example, some people find it easier to use HTML tags for images. Using HTML is also helpful when you need to change the attributes of an element, like specifying the color of text or changing the width of an image.

To use HTML, place the tags in the text of your Markdown-formatted file.

> `This **word** is bold. This <em>word</em> is italic.`

The rendered output looks like this:

> This **word** is bold. This <em>word</em> is italic.

For security reasons, not all Markdown applications support HTML in Markdown documents. When in doubt, check your Markdown application’s documentation. Some applications support only a subset of HTML tags.

Use blank lines to separate block-level HTML elements like `<div>`, `<table>`, `<pre>`, and `<p>` from the surrounding content. Try not to indent the tags with tabs or spaces — that can interfere with the formatting.

You can’t use Markdown syntax inside block-level HTML tags. For example, `<p>italic and **bold**</p>` won’t work.

</details>

.

Another thing which can help with pacing and organizing content is a line break:

---

## Topic Header 5

>[!Related Articles]
>
>- [Project Markdown](https://daringfireball.net/projects/markdown/)
>- [Markdown Guide - Basic Syntax](https://www.markdownguide.org/basic-syntax/)
>- [Adobe Markdown Guide](https://experienceleague.adobe.com/docs/contributor/contributor-guide/writing-essentials/markdown.html?lang=en)
>- VSCode Extensions:
>   - [Markdown All-in-one](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one)
>   - [Markdown lint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)
>   - [Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker)

**[- Back to Top -](#content)**

---

At the end of the document we can provide a quick way to get back to the 'Documentation' repository's main page / sitemap:

**[- Documentation / Home -](../main/)**
