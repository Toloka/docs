# Product recognition in images

For this type of project, you can use the **Product recognition in images** preset.

You can use this preset to classify, rate or moderate content. The preset can also be used to label images for computer vision training.

Take a look at the example: the interface includes an image and tools for labeling objects and areas within it.

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

## Add product categories {#add-categories}

If you need to categorize selected items, create labels for each category using the `labels` property of the [field.image-annotation](../reference/field.image-annotation.md) component. Note that if you use labels, you need to add at least two.

In this example, three buttons are used in the interface for selecting three categories of products: shoes, jeans and dresses. 

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
  "labels": [
    {
      "label": "Shoes",
      "value": "shoes"
    },
    {
      "label": "Jeans",
      "value": "jeans"
    },
    {
      "label": "Dress",
      "value": "dress"
    }
  ],
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

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/giq8piZW4GVZst)

## Add a checkbox and a clarifying question {#add-checkbox}

You can add a checkbox for reporting on problems with an image. 

To ask Tolokers to clarify their choice if they selected the **Cannot label the product** checkbox, add the [helper.if](../reference/helper.if.md) component which contains [field.radio-group](../reference/field.radio-group.md).

{% cut "Show code" %}

```json
{
  "type": "field.checkbox",
  "preserveFalse": true,
  "label": "Cannot label the product",
  "hint": "There is no product in the photo, the photo is of bad quality, the product is not fully visible, the photo didn't load",
  "data": {
    "type": "data.output",
    "path": "not_found"
  }
},
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
        "label": "There is no product in the photo",
        "value": "no_product"
      },
      {
        "label": "The photo is of bad quality",
        "value": "bad_quality"
      },
      {
        "label": "The product isn't fully visible",
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

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/SS0ShREc4GVp4Q)


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




