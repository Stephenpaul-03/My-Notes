## Definition
- **Markdown** is a lightweight markup language used for formatting plain text.
- Created by *John Gruber* in 2004.

## Syntax

### Headings
Use `#` followed by a space for headings.

```markdown
# Heading 1
## Heading 2
### Heading 3
#### Heading 4
##### Heading 5
###### Heading 6

Heading 1
=========

Heading 2
---------
```

### Paragraphs
Paragraphs are created by leaving a blank line without indentation.

### Emphasis
- *Italics*: `*text*` or `_text_`
- **Bold**: `**text**` or `__text__`
- ***Bold & Italics***: `***text***` or `___text___`

**Line Break:** End a line with two spaces and press Enter.

```markdown
Line one.  
Line two.
```

### Blockquotes
Use `>` to create blockquotes.

```markdown
> Simple Blockquote
>> Nested Blockquote
```

Blockquotes can contain headings, emphasis, lists, and more.

### Code Blocks
Indent 4 spaces or use fenced code blocks.

```markdown
    <html>
        <head>
        <title>Example</title>
        </head>
    </html>
```

### Lists

**Ordered List**
```markdown
1. First Item
2. Second Item
    1. Sub Item
    2. Sub Item
3. Third Item
```

**Unordered List**
```markdown
- First Item
- Second Item
    + Sub Item
    + Sub Item
- Third Item
```

### Images
```markdown
![Alt Text](source/image.png)
```

### Inline Code
Use backticks (\`) for inline code.

```markdown
This is `inline code`
```

### Links
```markdown
[Example](https://www.example.com "Title")

<https://www.example.com>
<example@mail.com>

*[Italic Link](https://www.example.com)*  
**[Bold Link](https://www.example.com)**
```

### Horizontal Lines
```markdown
***
---
___
```

### Escape Characters
Use backslash `\` before a special character.

## Extended Syntax

### Tables
```markdown
| X | Y | Z |
|:--|:-:|--:|
| A | B | C |
| D | E | F |
| Left | Mid | Right |
```

### Fenced Code Blocks
Use three backticks or tildes.

```markdown
```json
{
  "Test": "Success"
}
```
```

or

~~~
{
  "Test": "Success"
}
~~~
```

### Footnotes
```markdown
This is a footnote reference[^1]

[^1]: This is the footnote text.
```

### Definition Lists
```markdown
Term 1
: Definition 1

Term 2
: First Definition
: Second Definition
```

### Strikethrough
```markdown
This is ~~strikethrough~~ text.
```

### Task Lists
```markdown
- [x] Completed Task
- [ ] Incomplete Task
```
