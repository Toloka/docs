# Side-by-side text comparison

For this type of project, you can use the preset **Comparison of products**.

This preset allows you to compare two names and determine whether they belong to different products or the same.

Take a look at the example: there are two texts and buttons to choose an answer. Note that validation, keyboard shortcuts, and task layout are already configured in this example.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/Sf4lo2yk3TaD9n)

{% cut "Components used in the example" %}

- [view.text](../reference/view.text.md): The texts that you want to compare.

  {% cut "Show code" %}

  ```json
  {
    "type": "view.text",
    "content": {
      "type": "data.input",
      "path": "text_1"
    }
  }
  ```

  {% endcut %}

- [layout.columns](../reference/layout.columns.md): Arranges texts side by side.

  {% cut "Show code" %}

  ```json
  {
    "type": "layout.columns",
    "items": []
  }
  ```

  {% endcut %}

- [field.radio-group](../reference/field.radio-group.md): Buttons for answer options.

  {% cut "Show code" %}

  ```json
  {
    "type": "field.radio-group",
    "label": "Are the product names the same or different?",
    "options": [],
    "validation": {
      "type": "condition.required"
    },
    "data": {
      "type": "data.output",
      "path": "result"
    }
  }
  ```

  {% endcut %}

- [condition.required](../reference/condition.required.md): Checks if at least one option is selected.

  {% cut "Show code" %}

  ```json
  {
    "type": "condition.required"
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
      "taskWidth": 800
    }
  }
  ```

  {% endcut %}

- [plugin.hotkeys](../reference/plugin.hotkeys.md): [Keyboard shortcuts](../best-practices/hotkeys.md).

  {% cut "Show code" %}

  ```json
  {
    "1": {
      "type": "action.set",
      "data": {
        "type": "data.output",
        "path": "result"
      },
      "payload": "equal"
    },
    "2": {
      "type": "action.set",
      "data": {
        "type": "data.output",
        "path": "result"
      },
      "payload": "different"
    },
    "type": "plugin.hotkeys"
  }
  ```

  {% endcut %}

{% endcut %}

## What else can be configured {#add-more}

- To add a detailed description to the task, use the [view.text](../reference/view.text.md) component.

  {% cut "Show code" %}

  ```json
  {
    "type": "view.text",
    "content": "Look at the texts and tell if they are the same or different."
  }
  ```

  {% endcut %}

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/pm2SGLdb3TaFW6)

- To let Tolokers leave comments about the task or their response, add a text field using [field.textarea](../reference/field.textarea.md).

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

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/PDf1QLoJ3TaHDy)

If this preset doesn't meet your needs, see other examples in this section.

## Add a layout {#add-color}

To enhance Toloker's experience, you can highlight different types of data with colors using [view.alert](../reference/view.alert.md). In this example, the source text is highlighted with a blue border, and the buttons are highlighted with a yellow one.

  {% cut "Show code" %}

  ```json
  {
    "type": "view.alert",
    "theme": "info",
    "content": {
      "type": "view.text",
      "content": "Look at the texts and tell if they are the same or different."
    }
  },
  {
    "type": "view.alert",
    "theme": "warning",
    "content": {
      "type": "field.radio-group",
      "label": "Are the product names the same or different?",
      "options": [],
      "validation": {
        "type": "condition.required"
      },
      "data": {
        "type": "data.output",
        "path": "result"
      }
    }
  }
  ```

  {% endcut %}

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/XKSNJHhg3TaGY3)

{% include [contact-support](../_includes/contact-support.md) %}