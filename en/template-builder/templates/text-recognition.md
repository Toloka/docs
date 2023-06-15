# Text recognition from an image (OCR)

For this type of project, you can use the **Text recognition from an image (OCR)** preset.

This preset is used for interpreting information from a photo. 

Take a look at the example: the labeling interface includes an image, a response field, and a checkbox for reporting on problems with an image.

Note that validation and task layout are already configured in this Template Builder sample code.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/-q-TcuZy3ttDnk)

{% cut "Components used in the example" %}

- [view.list](../reference/view.list.md): Displays data in a list.

- [view.image](../reference/view.image.md): Adds an image.

  {% cut "Show code" %}

  ```json
  {
    "type": "view.image",
    "noBorder": true,
    "rotatable": true,
    "url": {
      "type": "data.input",
      "path": "image"
    }
  }
  ```
  {% endcut %}

- [view.text](../reference/view.text.md): Displays a block with text.

  If you need formatted text, use the [view.markdown](../reference/view.markdown.md) component.

  {% cut "Show code" %}

  ```json
  {
    "type": "view.text",
    "label": "Category",
    "content": {
      "type": "data.input",
      "path": "category"
    }
  }
  ```
  {% endcut %}

- A combination of [helper.if](../reference/helper.if.md) and [condition.equals](../reference/condition.equals.md): Displays the response field when the checkbox is not selected.

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
          "type": "field.text",
          "label": "Business name",
          "placeholder": "Enter text",
          "data": {
            "type": "data.output",
            "path": "output"
          },
          "validation": {
            "type": "condition.required"
          }
        }
      ]
    }
  }
  ```

  {% endcut %}

- [field.text](../reference/field.text.md): Adds a field for entering a short text.

  Use the [conditions.required](../reference/conditions.md) component inside the `validation` property to check that a Toloker filled in the text field.

  {% cut "Show code" %}

  ```json
  {
    "type": "field.text",
    "label": "Business name",
    "placeholder": "Enter text",
      "data": {
        "type": "data.output",
        "path": "output"
      }
    "validation": {
      "type": "condition.required"
    }
  }
  ```

  {% endcut %}

- [field.checkbox](../reference/field.checkbox.md): Adds a checkbox.

  {% cut "Show code" %}

  ```json
  {
    "type": "field.checkbox",
    "preserveFalse": true,
    "label": "No business",
    "hint": "There is no business in the photo, the photo is of bad quality, the name is not fully visible, the photo didn't load",
      "data": {
        "type": "data.output",
        "path": "not_found"
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
      "taskWidth": 650
    }
  }
  ```

  {% endcut %}

{% endcut %}

If this template doesn't meet your needs, see other examples in the **Images** section.

## Add a description {#add-description}

To add a detailed description to the task, use the `label` property of the [view.image](../reference/view.image.md) component.

{% cut "Show code" %}

```json
{
  "type": "view.image",
  "label": "Look at the photo and find the business name",
  "noBorder": true,
  "rotatable": true,
  "url": {
    "type": "data.input",
    "path": "image"
  }
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/FKmvxOnh3ttDoT)

## Add a clarifying question

To ask Tolokers to clarify their choice if they selected the **No business** checkbox, add the [helper.if](../reference/helper.if.md) component which contains [field.radio-group](../reference/field.radio-group.md).

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
    "to": true
  },
  "then": {
    "type": "field.radio-group",
    "label": "To clarify your choice, select one of the options:",
    "options": [
      {
        "label": "There is no business in the photo",
        "value": "no_business"
      },
      {
        "label": "The photo is of bad quality",
        "value": "bad_quality"
      },
      {
        "label": "The name is not fully visible",
        "value": "not_fully_visible"
      },
      {
        "label": "Loading error",
        "value": "error"
      }
    ],
    "data": {
      "type": "data.output",
      "path": "option"
    },
    "validation": {
      "type": "condition.required",
      "hint": "Select one option"
    }
  }
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/iEyXcTb04GW3db)

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
      "content": "Look at the photo and find the business name"
    }
  }
  ```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/H9oHYWVb3ttDqV)

## Add a field for comments {#add-text-area}

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

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/8Fp9udrO3ttDrM)

## Add keyboard shortcuts {#add-shortcuts}

Add keyboard shortcuts to rotate and zoom in images in the [plugin.hotkeys](../reference/plugin.hotkeys.md) configuration.

{% cut "Show code" %}

```json
{
  "type": "plugin.hotkeys",
  "l": {
    "type": "action.rotate",
    "view": {
      "$ref": "view.items.0"
    },
    "payload": "left"
  },
  "r": {
    "type": "action.rotate",
    "view": {
      "$ref": "view.items.0"
    },
    "payload": "right"
  },
  "q": {
    "type": "action.open-close",
    "view": {
      "$ref": "view.items.0"
    }
  }
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/G0W2K6e_3ttDsj)

{% include [contact-support](../_includes/contact-support.md) %}