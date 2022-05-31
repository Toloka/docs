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

{% cut "Example of the core Markdown syntax" %}

The code below demonstrates the basic Markdown syntax. Use the [sandbox](https://tb.yandex.net/editor?config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0AtgIYBOAawAmEElDwAaTDVqQodIgrZ4AxFgAWARiwAJIr2FwoCdJlXqNAJj0GjJs1AuWAzLcPHT555oAs7+y8nZ0sAVgDPRxCLTQA2CIdMRyj1XQh+OAAvaDpeABssACUAVzyiAGdkzAB9WqqoAFom+oAqNvqUrABRbiYNXnK4SqTMNoAVDSGsKYAjCDzhLEUADzp2kahaianZ+cWVujqNlu3y6bO4XLy4MCWiVZb66tPz6aubu9Xq+oA-H4BlOgZQREOgafgQYoIDR-DreLAAITyEDAggAjsUIIphhINgA+RHI1EYrEVLBgXjYfLlCBYGZELBQCqKYScNmOPEEtmcGYMLDFQYmLCGIx0ODQfJYBD8AyKfgNMGUrCDBBQM4ZaF0Rn3LV0WkGMAaLBYjREfjcjlYAlctnpLAkS5G8pMXhgMn0ugkIhKYX8CEkcqcOHBLAAGSGdBxjgAqlB0sIzURhPUANRYADCMt4imFWGu5S1vOVuX4YqFvDzxgZDrBWAABim65J6w0m8b+PWWnXHGn-sUZg185HfQy+Am6XzjAmFJ4sDZna6KshHDgGlgALICEEdw0CV1y8n9EwMmDpN1nJkkSsF4sCOjLmQ0FpYACCtyBEbgGIZ13pEKw+DzMUdAulq2YrjQaYAGKunA+Y7NgTAymKxTcIyQwFPkX7FKCEGrlgABypR5BWgF5MBoHCtcGK8Gh+BENcdA9lgABqZp8gY5QMAAhPUADy-AJjKyYbFonBhukRBoXATDlKhWCiMiHaDGB3C4ZgVjiem0DlEQYCKHQxQdh4TBDGAs4MZcjguOJACSChEAgZpYNw8zMsQeaSWh2YuQM5S8MGYlYAAmpC5JKgKDK6d+M6SlAqF-oG7KYEF3J2iCRBMFRBRggy8XcIlwpnHWYndhsgJ3oyCVmrONZGhAMAwLp971KEADs4mnhAjhBTMAjBjE2kJvU9nXEy9aQAmZW4lA9nTiy5IQMNGyyAA9KtWD-BAamLdwakKDishjQyOgNYty3UDgx1zsaMDnawj5XVWWBuGdk0PTNjhIiigj3bgZggDASjnmYeD1HWEOOP8tFMGUnxaqaMoWpgEPTZ0Yy8DMZRRpgAA+WB8UwYrQFg+MACIVGAGRE+K2C444+NNEza6M8zbMswzCnZhWOD46BRp6lzuRYPA2NLLSclMLDfK5ULFaKlqDp5AU9JYC65S6YsxiC4ovQkdi4n03jWBKAgz346bz2C6rkWLKeHZISiFSCggdx69mFTibolLCGUfX8BcZyywmMC8KUdCG5zOqyBbqxKIMJPWwytsi3aCY3qLnuk-UhSIBoYHXKqSaLeR3BqvU+OE8TdNYBT5RUzJ1fZ8b7PIKz7NM23nPCNzNB89mAu0j3wuZ0HEvFFLeQy6actLP0itwSrDLq5r0wKLSuuwx7gbN1AFsmObJsH+NSf8qv9tqxC54u27W8G3oPt+wIgdzwyIdh3kEe77HWp9ybcdqlpuLOkydz5p2ZCLOCWcjafXhOGKAggcZQAANpjV+gcAAugACnziBZA60Ez4E4HGBMFJOCQG4AASnqKg4wv06pLEuGUbBuCmD4NWiQvSvBOBmzBP2Tg4pVqmQpKtBMrkNqg3oEwhkBxeIA2oRsF8wEUTQHoqWYuaDNB0BAuUdhvCND8IoRwpaXChE3ArFgpQmM4ZoLgDAGWEtvQKNgSGWyfAnJIO4sg9cxhaYsO0bJdhKI9QJmWDwx0hjtqrTgO4ioq1uC+OgJwJgJhnGOHDCCSsCDyjNjcbwDxVEaSaF4PRXMXU6BxhzAWBgcMuIKF4MseoXiXyf3hhg5BcBhAYPqAAdUdLmGUQMZRQDdHmD2HZjCvwUiiVCSgtQh18UKWW0ZCihk8hSauD4ZodK6RQVhuj1rBJMWE-RkTuDRNieUUREAABWKJsycBuUwV2-08ATAZGTW59ymIAzBtQAAvpgf5IBJAgGMEwYCKA0DAv+UAA&locale=en) to see how you can use this code in the [view.markdown](../reference/view.markdown.md) component.

Note that before being inserted into the Template Builder, the code was edited to meet the [restrictions](#specs).
````
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
````

{% endcut %}

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


[![image](../_images/buttons/contact-support.svg)](../concepts/support.md)
