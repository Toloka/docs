# Product category classification

For this type of project, you can use the **Product category classification** preset.

You can use this preset to classify, rate or moderate content. It can also be used for labeling search queries with product categories for training classifiers and NLP models.

Take a look at the example: the interface includes a text box for the query and radio buttons for categories.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/hIAM0y4q4GsHEe)

{% cut "Components used in the example" %}

- [view.list](../reference/view.list.md): Displays data in a list.

- [view.link](../reference/view.link.md): A link to the site.

- [field.radio-group](../reference/field.radio-group.md): Adds radio buttons for selecting an answer option.

  {% cut "Show code" %}

  ```json
  {
    "type": "field.radio-group",
    "validation": {
      "type": "condition.required"
    },
    "label": "Choose category",
    "options": [
      {
        "label": "Devices",
        "value": "devices",
        "hint": "Smartphones, laptops, game consoles, robots and things for smart home, portable audio etc."
      },
      {
        "label": "Clothing",
        "value": "clothing",
        "hint": "Clothing for men, women, kids (all the types)."
      },
      {
        "label": "Sports",
        "value": "sports",
        "hint": "Goods for sports, camping, hiking, recreation, exercises, fitness etc."
      },
      {
        "label": "Home",
        "value": "home",
        "hint": "Furniture, kitchen, dining, decor (including holiday decor), bedding, bath, lighting etc."
      }
    ],
    "data": {
      "type": "data.output",
      "path": "category"
    }
  }
  ```

  {% endcut %}

- [plugin.hotkeys](../reference/plugin.hotkeys.md): Adds [keyboard shortcuts](../best-practices/hotkeys.md).

  {% cut "Show code" %}

  ```json
  {
    "1": {
      "type": "action.set",
      "data": {
        "type": "data.output",
        "path": "category"
      },
      "payload": "devices"
    },
    "2": {
      "type": "action.set",
      "data": {
        "type": "data.output",
        "path": "category"
      },
      "payload": "clothing"
    },
    "3": {
      "type": "action.set",
      "data": {
        "type": "data.output",
        "path": "category"
      },
      "payload": "sports"
    },
    "4": {
      "type": "action.set",
      "data": {
        "type": "data.output",
        "path": "category"
      },
      "payload": "home"
    },
    "type": "plugin.hotkeys"
  }
  ```

  {% endcut %}

  - [plugin.toloka](../reference/plugin.toloka.md): Customizes the task layout.

  {% cut "Show code" %}

  ```json
  {
    "type": "plugin.toloka",
    "layout": {
      "kind": "scroll",
      "taskWidth": 500
    }
  }
  ```
  {% endcut %}

{% endcut %}

## Add a description {#add-description}

To add a detailed description to the task, use the [view.text](../reference/view.text.md) component.

{% cut "Show code" %}

```json

{
  "type": "view.text",
  "content": "Read the query and choose a category that matches it:"
}

```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/rfXWGflu4Gtyw2)

## Add a layout {#add-layout}

To enhance Toloker's experience, you can highlight different types of data with colors using [view.alert](../reference/view.alert.md). In this example, the task description is highlighted with a blue border.

{% cut "Show code" %}

```json
{
  "type": "view.alert",
  "theme": "info",
  "content": {
    "type": "view.text",
    "content": "Read the query and choose a category that matches it:"
  }
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/huY1NSah4Gu8Tq)

## Add a checkbox {#add-checkbox}

If the query doesn't match any of the categories, add a **No category** checkbox using the [field.checkbox](../reference/field.checkbox.md) component.  

{% cut "Show code" %}

```json
{
  "type": "field.checkbox",
  "preserveFalse": true,
  "label": "No category",
  "hint": "This query doesn't match any of the categories above",
  "data": {
    "type": "data.output",
    "path": "no_category"
  }
}
```
{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/fvtHcWAX4Gtwvk)

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

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/YJk8Xfgw4Gu9FR)


{% include [contact-support](../_includes/contact-support.md) %}