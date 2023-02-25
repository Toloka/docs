# Product photo search

For this type of project, you can use the **Product photo search** preset.

This template helps you get the photos of the products from the Internet that meet the specified parameters. The Tolokers search products by name or SKU on the Internet and upload product images.

Take a look at the example:  the template includes a product description, links to search in Google, an upload area, and a checkbox. The users must select the "No photo found" option if the photo hasn't been found.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/8verSatf3yR3cu)

{% cut "Components used in the example" %}

- [view.list](../reference/view.list.md): Displays data in a list.

- [view.text](../reference/view.text.md): Adds text to the task.

  {% cut "Show code" %}

  ```json
  {
    "type": "view.text",
    "label": "Product name",
    "content": {
      "type": "data.input",
      "path": "name"
    }
  },
  {
    "type": "view.text",
    "label": "Brand",
    "content": {
      "type": "data.input",
      "path": "brand"
    }
  },
  {
    "type": "view.text",
    "label": "SKU",
    "content": {
      "type": "data.input",
      "path": "sku"
    }
  }
  ```
  {% endcut %}

- [view.link-group](../reference/view.link-group.md): Groups links together.

  {% cut "Show code" %}
  
  ```json
  {
    "type": "view.link-group",
    "validation": {
      "type": "condition.any",
      "hint": "Search for photos by the name or SKU",
      "conditions": [
        {
          "type": "condition.link-opened",
          "url": {
            "$ref": "view.items.3.links.0.url"
          }
        },
        {
          "type": "condition.link-opened",
          "url": {
            "$ref": "view.items.3.links.1.url"
          }
        }
      ]
    },
  }
  ```

  {% endcut %}

- [helper.search-query](../reference/helper.search-query.md): Creates a search query.

  {% cut "Show code" %}

  ```json
  {
    "type": "helper.search-query",
    "query": {
      "type": "data.input",
      "path": "name"
    },
    "engine": "google/images"
  }
  ```
  {% endcut %}

- A combination of [helper.if](../reference/helper.if.md) and [condition.equals](../reference/condition.equals.md): Hides the photo upload field if **No photo found** is selected.

  {% cut "Show code" %}

  ```json
  {
    "type": "helper.if",
    "condition": {
      "type": "condition.equals",
      "data": {
        "type": "data.output",
        "path": "not_found"
      },
      "to": false
   },
    "then": {
      "type": "view.list",
      "items": [
        {
          "type": "field.file",
          "label": "Product photo",
          "data": {
            "type": "data.output",
            "path": "image"
          }
        }
      ]
    }
  }
  ```
  {% endcut %}

- [field.checkbox](../reference/field.checkbox.md): Adds a checkbox.

  {% cut "Show code" %}

  ```json
  {
    "type": "field.checkbox",
    "label": "No photo found",
    "preserveFalse": true,
    "data": {
      "type": "data.output",
      "path": "not_found"
    }
  }
  ```
  {% endcut %}

- A combination of [condition.any](../reference/condition.any.md), [condition.required](../reference/condition.required.md), and [condition.equals](../reference/condition.equals.md): Checks that either the product image is uploaded or the **No photo found** option is selected.

  {% cut "Show code" %}

  ```json
  {
    "type": "condition.any",
    "conditions": [
      {
        "type": "condition.required",
        "data": {
          "type": "data.output",
          "path": "image"
        }
      },
      {
        "type": "condition.equals",
        "data": {
          "type": "data.output",
          "path": "not_found"
        },
        "to": true
      }
    ],
    "hint": "Please, attach a file or check \"No photo found\""
  }
  ```
  {% endcut %}

- [plugin.toloka](../reference/plugin.toloka.md): Customizes the task layout.

  {% cut "Show code" %}

  ```json
  "plugins": [
    {
      "type": "plugin.toloka",
      "layout": {
        "kind": "scroll",
        "taskWidth": 500
      }
    }
  ]
  ```
  {% endcut %}

{% endcut %}

{% include [toloka-tb-source-add-media](../_includes/toloka-tb-source/id-toloka-tb-source/add-media.md) %}

If this template doesn't meet your needs, see other examples in the **Data enrichment** section.

## Add a description {#add-description}

To add a detailed description to the task, use the [view.text](../reference/view.text.md) component.

{% cut "Show code" %}

```json
{
  "type": "view.text",
  "content": "Search for photos by the name or SKU. If you couldn't find photos, select the "No photo found" option."
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/48aj5QhH42KAUg)

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

The [helper.switch](../reference/helper.switch.md) component displays an additional interface element if a certain condition is met. In this example, the Toloker first selects **Yes** if the photo has been found, and **No** if it has not. After that, depending on the selected option an additional field appears: to upload the photo or to leave a comment why the photo cannot be uploaded.  

{% cut "Show code" %}

```json
{
  "type": "field.radio-group",
  "label": "Has the photo been found?",
  "data": {
    "type": "data.output",
    "path": "photo"
  },
  "options": [
    {
      "label": "Yes",
      "value": "yes"
    },
    {
      "label": "No",
      "value": "no"
    }
  ],
  "validation": {
    "type": "condition.required",
    "hint": "Select one of the options"
  }
},
{
  "type": "helper.switch",
  "cases": [
    {
      "condition": {
        "type": "condition.equals",
        "data": {
          "type": "data.output",
          "path": "photo"
        },
        "to": "yes"
      },
      "result": {
        "type": "field.file",
        "label": "Product photo",
        "data": {
          "type": "data.output",
          "path": "image"
        },
        "validation": {
          "type": "condition.required",
          "hint": "Please, attach a photo."
        }
      }
    },
    {
      "condition": {
        "type": "condition.equals",
        "data": {
          "type": "data.output",
          "path": "photo"
        },
        "to": "no"
      },
      "result": {
        "type": "field.textarea",
        "label": "Why?",
        "placeholder": "Add comment",
        "data": {
          "type": "data.output",
          "path": "comment"
        },
        "validation": {
          "type": "condition.required",
          "hint": "Please, add comment."
        }
      }
    }
  ]
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/YnKYHVcO3zriYw)

{% include [contact-support](../_includes/contact-support.md) %}