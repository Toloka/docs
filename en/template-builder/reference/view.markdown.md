# view.markdown

Block for displaying text in Markdown.

The contents of the block are written to the `content` property in a single line. To insert line breaks, use `\n`. Straight quotation marks (`"`) must be escaped like this: `\"`.

Examples of Markdown syntax:

```
# Level 1 header
## Level 2 header (and so on to level 6)

**Bold**

* Italics*

~~Crossed out text~~

+ Bulleted list
  + List sublevels are separated by two additional spaces
- The list can start with any of these characters: + - *

1. Numbered list
2. The second item in the list

[Text with link] (http://example.com/)

![Image] (http://example.com/image.png)
```

You can find documentation for the basic Markdown syntax in this [article](https://guides.github.com/features/mastering-markdown/).

[View example in the sandbox](https://clck.ru/Rnt2g).

Note that the `view.markdown` component is resource-intensive and might overload weak user devices. Do not use this component to display plain text. If you need to display text without formatting, use the [view.text](view.text.md) component. If you need to insert a link, use [view.link](view.link.md), and for an image use [view.image](view.image.md).

Links with Markdown are appended with `target="_blank"` (the link opens in a new tab), as well as `rel="noopener noreferrer"`.

## Component properties {#properties}

| Name                                     | Type                                                                                   | Description                           |
| ---------------------------------------- | -------------------------------------------------------------------------------------- | ------------------------------------- |
| `type`<span style="color: red">\*</span> | "view.markdown"                                                                        | <p>Set component type</p>             |
| `label`                                  | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Label above the component.</p>     |
| `content`                                | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Text in Markdown.</p>              |
| `hint`                                   | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Hint text.</p>                     |
| `validation`                             | <a class="xref popup-link" href="../concepts/types.dita#types/condition">condition</a> | <p>Validation based on condition.</p> |
