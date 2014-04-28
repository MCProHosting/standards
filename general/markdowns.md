# Markdowns

Readmes and markdown files are an integral part of any development project.

### General

 * MCPH development revolves around Github and, therefore, when working on Git-based projects, you must write in Github-flavored markdown.
 * You must insert one line break after each block-level element, including the last element of the page.
 * You should not use HTML within markdown files.

### Titles

 * You must use atx-styling headings. That is, the title preceded on the same line by a space and one or more pound symbols.
 * You must not use atx-styled closings on your titles. That is, inserting one or more pound symbols on the same line after the title.

```
## This is a title!
```

### Lists

 * Unordered lists should be denoted by using an asterisk `*` for each list item.
 * Ordered lists, denoted by numbers followed by a period rather than asterisks, must be written in order, so that the number of the list item within the markdown is the same as the number beside the list item when the markdown is rendered.
 * Lists must either use a single space after their denotation, or a hanging indentation to maintain text alignment. Examples:

```
* Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
Aliquam hendrerit mi posuere lectus. Vestibulum enim wisi,
viverra nec, fringilla in, laoreet vitae, risus.
* Donec sit amet nisl. Aliquam semper ipsum sit amet velit.
Suspendisse id sem consectetuer libero luctus adipiscing.

*   Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
    Aliquam hendrerit mi posuere lectus. Vestibulum enim wisi,
    viverra nec, fringilla in, laoreet vitae, risus.
*   Donec sit amet nisl. Aliquam semper ipsum sit amet velit.
    Suspendisse id sem consectetuer libero luctus adipiscing.
```

### Links

 * Links must not be denoted with the URLs in-line to the link text, references must be used when possible.
 * References may either be by text, or simply numerically referenced. If they are referenced numerically, a space must be inserted between the link text and the reference.

```
You should try [MCProHosting]! [Github] [1] is also pretty kick-ass!

[MCProHosting]: https://mcprohosting.com
[1]: https://github.com
```

### Emphasis and Bolding

 * Emphasis and bolding must be done using asterisks.

```
Some **bold** text and some *italic* text!
```
