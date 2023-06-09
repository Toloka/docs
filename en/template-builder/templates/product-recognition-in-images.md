# Product recognition in images

For this type of project, you can use the **Product recognition in images** preset.

This preset is used for recognizing products in images by labeling objects and areas.

Take a look at the example: the labeling interface includes an image and a bounding box.

Note that validation and task layout are already configured in this Template Builder sample code.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/wWPxyb2K4Fb2Aq)

{% cut "Components used in the example" %}

- [view.list](../reference/view.list.md): Displays data in a list.

- [view.markdown](../reference/view.markdown.md): Displays a text in Markdown.

  {% cut "Show code" %}

  ```json
  {
    "type": "view.markdown",
    "content": {
      "type": "helper.join",
      "items": [
        "**Clothes category**:",
          {
            "type": "data.input",
            "path": "category"
          }
        ],
      "by": " "
    }
  }
  ```
  {% endcut %}

  Note that the `view.markdown` component is resource-intensive and might overload weak Toloker devices. Do not use this component to display plain text. If you need to display text without formatting, use the [view.text](../reference/view.text.md) component.

  - [field.image-annotation](../reference/field.image-annotation.md): Lets you select areas using points, rectangles, and polygons.

  {% cut "Show code" %}

  ```json
  {
    "type": "field.image-annotation",
    "image": {
      "type": "data.input",
      "path": "image"
      },
    "data": {
      "type": "data.output",
        "path": "result"
      },
    "fullHeight": true,
    "shapes": {
      "rectangle": true
    },
    "validation": {
      "type": "condition.required"
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
    "modes": {
      "select": "q",
      "rectangle": "e"
    },
    "confirm": "a",
    "cancel": "x"
  }
  ```

  {% endcut %}

{% endcut %}

If this template doesn't meet your needs, see other examples in the **Images** section.

## Add a description {#add-description}

To add a detailed description to the task, use the `label` property of the [field.image-annotation](../reference/field.image-annotation.md) component.


{% cut "Show code" %}

```json
{
  "type": "field.image-annotation",
  "label": "Look at the picture and outine the product",    
  "image": {
     "type": "data.input",
     "path": "image"
  },
  "data": {
     "type": "data.output",
     "path": "result"
  },
  "fullHeight": true,
  "shapes": {
     "rectangle": true
  },
  "validation": {
     "type": "condition.required"
  }
} 
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/zW4MLt1O4FgaBk)


## Add a layout {#add-layout}

To enhance Toloker's experience, you can highlight different types of data with colors using [view.alert](../reference/view.alert.md). You can place it in the [view.list](../reference/view.list.md) along with the `field.image-annotation` component.

In this example, the text is highlighted with a blue border.

```json
{
  "type": "view.alert",
  "theme": "info",
  "content": {
    "type": "view.text",
    "content": "Look at the picture and outline a product"
  }
},
```

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/QB7ZXAcB4Fgciy)

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

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/IifhWjIL4FgnF8)


{% include [contact-support](../_includes/contact-support.md) %}




