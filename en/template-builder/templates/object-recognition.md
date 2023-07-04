# Object recognition & detection

For this type of project, you can use the **Object recognition & detection** preset.

This preset is designed to outline objects in images for training computer vision to detect them.

Take a look at the example: the labeling interface includes an image with bounding boxes, polygons, or key points. Note that validation, keyboard shortcuts, and task layout are already configured in this example.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/ajl1SJ1d3ttCsE)

{% cut "Components used in the example" %}

- [field.image-annotation](../reference/field.image-annotation.md): Lets you select areas using points, rectangles, and polygons.

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

## Add a description {#add-description}

To add a detailed description to the task, use the `label` property of the [field.image-annotation](../reference/field.image-annotation.md) component.

{% cut "Show code" %}

```json
{
  "type": "field.image-annotation",
  "image": {
    "type": "data.input",
    "path": "image"
  },
  "fullHeight": true,
  "label": "Look at the picture and outine the road signs",
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

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/J3wI38wh3ttCtn)

## Add a response field {#add-text-area}

To let Tolokers leave comments about the task or their response, add a text field using [field.textarea](../reference/field.textarea.md). You can place it in the [view.list](../reference/view.list.md) along with the `field.image-annotation` component.

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

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/PWIhgNqi3ttCvX)

## Add a layout {#add-layout}

To enhance Toloker's experience, you can highlight different types of data with colors using [view.alert](../reference/view.alert.md). You can place it in the [view.list](../reference/view.list.md) along with the `field.image-annotation` component.

In this example, the text is highlighted with a yellow border.

{% cut "Show code" %}

```json
{
  "type": "view.alert",
  "theme": "warning",
  "content": {
    "type": "view.text",
    "content": "Look at the picture and outline the road signs"
  }
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/CD_JTa4r3ttCx9)

## See also {#see-also}

- [Tutorials: Object recognition & detection](../../guide/tutorials/selection.md)

{% include [contact-support](../_includes/contact-support.md) %}