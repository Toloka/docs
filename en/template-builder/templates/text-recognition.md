# Text recognition from an image (OCR)

For this type of project, you can use the **Text recognition from an image (OCR)** preset.

This preset is designed to identify and transcribe text in images for training text recognition algorithms or to verify and fine-tuning the output of your OCR models.

Take a look at the example: the labeling interface includes an image, matching text, and a response field. The Toloker will be able to select the option **No business** if there is no business in the photo, the photo is of bad quality, the name is not fully visible, the photo didn't load.

Note that validation and task layout are already configured in this Template Builder sample code.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/L4S3M6dO3fhFNB)

{% cut "Components used in the example" %}

- [view.list](../reference/view.list.md): displays data in a list.

- [view.image](../reference/view.image.md): displays an image.

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

- [view.text](../reference/view.text.md): displays a block with text.

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

If you need to display text with formatting, use the [view.markdown](../reference/view.markdown.md) component. Note that the `view.markdown` component is resource-intensive and might overload weak Toloker devices.

- A combination of [helper.if](../reference/helper.if.md) and [condition.equals](../reference/condition.equals.md): hides the response field if **No business** is selected.

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

- [field.checkbox](../reference/field.checkbox.md): add a checkbox control.

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

- [plugin.toloka](../reference/plugin.toloka.md): customizes the task layout.

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
    "label": "Look at the photo and find a sign with the business's name.",
    "noBorder": true,
    "rotatable": true,
    "url": {
      "type": "data.input",
      "path": "image"
    }
  }
  ```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/srUYLJFX3fhJvr)

## Add a layout {#add-layout}

To enhance Toloker's experience, you can highlight different types of data with colors using [view.alert](../reference/view.alert.md). You can place it in the [view.list](../reference/view.list.md) along with the `view.image` and the `view.text` components.

In this example, the text is highlighted with a blue border.

{% cut "Show code" %}

```json
  {
    "type": "view.alert",
    "theme": "info",
    "content": {
      "type": "view.text",
      "content": "Look at the photo and find a sign with the business's name."
    }
  }
  ```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/lN3DPZ5X3fkZyX)

{% include [contact-support](../_includes/contact-support.md) %}