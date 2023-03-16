# Named Entity Recognition (NER)

For this type of project, you can use the **Named Entity Recognition (NER)** preset.

This preset helps you identify parts of speech, proper nouns, and other entities in the text.

Take a look at the example: the labeling interface includes a text block and buttons for categories.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/-WB38I-Y3xvU3M)

{% cut "Components used in the example" %}

- [field.text-annotation](../reference/field.text-annotation.md): A component for text segmentation.

    {% cut "Show code" %}

    ```json
    {
      "type": "field.text-annotation",
      "content": {
        "type": "data.input",
        "path": "input"
      }
    }
    ```

    {% endcut %}

- [condition.required](../reference/condition.required.md): Checks that the data is filled in.

    {% cut "Show code" %}

    ```json
    {
      "type": "condition.required"
    }
    ```

    {% endcut %}

{% endcut %}

{% include [toloka-tb-source-add-media](../_includes/toloka-tb-source/id-toloka-tb-source/add-media.md) %}

If this template doesn't meet your needs, see other examples in the **Text** section.

## Add a description {#add-description}

To add a detailed description to the task, use the [view.text](../reference/view.text.md) component.

{% cut "Show code" %}

```json
{
  "type": "view.text",
  "content": "In the text provided, find information about the product and manufacturer and highlight it with different colors: red for product name, blue for brand, green for package size, pink for country of manufacture. If a word is misspelled, highlight it with yellow."
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/CaVc0G9O44eWpp)

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

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/FYqX4xd63yQyPz)

## Add a layout {#add-layout}

To enhance Toloker's experience, you can highlight different types of data with colors using [view.alert](../reference/view.alert.md). In this example, the text is highlighted with a blue border.

{% cut "Show code" %}

```json
{
  "type": "view.alert",
  "theme": "info",
  "content": {
    "type": "view.text",
    "content": "In the text provided, find information about the product and manufacturer and highlight it with different colors: red for product name, blue for brand, green for package size, pink for country of manufacture. If a word is misspelled, highlight it with yellow."
  }
}
  ```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/ahNzXcDI3yQzD3)

## Add keyboard shortcuts {#add-shortcuts}

Assign keyboard shortcuts for selecting categories using [plugin.field.text-annotation.hotkeys](../reference/plugin.field.text-annotation.hotkeys.md) configuration.

{% cut "Show code" %}

```json
"plugins": [
  {
    "type": "plugin.field.text-annotation.hotkeys",
    "labels": [
      "1",
      "2",
      "3",
      "4",
      "5"
    ]
  }
]
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/W5ddd6ZJ44eZbB)

{% include [contact-support](../_includes/contact-support.md) %}