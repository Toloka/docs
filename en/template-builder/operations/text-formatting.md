# Text formatting

If you want to insert some formatted text, table, or list, use the [view.markdown](../reference/view.markdown.md) component. This section shows how to insert a Markdown text block into the Toloka task interface.

{% note info %}

The [view.markdown](../reference/view.markdown.md) component is resource-intensive and may overload low-end user devices.

Don't use this component to display plain text. If you need to display text without formatting, use the [view.text](../reference/view.text.md) component. Use [view.link](../reference/view.link.md) to insert a link and [view.image](../reference/view.image.md) to insert an image.

{% endnote %}

The block content is specified in the `content` property:
```json
{
  "type"   : "view.markdown",
  "content": "_Italic text_"
}
```

#### Example of the core Markdown syntax

The code below demonstrates the basic Markdown syntax. Use the  to see how you can use this code in the [view.markdown](../reference/view.markdown.md) component.

Note that before being inserted into the Template Builder, the code was edited to meet the [restrictions](#specs).
```
# h1 Heading
## h2 Heading
### h3 Heading
#### h4 Heading
##### h5 Heading
###### h6 Heading


## Horizontal Rules

___

---

***


## Emphasis

**This is bold text**

__This is bold text__

*This is italic text*

_This is italic text_

~~Strikethrough~~


## Blockquotes


> Blockquotes can also be nested...
>> ...by using additional greater-than signs right next to each other...
> > > ...or with spaces between arrows.


## Lists

Unordered

+ Create a list by starting a line with `+`, `-`, or `*`
+ Sub-lists are made by indenting 2 spaces:
  - Marker character change forces new list start:
    * Ac tristique libero volutpat at
    + Facilisis in pretium nisl aliquet
    - Nulla volutpat aliquam velit
+ Very easy!

Ordered

1. Lorem ipsum dolor sit amet
2. Consectetur adipiscing elit
3. Integer molestie lorem at massa


1. You can use sequential numbers...
1. ...or keep all the numbers as `1.`

Start numbering with offset:

57. foo
1. bar


## Code

Inline `code`

Indented code

    // Some comments
    line 1 of code
    line 2 of code
    line 3 of code


Block code "fences"

```
Sample text here...
```

## Tables

| Option | Description |
| ------ | ----------- |
| data   | path to data files to supply the data that will be passed into templates. |
| engine | engine to be used for processing templates. Handlebars is the default. |
| ext    | extension to be used for dest files. |

Right aligned columns

| Option | Description |
| ------:| -----------:|
| data   | path to data files to supply the data that will be passed into templates. |
| engine | engine to be used for processing templates. Handlebars is the default. |
| ext    | extension to be used for dest files. |


## Links

[link text](http://dev.nodeca.com)

[link with title](http://nodeca.github.io/pica/demo/ "title text!")

Autoconverted link https://github.com/nodeca/pica (enable linkify to see)


## Images

![Minion](https://octodex.github.com/images/minion.png)

Like links, Images also have a footnote style syntax

![Alt text][id]

With a reference later in the document defining the URL location:

[id]: https://octodex.github.com/images/dojocat.jpg  "The Dojocat"
```

## Specifics of inserting Markdown code {#specs}

Since Template Builder is JSON-based, there are some restrictions for inserting Markdown code into the `content` property.
- The value of the `content` property has a single-line format. Make sure to replace all the line breaks with ``\n``.
- Make sure to escape double-quotes inside text values (`"`) with backslashes: `\"`.

```json
{
  "type"   : "view.markdown",
  "content": "# Header \n **Formatted text with \"double quotes\"**"
}
```


[![](../_images/buttons/contact-support.svg)](../concepts/support.md)
