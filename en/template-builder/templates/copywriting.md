# Copywriting

For projects of this type, you can use the **Generating product descriptions** preset.

This preset helps to create a description of products based on the image and its name.

Take a look at the example: the labeling interface includes an image, text data, button and a text input area. If the Toloker clicks on the button, a search engine opens with a request about the product. Note that validation and task layout are are already configured in this example.

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/L6DkKbbO47KQ38)

{% cut "Components used in the example" %}

- [view.list](../reference/view.list.md): Displays data in a list.

- [layout.columns](../reference/layout.columns.md): Places content in separate columns.

  {% cut "Show code" %}

  ```json
  {
    "type": "layout.columns",
    "items": [
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
      },
      {
        "type": "view.list",
        "items": [
          {
            "type": "view.text",
            "content": {
              "type": "data.input",
              "path": "title"
            },
            "label": "Title"
          },
          {
            "type": "view.action-button",
            "label": "Search product in Google",
            "action": {
              "type": "action.open-link",
              "payload": {
                "type": "data.input",
                "path": "search_url"
              }
            }
          },
          {
            "type": "field.textarea",
            "data": {
              "type": "data.output",
              "path": "result"
            },
            "label": "Describe the product in 2-3 sentences:",
            "validation": {
              "type": "condition.required",
              "hint": "Write the description in the box"
            }
          }
        ]
      }
	]
  }	
  ```
  {% endcut %}
  
- [view.image](../reference/view.image.md): Adds an image.

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
      "path": "title"
    },
    "label": "Title"
  }
  ```
  {% endcut %}
  
- [view.action-button](../reference/view.action-button.md): Displays the button that triggers the action.

  {% cut "Show code" %}

  ```json
  {
    "type": "view.action-button",
    "label": "Search product in Google",
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
  
- [field.textarea](../reference/field.textarea.md): Adds a block for entering multi-line text.

  {% cut "Show code" %}

  ```json
  {
    "type": "field.textarea",
    "data": {
      "type": "data.output",
      "path": "result"
    },
   "label": "Describe the product in 2-3 sentences:",
   "validation": {
      "type": "condition.required",
      "hint": "Write the description in the box"
    }
  }
  ```
  {% endcut %}
  
- [condition.required](../reference/condition.required.md): Checks if the text field is filled in.

  {% cut "Show code" %}

  ```json
  {
    "validation": {
      "type": "condition.required",
      "hint": "Write the description in the box"
    }
  }
  ```
  {% endcut %}

- [plugin.toloka](../reference/plugin.toloka.md): Customizes the task width.

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

If this template doesn't meet your needs, see other examples in the **Text** section.

## Set the desired text length {#text-length}

To set the desired text length, use the [condition.schema](../reference/condition.schema.md) component instead of [condition.required](../reference/condition.required.md). It won't let a Toloker submit a response if the text they entered is longer or shorter than specified.

{% cut "Show code" %}

 ```json
 {
    "type": "condition.schema",
    "schema": {
      "type": "string",
      "minLength": 50,
      "maxLength": 200
    },
    "hint": "Please make sure your description contains 50 to 200 characters"
 }
 ```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/vq9w3lrp47NtE7.)

## Use short single-line text field {#short-text-field}

For short single-line text, use the [field.text](../reference/field.text.md) component instead of [field.textarea](../reference/field.textarea.md).

{% cut "Show code" %}

 ```json
 {
   "type": "field.text",
   "data": {
     "type": "data.output",
     "path": "result"
    },
    "label": "Describe the product in 2-3 sentences:",
    "validation": {
      "type": "condition.required",
      "hint": "Write the description in the box"
    }
 }
 ```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/lFvWtPU63zeh7g)

## Add a description {#add-description}

To add a detailed description to the task, use the `label` property of the [view.image](../reference/view.image.md) component.

{% cut "Show code" %}

```json
{
  "type": "view.text",
  "content": "Look at the product photo and write a brief description about it."
}

```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/F-uKaF6v47LVBm)

## Add a layout {#add-layout}

To enhance Toloker's experience, you can highlight different types of data with colors using [view.alert](../reference/view.alert.md). 

You can place it in the [view.list](../reference/view.list.md) along with the other components.

In this example, the description is highlighted with a blue border.

{% cut "Show code" %}

```json
{
  "type": "view.alert",
  "theme": "info",
  "content": {
    "type": "view.text",
    "content": "Look at the product photo and write a brief description about it."
  }
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/U4g9kJuh3zfJy9)

## Remove an image {#remove-image}

For tasks where images or columns are not required, use a simplified example without them.

{% cut "Show code" %}

```json
{
  "view": {
    "type": "view.list",
    "items": [
      {
        "type": "view.text",
        "label": "Text for translation",
        "content": {
          "type": "data.input",
          "path": "text"
        }
      },
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
  },
  "plugins": [
    {
      "type": "plugin.toloka",
      "layout": {
        "kind": "scroll",
        "taskWidth": 600
      }
    }
  ]
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/9-sO-Ei747iRsq)

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
      "validation": {
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
      "validation": {
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
      "validation": {
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

## Check the link click {#link-click}

Add a button that opens the search results and generate a search query link using the [helper.search-query](../reference/helper.search-query.md) component. To make sure that a Toloker clicked on the link and checked its contents, configure validation, as in the example.

{% cut "Show code" %}

 ```json
 {
   "type": "helper.search-query",
   "engine": "google",
   "query": {
      "type": "data.input",
      "path": "link"
    }
 }
 ```
 
{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/0iYQZxMX47ibsS)

## Allow a Toloker adding input fields {#dynamic-field-add}

This is a complex example that consists of four main parts.

{% cut "Components used in the example" %}

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

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/RMHTYfPs47MxYV)

{% include [contact-support](../_includes/contact-support.md) %}