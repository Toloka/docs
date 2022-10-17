# Image comparison (Side-by-side)

For this type of project, you can use the **Image comparison (Side-by-side)** preset.

Take a look at the example: there are two images and buttons to choose an answer. Note that validation, keyboard shortcuts, and task layout are already configured in this example.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/tDog1HS73TUM4B)

{% cut "Components used in the example" %}

- [view.image](../reference/view.image.md): Image.

  {% cut "Show code" %}

  ```json
  {
    "type": "view.image",
    "url": "https://tlk.s3.yandex.net/dataset/toloka_logos/b2b_dandelion_icon.png"
  }
  ```

  {% endcut %}

- [layout.side-by-side](../reference/layout.side-by-side.md): Arranges images side by side.

  {% cut "Show code" %}

  ```json
  {
    "type": "layout.side-by-side",
    "items": [],
    "controls": {
      "type": "view.list",
      "items": []
    }
  }
  ```

  {% endcut %}

- [field.radio-group](../reference/field.radio-group.md): Buttons for answer options.

  {% cut "Show code" %}

  ```json
  {
    "type": "field.radio-group",
    "label": "Which icon do you like more?",
    "options": [],
    "data": {
      "type": "data.output",
      "path": "result"
    },
    "validation": {
      "type": "condition.required"
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
      "payload": "LEFT"
    },
    "2": {
      "type": "action.set",
      "data": {
        "type": "data.output",
        "path": "result"
      },
      "payload": "RIGHT"
    },
    "3": {
      "type": "action.set",
      "data": {
        "type": "data.output",
        "path": "result"
      },
      "payload": "404"
    },
    "type": "plugin.hotkeys"
  }
  ```

  {% endcut %}

{% endcut %}

{% include [toloka-tb-source-add-media](../_includes/toloka-tb-source/id-toloka-tb-source/add-media.md) %}

## What else can be configured {#add-more}

- To add a detailed description to the task, use the [view.text](../reference/view.text.md) component.

  {% cut "Show code" %}

  ```json
  {
    "type": "view.text",
    "content": "Look at the pictures and choose the one you like more."
  }
  ```

  {% endcut %}

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/EosbIOF23TUN3V)

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

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/IP_OifxG3TUbMm)

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
      "content": "Look at the pictures and choose the one you like more."
    }
  },
  {
    "type": "layout.side-by-side",
    "items": [],
    "controls": {
      "type": "view.alert",
      "theme": "warning",
      "content": {
        "type": "field.radio-group",
        "label": "Which icon do you like more?",
        "options": [],
        "data": {
          "type": "data.output",
          "path": "result"
        },
        "validation": {
          "type": "condition.required"
        }
      }
    }
  }
  ```

  {% endcut %}

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/jHaQHSZk3TUZcW)

#### See also {#see-also}

- [Tutorials — image comparison (side-by-side)](https://toloka.ai/docs/guide/tutorials/side-by-side.html)

{% include [contact-support](../_includes/contact-support.md) %}