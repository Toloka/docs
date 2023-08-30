# Форматирование текста

{% include [deprecate](../../_includes/deprecate.md) %}

Если вы хотите вставить отформатированный текст, таблицу или список, используйте компонент [view.markdown](../reference/view.markdown.md). В этом разделе мы покажем, как вставить блок в разметке Markdown в интерфейс задания в Толоке.

{% note info %}

Компонент [view.markdown](../reference/view.markdown.md) — ресурсозатратный и может нагружать слабые устройства исполнителей.

Не используйте этот компонент для отображения простого текста. Если вам надо отобразить текст без форматирования, используйте компонент [view.text](../reference/view.text.md). Если надо вставить ссылку — [view.link](../reference/view.link.md), а если изображение — [view.image](../reference/view.image.md).

{% endnote %}

Содержимое блока указывается в свойстве `content`:
```json
{
  "type"   : "view.markdown",
  "content": "_Курсивный текст_"
}
```

{% cut "Пример основного синтаксиса Markdown" %}

Ниже представлен код, охватывающий основной синтаксис Markdown. Посмотрите в [песочнице](https://ya.cc/t/CItaz_xm3tw2MF), как можно использовать этот код в компоненте [view.markdown](../reference/view.markdown.md).

Обратите внимание, что код перед вставкой в конструктор шаблонов был отредактирован в соответствии с [ограничениями](#specs).

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

[link text](https://dev.nodeca.com)

[link with title](https://nodeca.github.io/pica/demo/ "title text!")

Autoconverted link https://github.com/nodeca/pica (enable linkify to see)

## Images

![Minion](https://octodex.github.com/images/minion.png)

Like links, Images also have a footnote style syntax

![Alt text][id]

With a reference later in the document defining the URL location:

[id]: https://octodex.github.com/images/dojocat.jpg  "The Dojocat"
````

{% endcut %}

## Особенности вставки кода в разметке Markdown {#specs}

Поскольку конструктор шаблонов использует в своей основе JSON, существуют некоторые ограничения, которые необходимо учитывать, вставляя код в разметке Markdown в свойство `content`.
- Содержимое свойства `content` записывается в одну строку, поэтому все переносы строк необходимо заменять на специальный знак переноса: ``\n``.
- Символ универсальной кавычки (`"`) необходимо экранировать с помощью обратного слеша: `\"`.

```json
{
  "type"   : "view.markdown",
  "content": "# Заголовок \n **Отформатированный текст c \"кавычками\"**"
}
```

[![](../_images/buttons/contact-support.svg)](../concepts/support.md)

{% include [image-styles](../../../_includes/image-styles-internal.md) %}