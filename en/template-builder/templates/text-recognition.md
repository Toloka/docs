# Text recognition from an image (OCR)

For this type of project, you can use the **Text recognition from an image (OCR)** preset.

This preset is designed to identify and transcribe text in images for training text recognition algorithms or to verify and fine-tuning the output of your OCR models.

Take a look at the example: the labeling interface includes an image, matching text, and a response field. The Toloker will be able to select the option **No business** if there is no business in the photo, the photo is of bad quality, the name is not fully visible, the photo didn't load.

Note that validation and task layout are already configured in this Template Builder sample code.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/L4S3M6dO3fhFNB)

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

  If you need to display text with formatting, use the [view.markdown](../reference/view.markdown.md) component.

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

- [field.text](../reference/field.checkbox.md): Adds a field for entering a short text.

  Use the [conditions.required](../reference/conditions.md) component inside the `validation` property to check that the Toloker filled in the text field before sending the response to the task.

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

- [field.checkbox](../reference/field.checkbox.md): Adds a checkbox control.

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
    "label": "Look at the photo and find a sign with the business name.",
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


## Add a selection option

Ask the Tolokers to clarify their decision if they have labeled **No business**: add the [field.radio-group](../reference/field.radio-group.md) so they can select one of the suggested options.

{% cut "Show code" %}

```json
  {
    "type": "field.radio-group",
    "label": "To clarify your decision, select one of the options:",
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
        "label": "The name isn not fully visible",
        "value": "not_fully_visible"
      },
      {
        "label": "Loading error",
        "value": "error"
      }
    ],
    "data": {
      "type": "data.output",
      "path": "path"
    },
    "validation": {
      "type": "condition.required",
      "hint": "Select one option"
    }
  }
  ```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/6Dj-dc5n3iax5d)

<!--
One possible solution may be to add a **None of the above** option to the radio button group. Add the [field.textarea](../reference/field.textarea.md) that would allow Tolokers to leave comments with their own version, if this option is selected.

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

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/7JAxeo6B3gfh6r)

-->

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
      "content": "Look at the photo and find a sign with the business name."
    }
  }
  ```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/lN3DPZ5X3fkZyX)

{% include [contact-support](../_includes/contact-support.md) %}