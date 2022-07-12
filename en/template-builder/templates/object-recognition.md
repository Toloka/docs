# Object recognition & detection

For this type of project, you can use the **Object recognition & detection** preset.

This preset is intended to outline objects on images for training computer vision to detect them.

Take a look at the example: the labeling interface includes an image with bounding boxes, polygons, or key points. Note that validation, keyboard shortcuts, and task layout are already configured in this example.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/Bv2ocvkf3Vbvhr)

{% cut "Components used in the example" %}

- [field.image-annotation](../reference/field.image-annotation): Lets you select areas using points, rectangles, and polygons.

  {% cut "Show code" %}

  ```json
  {
    "type": "field.image-annotation",
    "image": {
      "type": "data.input",
      "path": "image"
    },
    "fullHeight": true,
    "data": {
      "type": "data.output",
      "path": "result"
    },
    "validation": {
      "type": "condition.required",
      "hint": "Please select an area"
    }
  }
  ```
  {% endcut %}

- [condition.required](../reference/condition.required.md): Checks if at least one area is selected.

  {% cut "Show code" %}

  ```json
  {
     "type": "condition.required",
     "hint": "Please select an area"
   }
  ```

  {% endcut %}

- [plugin.toloka](../reference/plugin.toloka.md): Customizes the task layout.

  {% cut "Show code" %}

  ```json
  {
    "type": "plugin.toloka",
    "layout": {
      "kind": "pager"
    }
  }  
  ```

  {% endcut %}
  
- [plugin.field.image-annotation.hotkeys](../reference/plugin.field.image-annotation.hotkeys.md): Sets hotkeys to select area types and selection modes and to confirm or cancel area creation.

  {% cut "Show code" %}

  ```json
  {
      "type": "plugin.field.image-annotation.hotkeys",
      "labels": [
        "1",
        "2",
        "3",
        "4",
        "5"
      ],
      "modes": {
        "select": "q",
        "point": "w",
        "rectangle": "e",
        "polygon": "r"
      },
      "confirm": "a",
      "cancel": "s"
    }
  ```

  {% endcut %}

{% endcut %}

{% include [toloka-tb-source-add-media](../_includes/toloka-tb-source/id-toloka-tb-source/add-media.md) %}

If this preset doesn't meet your needs, see other examples in this section.

## What else can be configured {#add-more}

To add a detailed description to the task, use the [view.text](../reference/view.text.md) component.

{% cut "Show code" %}

```json
{
  "type": "view.text",
  "content": "Look at the picture and select a green traffic light."
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)]()

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

  [![](../_images/buttons/view-example.svg)]()

[![image](../_images/buttons/contact-support.svg)](../concepts/support.md)