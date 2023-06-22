# Product recognition in images

For this type of project, you can use the **Product recognition in images** preset.

You can use this preset to classify, rate or moderate content. It can also be used to label images for computer vision training.

Take a look at the example: the interface includes an image and tools for labeling objects and areas within it.

Note that validation, keyboard shortcuts, and task layout are already configured in this example.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/wWPxyb2K4Fb2Aq)

{% cut "Components used in the example" %}

- [view.list](../reference/view.list.md): Displays data in a list.

- [view.markdown](../reference/view.markdown.md): Adds a block for displaying text in Markdown.

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

- [field.image-annotation](../reference/field.image-annotation.md): Adds a tool for labeling objects or areas within an image using points, rectangles, and polygons.

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
  "label": "Look at the photo and highlight the product that belongs to the specified category with a rectangular selection.",
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

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/gSVMk1wW4H8FVF)


## Add a layout {#add-layout}

To enhance Toloker's experience, you can highlight different types of data with colors using [view.alert](../reference/view.alert.md). You can place it in the [view.list](../reference/view.list.md) along with the `field.image-annotation` component.

In this example, the text is highlighted with a blue border.

```json
{
  "type": "view.alert",
  "theme": "info",
  "content": {
    "type": "view.text",
    "content": "Look at the photo and highlight the product that belongs to the specified category with a rectangular selection."
  }
}
```

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/b61nCEsv4H8Jzn)

## Add a field for comments {#add-text-area}

To let Tolokers leave comments about the task or their response, add a text field using [field.textarea](../reference/field.textarea.md).

{% cut "Show code" %}

```json
{
  "type": "field.textarea",
  "label": "Leave your comment",
  "hint": "Describe what product you see in the picture, enter the brand name etc.",
  "placeholder": "Enter text",
  "data": {
    "type": "data.output",
    "path": "comment"
  }
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/0jiq2cxp4HA8wV)

## Add product categories {#add-categories}

If you need to categorize selected products, create labels for each category using the `labels` property of the [field.image-annotation](../reference/field.image-annotation.md) component. Note that if you use labels, you need to add at least two.

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

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/EQ7JhH7S4H8Nn3)

## Add a checkbox and a clarifying question {#add-checkbox}

You can add a checkbox for reporting on problems with an image. 

To ask Tolokers to clarify their choice if they selected the **Cannot label the product** checkbox, add the [field.checkbox](../reference/field.checkbox.md) component and the [helper.if](../reference/helper.if.md) component which contains [field.radio-group](../reference/field.radio-group.md).

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
    ]
  }
},
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

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/jT4KtnJs4HRWJF)


## Add a control checkbox {#add-control-checkbox}

If you want to allow labeling only after a certain condition has been set, use the `disabled` property of the [field.image-annotation](../reference/field.image-annotation.md) component.

In this example, a checkbox has been added so that users could label the photos where there is no product. Tolokers will be able to highlight products only if the **Product in the photo** option is activated.

{% cut "Show code" %}

```json
{
  "type": "field.checkbox",
  "preserveFalse": true,
  "label": "Product in the photo.",
  "hint": "Activate this option if you can see a product in the photo.",
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
    "disabled": true,
    "shapes": {
      "rectangle": true
    }
  },
  "else": {
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
    "disabled": false,
    "shapes": {
      "rectangle": true
    },
    "validation": {
      "type": "condition.required"
    }
  }
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/PKPUJ4ne4HRaiQ)

{% include [contact-support](../_includes/contact-support.md) %}




