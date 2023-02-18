# Product photo search

For this type of project, you can use the **Product photo search** preset.

This preset helps Tolokers find and upload product images.

Take a look at the example:  the template includes a product description, links to search in Google, and an upload area.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/8verSatf3yR3cu)

{% cut "Components used in the example" %}

- [view.text](../reference/view.text.md): To add text to the task.
- [view.link-group](../reference/view.link-group.md): To group links together.
- [helper.search-query](../reference/helper.search-query.md): To create a search query.
- A combination of [helper.if](../reference/helper.if.md) and [condition.equals](../reference/condition.equals.md): To hide the photo upload field if “No photo found” is selected.
- [field.checkbox](../reference/field.checkbox.md): To add a checkbox.
- A combination of [condition.any](../reference/condition.any.md), [condition.required](../reference/condition.required.md), and [condition.equals](../reference/condition.equals.md): To check that either the product image is uploaded or the **No photo found** option is selected.
- [plugin.toloka](../reference/plugin.toloka.md): To customize the task layout.

{% endcut %}

{% include [toloka-tb-source-add-media](../_includes/toloka-tb-source/id-toloka-tb-source/add-media.md) %}

If this template doesn't meet your needs, see other examples in the **Data enrichment** section.

## Add a description {#add-description}

To add a detailed description to the task, use the [view.text](../reference/view.text.md) component.

{% cut "Show code" %}

```json
{
  "type": "view.text",
  "content": "Search for photos by the name or SKU."
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/VWELiMXg3yh24N)

## Add a response field {#add-text-area}

To let Tolokers leave comments about the task or their response, add a text field using [field.textarea](../reference/field.textarea.md).

{% cut "Show code" %}

```json
{
  "type": "field.textarea",
  "label": "Comments",
  "placeholder": "Enter text",
  "data": {
    "type": "data.output",
    "path": "comment"
  }
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/WE4imhN33yh6Ww)

## Add a layout {#add-layout}

To enhance Toloker's experience, you can highlight different types of data with colors using [view.alert](../reference/view.alert.md). In this example, the text is highlighted with a blue border.

{% cut "Show code" %}

```json
  {
    "type": "view.alert",
    "theme": "info",
    "content": {
      "type": "view.text",
      "content": "Search for photos by the name or SKU."
    }
  }
  ```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/W60xAmR23yh9mM)

## Add conditions {#dependencies}

The [helper.if](../reference/helper.if.md) component displays an interface element after a specific response is selected.

{% cut "Show code" %}

```json
{
    "type": "helper.if",
    "condition": {
      "type":"condition.equals",
      "data":{
        "type":"data.output",
        "path": "not-found"
      },
    "to": "error"
    },
    "then": {
      "type": "field.textarea",
      "label": "Please, leave your comment",
      "placeholder":"Enter text",
      "data": {
        "type": "data.output",
        "path": "comment"
        }
    }
  }
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/rysQ_p7a3y9KTo)



{% include [contact-support](../_includes/contact-support.md) %}