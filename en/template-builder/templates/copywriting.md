# Copywriting

For projects of this type, you can use the **Generating product descriptions** preset.

This preset helps to create a description of products based on the image and its name.

Take a look at an example: the labeling interface includes an image, text data, and a text input area. 

Note that validation, keyboard shortcuts, and task layout are already configured in this template designer code example.

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/YEsaR2Qj3ynhRS)

{% cut "Components used in the example" %}

- [view.list](../reference/view.list.md): Displays data in a list.

- [layout.columns](../reference/layout.columns.md): Places the image in a separate column to the left of other interface elements.

  {% cut "Show code" %}

  ```json
  {
    "type": "layout.columns",
    "items": [
	....
	]
  }
  ```
  {% endcut %}
  
- [view.image](../reference/view.image.md): Image.

  {% cut "Show code" %}

  ```json
  {
    "type": "view.image",
    "url": {
       "type": "data.input",
       "path": "image"
    },
    "fullHeight": true,
    "ratio": [
        2,
        1
    ]
  }
  ```
  {% endcut %}
  
- [view.text](../reference/view.text.md): Shows the text from the task input data.

  {% cut "Show code" %}

  ```json
  {
    "type": "view.text",
    "content": {
       "type": "data.input",
       "path": "breed"
    },
    "label": "Cat breed"
  }
  ```
  {% endcut %}
  
- [view.action-button](../reference/view.action-button.md): The button that triggers the action.

  {% cut "Show code" %}

  ```json
  {
    "type": "view.action-button",
    "label": "Google Search",
    "action": {
        "type": "action.open-link",
        "payload": {
            "type": "data.input",
            "path": "search_url"
        }
    }
  }
  ```
  {% endcut %}
  
- [field.textarea](../reference/field.textarea.md): Text input field.

  {% cut "Show code" %}

  ```json
  {
    "type": "field.textarea",
    "data": {
       "type": "data.output",
       "path": "result"
    },
   "label": "Describe this breed of cat",
   "validation": {
       "type": "condition.required",
       "hint": "enter your text\n"
    }
  }
  ```
  {% endcut %}
  
- [condition.required](../reference/condition.required.md): Checks if the text field is filled in.

  {% cut "Show code" %}

  ```json
  {
    "type": "condition.required",
    "hint": "Select an option"
  }
  ```
  {% endcut %}

- [plugin.toloka](../reference/plugin.toloka.md): Customizes the task width.

  {% cut "Show code" %}

  ```json 
  {
    "type": "plugin.toloka",
    "layout": {
      "kind": "scroll",
      "taskWidth": 1200
    }
  }
  ```
  {% endcut %}

{% endcut %}

If this template doesn't meet your needs, see other examples in the **Text**.

## Set the desired text length {#text-length}

To set the desired text length, use the [condition.schema](../reference/condition.schema.md) component instead of [condition.required](../reference/condition.required.md). It won't let a Toloker submit a response if the text they entered is longer or shorter than specified.

{% cut "Show code" %}

 ```json
 {
    "type": "condition.schema",
    "schema": {
     "type": "string",
     "minLength": 500,
     "maxLength": 2000
    },
    hint": "Enter a text that's between 500 and 2000 characters long"
 }
 ```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/_CWxs3QH3z2WcY)

## Use short single-line text field {#short-text-field}

For short single-line text, use the [field.text](../reference/field.text.md) component instead of [field.textarea](../reference/field.textarea.md).

{% cut "Show code" %}

 ```json
 {
   "type": "field.text",
    "data": {
       "type": "data.output",
       "path": "result"
    }
 }
 ```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/LJs6Z3fk3z2fCU)

## Add a description {#add-description}

To add a detailed description to the task, use the `label` property of the [view.image](../reference/view.image.md) component.

{% cut "Show code" %}

```json
{
  "type": "view.text",
  "content": "Siberian cat is a popular breed in Russia."
}

```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/RHGfVYiX3z3TBy)

## Add a layout {#add-layout}

To enhance Toloker's experience, you can highlight different types of data with colors using [view.alert](../reference/view.alert.md). 

You can place it in the [view.list](../reference/view.list.md) along with the other components.

In this example, the description is highlighted with a blue border, and the text field is green.

{% cut "Show code" %}

```json
{
  "type": "view.alert",
  "theme": "info",
  "content": {
     "type": "view.text",
     "content": "Siberian cat is a popular breed in Russia."
    }
},
{
  "type": "view.alert",
  "theme": "success",
  "content": {
     "type": "field.textarea",
     "data": {
         "type": "data.output",
         "path": "result"
        },
     "label": "Describe this breed of cat:",
     "validation": {
         "type": "condition.required",
         "hint": "Enter your text"
        }
    }  
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/o9-Xt8o-3z4DTq)

## Remove an image {#remove-image}

For tasks where images or columns are not required, use a simplified example without them.

{% cut "Show code" %}

```json
{
  "plugins": [
    {
      "type": "plugin.toloka",
      "layout": {
        "kind": "scroll",
        "taskWidth": 600
      }
    }
  ],
  "view": {
    "type": "view.list",
    "items": [
      {
        "type": "view.list",
        "items": [
          {
            "type": "view.text",
            "label": "Text for translation",
            "content": {
              "type": "data.input",
              "path": "text"
            }
          }
        ]
      },
      {
        "type": "view.list",
        "items": [
          {
            "type": "field.textarea",
            "label": "How would you say this in Spanish?",
            "data": {
              "type": "data.output",
              "path": "result"
            },
            "validation": {
              "type": "condition.required"
            }
          }
        ]
      }
    ]
  }
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/RYB77BTQ3ttFMj)

## Add a condition {#dependencies}

The [helper.if](../reference/helper.if.md) component displays an interface element after a specific response is selected.

Parameters can be displayed using: [field.radio-group](../reference/field.radio-group.md), [field.button-radio-group](../reference/field.button-radio-group.md), [field.checkbox](../reference/field.checkbox.md). 

{% list tabs %}

- Radio buttons

  Use the [field.radio-group](../reference/field.radio-group.md) component.

  {% cut "Show code" %}

   ```json
  {
    "type": "helper.if",
    "condition": {
      "type": "condition.equals",
      "data": {
          "type": "data.output",
          "path": "verdict"
        },
      "to": "bad"
    },
    "then": {
     "type": "field.textarea",
     "data": {
         "type": "data.output",
         "path": "error_description"
        },
        "label": "Describe the error",
        validation": {
           "type": "condition.required",
           "hint": "enter something in the box"
        }
    }
  }

  ```

  {% endcut %}
  
  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/cCnptYRg3ttFNe)

- Buttons

  Use the [field.button-radio-group](../reference/field.button-radio-group.md) component.

  {% cut "Show code" %}

   ```json
  {
    "type": "helper.if",
    "condition": {
      "type": "condition.equals",
      "data": {
          "type": "data.output",
          "path": "verdict"
        },
      "to": "bad"
    },
    "then": {
     "type": "field.textarea",
     "data": {
         "type": "data.output",
         "path": "error_description"
        },
        "label": "Describe the error",
        validation": {
           "type": "condition.required",
           "hint": "enter something in the box"
        }
    }
  }

  ```

  {% endcut %}
  
  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/qXZ539523ttFPL)

- Checkbox

  Use the [field.checkbox](../reference/field.checkbox.md) component.
  
  {% cut "Show code" %}

   ```json
  {
    "type": "helper.if",
    "condition": {
      "type": "condition.equals",
      "data": {
          "type": "data.output",
          "path": "verdict"
        },
      "to": "bad"
    },
    "then": {
     "type": "field.textarea",
     "data": {
         "type": "data.output",
         "path": "error_description"
        },
        "label": "Describe the error",
        validation": {
           "type": "condition.required",
           "hint": "enter something in the box"
        }
    }
  }

  ```

  {% endcut %}
  
  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/-Zd32wl73ttFQ3)

{% endlist %}

## Use multiple columns {#several-columns}

To compare two texts, place them in adjacent columns using the [layout.columns](../reference/layout.columns.md) component. It allows you to set the column width and vertical alignment.

The [view.group](../reference/view.group.md) component adds frames around the texts to visually separate them from each other and make them easier to read.

The third column in the example contains two input fields for Tolokers to write their text.

 {% cut "Show code" %}

 ```json
 {
    "type": "layout.columns",
    "fullHeight": true,
    "items": [
      {
        "type": "view.group",
        "label": {
          "type": "data.input",
          "path": "title1"
        },
        "content": {
          "type": "view.text",
          "content": {
            "type": "data.input",
            "path": "text1"
          }
        }
      },
      {
        "type": "view.group",
        "label": {
          "type": "data.input",
          "path": "title2"
        },
        "content": {
          "type": "view.text",
          "content": {
            "type": "data.input",
            "path": "text2"
          }
        }
      },
    ....
	]
 }
  ```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/EtNLEAun3ttFNK)

## Allow a Toloker adding input fields {#dynamic-field-add}

This is a complex example that consists of four main parts.

{% cut "Components used in the example" %}

- [view.image](../reference/view.image.md): Image.
- [field.radio-group](../reference/field.radio-group.md): Response selection options.
- [field.text](../reference/field.text.md): The text input field.
- [field.list](../reference/field.list.md): A button that adds new text input fields.

{% endcut %}

What's unique about this example is that a Toloker can add and remove text input fields.

In addition, the example checks that each line has at least three characters, including letters and spaces. The condition is implemented using [condition.schema](../reference/condition.schema.md).


 {% cut "Show code" %}

 ```json
 {
   "type": "condition.schema",
   "schema": {
      "type": "string",
      "minLength": 3,
      "pattern": "^[А-Яа-яЁёa-zA-Z\\s]+$"
    }
  }
  ```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/T-rVMAPk3vvtDM)

{% include [contact-support](../_includes/contact-support.md) %}