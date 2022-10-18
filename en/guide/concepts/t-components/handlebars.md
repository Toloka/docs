# Expressions and helpers

{% note info %}

The task interface configuration guide describes the features of the HTML/JS/CSS editor. You can also try creating a task interface in [Template Builder](https://toloka.ai/en/docs/template-builder/reference/).

{% endnote %}

Handlebars is a template engine that uses templates to simplify HTML creation.

Templates look like regular HTML code with [Handlebars expressions](#expressions) added to it. When the template is executed, the expressions are replaced with the input parameter values.

The `toloka-handlebars-templates` library is connected to the project by default. It contains a set of components and the `TolokaHandlebarsTask` and `TolokaHandlebarsTaskSuite` classes that are added to the basic `[TolokaTask](../js/task.md)` and `[TolokaTaskSuite](../js/tasksuite.md)` classes and extend them.

## Expressions {#expressions}

Expressions are enclosed in double curly brackets. In this case, their value is automatically escaped.

```html
<input type="text" placeholder="not_var{{i18n.hint}}" name="{{concat "field_" name}}" value="not_var{{value}}">
```

If you need an unescaped value, you can:

- Put it in triple brackets: `{not_var{{raw}}}`

- Write a helper that will return the unescaped value: `return new Handlebars.SafeString(value)`

    {% note warning %}

    Please note that this isn't safe! Always check the input data that you display in the template. You can escape the data in the helper using the `Handlebars.Utils.escapeExpression` method.

    {% endnote %}

To get the value of a nested parameter in the Handlebars expression, separate the parameter names with a dot.

For example, if you have code in JSON format

```json
{
    "id": 123,
    "link": {
        "title": "<b>Toloka</b>",
        "url": "https://toloka.ai"
    }
}
```

and you want to pull the values of the `title` and `url` parameters nested in `link` from it, specify the path to them using the dot separator:

```html
id: not_var{{id}}<a href="not_var{{link.url}}">not_var{{link.title}}</a>
```

Comments are also Handlebars expressions: `{{!comment}}` or `{{!-- comment --}}`.

## Helpers {#helpers}

Helpers are functions that you can use to pass any number of expressions. After processing the result, they return HTML code.

You can register your helper using the `Handlebars.registerHelper` method. Example:

The helper for escaping the `title` parameter from the above [code in JSON format](#example-json):

```html
Handlebars.registerHelper('escape', (title, url) => new Handlebars.SafeString(`<a href="${Handlebars.escapeExpression(url)}">${Handlebars.escapeExpression(title)}</a>`));
```

Calling the helper:

```html
not_var{{escape link.title link.url}}
```

The result is HTML code with the escaped `title` parameter. The tag added in the helper remains unchanged:

```html
<a href="https://toloka.ai"><b>Toloka</b></a>
```

Helpers can have other helpers as input. For this, enclose them in round brackets:

```html
{{or (equal title "Toloka") (equal title "Google")}}
```

{% note info %}

Before creating your own Handlebars helper, look it up:

- In the list of [available Toloka components and helpers](../t-components.md).

- In the [repository of Handlebars helpers](https://github.com/helpers/handlebars-helpers).

{% endnote %}

## Block helpers {#block-helpers}

Block helpers contain the functions for calling a passed block in a new context.

To indicate that you're calling a block helper, add a lattice to its name: `{{#if}}`. Unlike regular helpers, block helpers need to be closed. The block helper is closed in the same way as a regular tag: `{{/if}}`.

Handlebars already has built-in block helpers: [If](#if), [Unless](#unless), [Each](#each), [With](#with).

[Learn more about block helpers](https://handlebarsjs.com/guide/block-helpers.html#the-with-helper)

### If {#if}

Block output by condition. If the argument of this helper returns "false," the block inside the helper will not be executed:

```html
{{#if (equal id "123")}}
    ... {{!Code block only for id 123}}
not_var{{else}}
    ... {{!Code block for all other values}}
{{/if}}
```

### Unless {#unless}

The opposite of the `if` helper. Outputs the block if the argument returns "false."

```html
{{#unless (equal id "123")}}
    ... {{!Code block for all id values different from 123}}
not_var{{else}}
    ... {{!Code block only for id 123}}
{{/unless}}
```

### Each {#each}

The helper for sorting lists. To access the current item in the list, use `this`.

{% note info %}

To access an item that's not in the current block context, go up a level by using `../`

{% endnote %}

For example, for a list

```json
{
    "id": 123,
    "links": [
        { "url": "https://toloka.ai", "title": "Toloka" },
        { "url": "https://google.com", "title": "Google" }
    ]
}
```

, the helper that outputs the values of each list item (in this case, links) will look like this:

```html
{{#each links}}
    ID: {{../id}}
    <a href="not_var{{this.url}}">not_var{{this.title}}</a>
{{/each}}
```

Inside the `Each` block, the following auxiliary expressions are available:

- `{{@key}}` — Name of the current key.
- `{{@index}}` — Current index.
- `{{@first}}` — True if it is the first element of the array.
- `{{@last}}` — True if it is the last element of the array.

In the above [list](#example-json-2), the helper

```html
{{#each links}}
    Global ID: {{../id}}
    {{@index}}: <a href="not_var{{this.url}}">not_var{{this.title}}</a>
    {{#unless @last}}<hr>{{/unless}}
{{/each}}
```

will display links.

- The links will be numbered.
- A horizontal separator will be added after each link, except the last one.

### With {#with}

Rebinds the context.

For example, for code

```json
{
    "id": 123,
    "link": {
        "title": "<b>Toloka</b>",
        "url": "https://toloka.ai"
    }
}
```

, the helper that displays the block in a different context, which helps to avoid using the name of the parent parameter, will look like this:

```html
ID: not_var{{id}}
{{#with link}}
    <a href="not_var{{url}}">not_var{{title}}</a>
{{/with}}
```

## Reusing templates (partials) {#partials}

Partials allow you to reuse sections of code. They are regular templates that can be called by other templates. Example:

You need to display the same type of layout in several places:

```html
<h3>Field</h3>
{{field type="input" name="field_name"}}
```

To avoid copying the code, you can register a new partial:

```html
Handlebars.registerPartial('formInput', '<h3>not_var{{fieldTitle}}</h3>{{field type="input" name=fieldName}}');
```

Calling a template to insert a layout into the form:

```html
{{> formInput fieldTitle="Field 1" fieldName="my_field"}}
<p>Paragraph with text</p>
{{> formInput fieldTitle="Field 2" fieldName="some_other_field"}}
```

Result:

```html
<h3>Field 1</h3>
{{field type="input" name="my_field"}}
<p>Paragraph with text</p>
<h3>Field 2</h3>
{{field type="input" name="some_other_field"}}
```

{% include [contact-support](../../_includes/contact-support-help.md) %}