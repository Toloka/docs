# Product category classification

For this type of project, you can use the **Product category classification** preset.

This preset is used for labeling search queries with product categories for training classifiers and NLP models.

Take a look at the example: the interface includes a link with a search query and a group of radio buttons for categories.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/hIAM0y4q4GsHEe)

{% cut "Components used in the example" %}

- [view.list](../reference/view.list.md): Displays data in a list.

- [view.link](../reference/view.link.md): A link to the site.

  {% cut "Show code" %}

  ```json
  {
    "type": "view.link",
    "content": {
      "type": "data.input",
      "path": "query"
    },
    "label": "Search query",
    "url": {
      "type": "helper.search-query",
      "query": {
        "type": "data.input",
        "path": "query"
      },
      "engine": "google"
    }
  }
  ```

  {% endcut %}

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

If you need to display formatted text, use the [view.markdown](../reference/view.markdown.md) component. Note that this setting is resource-intensive and might overload Tolokers' devices that aren't powerful enough.

{% cut "Show code" %}

```json
{
  "type": "view.markdown",
  "content": "**Read the query and choose a category that matches it.**"
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/wlqqNXQN4J8hx8)

## Add a layout {#add-layout}

To enhance Toloker's experience, you can highlight different types of data with colors using [view.alert](../reference/view.alert.md). You can place it in the [view.list](../reference/view.list.md) along with the other components.

In this example, the text is highlighted with a blue border.

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

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/c-fhh6MV4JT2by)

## Add a condition {#add-condition}

If the query doesn't match any of the categories, add a **Select category** checkbox using the [field.checkbox](../reference/field.checkbox.md) component.

{% cut "Show code" %}

```json
{
  "type": "field.checkbox",
  "preserveFalse": true,
  "label": "Select category.",
  "hint": "Activate this option if you can choose a category for a query.",
  "data": {
    "type": "data.output",
    "path": "found"
  }
},
{
  "type": "helper.if",
  "condition": {
    "type": "condition.equals",
    "data": {
      "type": "data.output",
      "path": "found"
    },
    "to": false
  },
  "then": {
    "type": "field.radio-group",
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
    "disabled": true,
    "data": {
      "type": "data.output",
      "path": "not_found"
    }
  },
  "else": {
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
    "disabled": false,
    "data": {
      "type": "data.output",
      "path": "category"
    }
  }
}
```
{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/GXxHO6hk4J94Ho)

## Add an image {#add-image}

You can add an image that matches the query to your task using [view.image](../reference/view.image.md).

{% cut "Show code" %}

```json
{
  "type": "view.image",
  "maxWidth": 350,
  "url": {
    "type": "data.input",
    "path": "imagepath"
  }
}
```
{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/0n5SpUJE4J9nwK)


## Add a response field {#add-text-area}

To let Tolokers leave comments about the task or their response, add a text field using [field.textarea](../reference/field.textarea.md).

{% cut "Show code" %}

```json
{
  "type": "field.textarea",
  "label": "Leave your comment",
  "placeholder": "Enter text",
  "data": {
    "type": "data.output",
    "path": "comment"
  }
}
```
{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/EPe5fSc34J9gWf)


## See also {#see-also}

- [Image and search query comparison](../../guide/tutorials/image-classification.md#search)


{% include [contact-support](../_includes/contact-support.md) %}