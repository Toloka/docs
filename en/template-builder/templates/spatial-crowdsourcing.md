# Spatial Crowdsourcing

For this type of project, you can use the **Spatial Crowdsourcing** preset.

This preset is used for field tasks in the Toloka mobile app. The Toloker selects a point on the map, goes to the location, takes photos, and writes a comment.

{% note info %}

This preset uses [HTML/JS/CSS editor](../../guide/concepts/spec.md), but you can use the [Template Builder](index.md) for the same purpose. To get that done, copy the code from the example, in the **Task interface** section of your project select the **Template builder** option and paste the code to the **Config** section.

{% endnote %}

Take a look at the example: the interface includes a text field, a button for uploading the coordinates of the Toloker's device, a button for uploading photos, and a comment field.

Note that validation and task layout are already configured in this Template Builder sample code.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/ZFj9dvvG3Zg9Xw)

{% cut "Components used in the example" %}

- [view.list](../reference/view.list.md): Displays data in a list.

- [view.text](../reference/view.text.md): Displays a block with text.

  If you need formatted text, use the [view.markdown](../reference/view.markdown.md) component.

  {% cut "Show code" %}

  ```json
  {
    "type": "view.text",
    "label": "Store name:",
    "content": {
      "type": "data.input",
      "path": "name"
    }
  }
  ```
  {% endcut %}

- [view.divider](../reference/view.divider.md): Displays a horizontal delimiter.

- [view.action-button](../reference/view.action-button.md): Adds a button that calls an action.

  In this example, when the button is clicked, the coordinates of the Toloker's device will be transmitted, when they are within 50 meters of the specified location. To change this condition, replace the value of the `max` property with the desired distance. The combination of [condition.distance](../reference/condition.distance.md) and [@yandex-toloka/data.location](../reference/data.location.md) will allow you to check that the coordinates are transmitted and that they correspond to those that you set.

  {% cut "Show code" %}

  ```json
  {
    "type": "view.action-button",
    "label": "Share your coordinates",
    "action": {
      "type": "action.set",
      "payload": {
        "type": "@yandex-toloka/data.location"
      },
      "data": {
        "type": "data.output",
        "path": "worker_coordinates"
      }
    },
    "validation": {
      "type": "condition.all",
      "conditions": [
        {
          "type": "condition.required",
          "hint": "Click to share your coordinates",
          "data": {
            "type": "data.output",
            "path": "worker_coordinates"
          }
        },
        {
          "type": "@yandex-toloka/condition.distance",
          "hint": "you are too far away from the location.",
          "from": {
            "type": "@yandex-toloka/data.location"
          },
          "to": {
            "type": "data.input",
            "path": "position"
          },
          "max": 50
        }
      ]
    }
  }
  ```
  {% endcut %}

- [field.media-file](../reference/field.media-file.md): Adds a button for uploading photos.

  Use the [conditions.required](../reference/conditions.md) component inside the `validation` property to check that a Toloker uploaded photos.

  {% cut "Show code" %}

  ```json
  {
    "type": "field.media-file",
    "label": "Find a local business",
    "accept": {
      "photo": true
    },
    "multiple": true,
      "data": {
        "type": "data.output",
        "path": "photo"
      },
    "validation": {
      "type": "condition.required",
      "hint": "Attach photos of the organization."
    }
  }
  ```

  {% endcut %}

- [field.textarea](../reference/field.textarea.md): Adds a box for entering multi-line text.

  {% cut "Show code" %}

  ```json
  {
    "type": "field.textarea",
    "label": "Comments",
    "placeholder": "If your photos don't contain all the necessary information, add details here.",
      "data": {
        "type": "data.output",
        "path": "comment"
      }
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
      "taskWidth": 600
    }
  }
  ```

  {% endcut %}

{% endcut %}

If this template doesn't meet your needs, see other examples in the **Field tasks** section.

## Add a description {#add-description}

To add a detailed description to the task, replace the sample text with your value in the `label` property of the [view.text](../reference/view.text.md) component.

{% cut "Show code" %}

```json
{
  "type": "view.text",
  "label": "Find a local business in your city:",
  "content": {
    "type": "data.input",
    "path": "name"
  }
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/LdkIIKSv3nS2oL)

## Add a layout {#add-layout}

To enhance Toloker's experience, you can highlight different types of data with colors using [view.alert](../reference/view.alert.md). You can place it in the [view.list](../reference/view.list.md) along with the other components.

In this example, the text is highlighted with a blue border.

{% cut "Show code" %}

```json
  {
    "type": "view.alert",
    "theme": "info",
    "content": {
      "type": "view.text",
      "label": "Find a local business in your city:",
      "content": {
        "type": "data.input",
        "path":"name"
      }
    }
  }
  ```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/a6I75hXP3nS2wX)

{% include [contact-support](../_includes/contact-support.md) %}