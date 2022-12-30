# Accessories recommendations

For this type of project, you can use the **Accessories recommendations** preset.

This preset is designed to identify products that go together to train your store's recommendation system.

Take a look at the example: the labeling interface includes two images and several radio buttons. Note that validation, keyboard shortcuts, and task layout are already configured in this Template Builder sample code.

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/02zo1PEd3scPcM)

{% cut "Components used in the example" %}

- [view.list](../reference/view.list.md): Displays data in a list.

- [view.text](../reference/view.text.md): Adds a block with text.

  {% cut "Show code" %}

  ```json
  {
    "type": "view.text",
    "label": "Is the second item a good recommendation for the first one?"
  }
  ```

  {% endcut %}

- [view.image](../reference/view.image.md): Displays an image.

  The [layout.columns](../reference/layout.columns.md) component places two images next to each other.

  {% cut "Show code" %}

  ```json
  {
    "type": "layout.columns",
    "items": [
      {
        "type": "view.image",
        "label": {
          "type": "data.input",
          "path": "title_1"
        },
        "url": {
          "type": "data.input",
          "path": "image_1"
        }
      },
      {
        "type": "view.image",
        "label": {
          "type": "data.input",
          "path": "title_2"
        },
        "url": {
          "type": "data.input",
          "path": "image_2"
        }
      }
    ]
  }
  ```

  {% endcut %}

- [field.button-radio-group](../reference/field.button-radio-group.md): Adds buttons for selecting an answer option.

  The [condition.required](../reference/condition.required.md) component inside the `validation` property checks if at least one option is selected.

  {% cut "Show code" %}

  ```json
  {
    "type": "field.button-radio-group",
    "options": [
      {
        "label": "Good recommendation",
        "value": "ok"
      },
      {
        "label": "Bad recommendation",
        "value": "bad"
      }
    ],
    "data": {
      "type": "data.output",
      "path": "result"
    },
    "validation": {
      "type": "condition.required",
      "hint": "Please choose an option"
    }
  }
  ```

  {% endcut %}

- [plugin.hotkeys](../reference/plugin.hotkeys.md): : Adds [keyboard shortcuts](../best-practices/hotkeys.md).

  {% cut "Show code" %}

  ```json
  {
    "type": "plugin.hotkeys",
    "1": {
      "type": "action.set",
      "data": {
        "type": "data.output",
        "path": "result"
      },
      "payload": "ok"
    },
    "2": {
      "type": "action.set",
      "data": {
        "type": "data.output",
        "path": "result"
      },
      "payload": "bad"
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

{% endcut %}

{% include [toloka-tb-source-add-media](../_includes/toloka-tb-source/id-toloka-tb-source/add-media.md) %}

If this preset doesn't meet your needs, see other examples in this section.

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

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/eyjfv6xy3scQDR)

## Add a layout {#add-layout}

To enhance Toloker's experience, you can highlight different types of data with colors using [view.alert](../reference/view.alert.md). You can place it in the [view.list](../reference/view.list.md) along with the other components.

In this example, the description is highlighted with a blue border, and the buttons are highlighted with a yellow one.

{% cut "Show code" %}

```json
  {
    "type": "view.alert",
    "theme": "info",
    "content": {
      "type": "view.text",
      "content": "Is the second item a good recommendation for the first one?"
    }
  },
  {
    "type": "view.alert",
    "theme": "warning",
    "content":{
      "type": "field.button-radio-group",
      "options": [
        {
          "label": "Good recommendation",
          "value": "ok"
        },
        {
          "label": "Bad recommendation",
          "value": "bad"
        }
      ],
      "data": {
        "type": "data.output",
        "path": "result"
      }
      "validation": {
      "type": "condition.required",
      "hint": "Please choose an option"
      }
    }
  }
  ```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/hZdJe0Yk3scQnS)

## Other options for buttons {#add-variants}

Decide whether a Toloker can select only one or multiple answer options.

{% list tabs %}

- Multiple options (checkboxes)

  If there are several possible answers, use the [field.checkbox-group](../reference/field.checkbox-group.md) component.

  {% cut "Show code" %}

  ```json
  {
    "type": "field.checkbox-group",
    "label": "Select the statements that apply to both products:",
    "options": [
      {
        "label": "Product category is “Candy and chocolate”.",
        "value": "1"
      },
      {
        "label": "The type of chocolate is “Milk”.",
        "value": "2"
      },
      {
        "label": "The flavor is “Chocolate and caramel”.",
        "value": "3"
      },
      {
        "label": "The form is “Chocolate bar”.",
        "value": "4"
      }
    ],
    "data": {
      "type": "data.output",
      "path": ""
    },
    "validation": {
      "type": "condition.required",
      "hint": "Select one or more options"
    }
  }
  ```

  {% endcut %}

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/F5edFPVq3seM9p)

- One option (a radio button)

  The [field.button-radio-group](../reference/field.button-radio-group.md) component is displayed as solid buttons. It's better to use these buttons if the question has 2–4 short answer options.

  If there are more answer options, or they are long, it's better to use [field.radio-group](../reference/field.radio-group.md), as in the example.

  {% cut "Show code" %}

  ```json
  {
    "type": "field.radio-group",
    "label": "Choose the correct statement:",
    "options": [
      {
        "label": "The products belong to the category “Candy & Chocolate”.",
        "value": "1"
      },
      {
        "label": "The products belong to the category “Ice Creams & Frozen Juices”.",
        "value": "2"
      }
    ],
    "data": {
      "type": "data.output",
      "path": "result"
    },
    "validation": {
      "type": "condition.required",
      "hint": "Please choose an option"
    }
  }
  ```

  {% endcut %}

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/nvnq7AUA3seNqp)

{% endlist %}

## Add clarifying questions to one of the options {#add-addition}

The [helper.if](../reference/helper.if.md) component displays an interface element after a specific response is selected. In this example, a Toloker can answer the question about recommendation only if both images loaded.

  {% cut "Show code" %}

```json
  {
    "type": "helper.if",
    "condition": {
      "type": "condition.equals",
      "data": {
        "type": "data.output",
        "path": "loaded"
      },
      "to": "yes"
    },
    "then": {
      "type": "field.button-radio-group",
      "options": [
        {
          "label": "Good recommendation",
          "value": "ok"
        },
        {
          "label": "Bad recommendation",
          "value": "bad"
        }
     ],
      "data": {
        "type": "data.output",
        "path": "result"
      },
      "validation": {
        "type": "condition.required",
        "hint": "Please choose an option"
      }
    }
  }
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/iWh2lB3X3sktQY)

If you need to check sequentially more than two conditions, use the [helper.switch](../reference/helper.switch.md) component.

{% include [contact-support](../_includes/contact-support.md) %}