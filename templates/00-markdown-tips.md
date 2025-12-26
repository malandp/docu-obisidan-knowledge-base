# What is markdown?
Markdown is a lightweight markup language that lets you format text using plain, readable characters. It’s designed to be fast, simple, and easy to write.

Below are some tips and pointers to get you started to have nicely formatted markdown files!

---
# Top-level heading
Start with a `#` and leave a space after before typing text
"# Top-level heading" 
## Section heading
Start with a `##` and leave a space after before typing text
"## Section heading"
### Sub-section
Start with a `###` and leave a space after before typing text
"### Sub-section"

## Section break/line
Simply write `---`

---
## Text formatting
**bold text**: Enclose with `**` i.e. \*\*TEXT\*\*. No need for spaces
*italic text*: Enclose with `*` i.e. \*TEXT\*. No need for spaces
~~strikethrough~~: Enclose with `~~` i.e. \~\~TEXT\~\~. No need for spaces
`inline code`:  Enclose with \` i.e. \`TEXT\`. No need for spaces

## Links
Enter a simple hyperlink by enclosing with `<>:` <https://www.gooogle.com>
To pretty print links, prepend text enclosed with `[]`, and follow with link enclosed with `()`: [google](<https://www.gooogle.com>)


### TIP: Make special characters display normally
To make special characters display normally, add a `\` in front of them.
\*This would have been italic if not for the \\\*
## Quotations/Notes/Block quotes
Add a `>` in front of the text. No need for spacing.
>This is a quotation/note/block quote
## Lists
### Bullet lists
Bullet list: Start with a `-` and add a space. Tab for indent.
"- Bulleted list
	"- Nested item
	    "- Sub-item
- Bulleted list
	- Nested item
		- Sub-item

## Numbered lists
"1. Number 1
"1. Number 2
   "1. Nested numbering
   1. Number 1
   2. Number 2
	   1. Indented number

## Code blocks
Enclose with either \`\`\` or `~~~`.
The enclosing characters should be in their own line.
Specify language immediately after opening, `bash`, `yaml`, `python`, etc.

```bash
sudo apt update
sudo apt install docker
```

```python
if cool:
	put_on_glasses()
```
## Tables
Use pipe characters (`|`) to define columns and hyphens (`-`) to separate the header row from the data rows. Colons (`:`) can be used in the separator line to control text alignment within columns.

```markdown
| Header 1 | Header 2 | Header 3 |
| :------- | :------: | -------: |
| Left     |  Center  |    Right |
| Item A   |  Item B  |   Item C |
| 123      |   456    |      789 |
```

| Header 1 | Header 2 | Header 3 |
| :------- | :------: | -------: |
| Left     |  Center  |    Right |
| Item A   |  Item B  |   Item C |
| 123      |   456    |      789 |

## Linking to documents
It is useful to link to other documents for faster navigation.
To do this, enclose with `[[]]`: [[README]]
Nested files can also be linked to by using `/` to indicate nesting: [[guides/_index]]

## Special notes
Use `!` together with `>` for a comment block and enclose the text with `[]`:
`> [!note]`, `> [!warning]` etc

> [!note] This is a note with a heading
> This is a note.

> [!warning]
> This is a warning. It was not given a heading.

Below are all the options:
/> [!note]
/> [!abstract]
/> [!summary]
/> [!tldr]
/> [!info]
/> [!todo]
/> [!tip]
/> [!hint]
/> [!important]
/> [!success]
/> [!check]
/> [!done]
/> [!question]
/> [!help]
/> [!faq]
/> [!warning]
/> [!caution]
/> [!attention]
/> [!failure]
/> [!fail]
/> [!missing]
/> [!danger]
/> [!error]
/> [!bug]
/> [!example]
/> [!quote]
/> [!cite]