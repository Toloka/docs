# Side-by-side video comparison

Take a look at the example: there are two videos and buttons to choose an answer. Note that validation, keyboard shortcuts, and task layout are already configured in this example.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/vSBnRFLf3TXf7r)

{% cut "Components used in the example" %}

- [view.video](../reference/view.video.md): A video player.

  {% cut "Show code" %}

  ```json
  {
    "type": "view.video",
    "validation": {
      "type": "condition.played",
      "hint": "Please, watch the video"
    },
    "url": {
      "type": "data.input",
      "path": "video_1"
    }
  }
  ```

  {% endcut %}

- [layout.columns](../reference/layout.columns.md): Arranges videos side by side.

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
    "label": "Are the videos the same or different?",
    "options": [],
    "validation": {
      "type": "condition.required",
      "hint": "Choose one of the options"
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
    "type": "condition.required",
    "hint": "Choose one of the options"
  }
  ```

  {% endcut %}

- [plugin.toloka](../reference/plugin.toloka.md): Customizes the task layout.

  {% cut "Show code" %}

  ```json
  {
    "type": "plugin.toloka",
    "layout": {
      "kind": "pager",
      "taskWidth": 1200
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
    "3": {
      "type": "action.set",
      "data": {
        "type": "data.output",
        "path": "result"
      },
      "payload": "error"
    },
    "type": "plugin.hotkeys"
  }
  ```

  {% endcut %}

{% endcut %}

{% include [toloka-tb-source-add-media](../_includes/toloka-tb-source/id-toloka-tb-source/add-media.md) %}

## What else can be configured {#add-more}

- To [check](../best-practices/conditions.md) whether a Toloker watched videos up to the end, replace the [condition.played](../reference/condition.played.md) component with [condition.played-fully](../reference/condition.played-fully.md).

  {% cut "Show code" %}

  ```json
  {
    "type": "condition.played-fully",
    "hint": "Please, watch the video"
  }
  ```

  {% endcut %}

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/Agy26p4z3TXfRe)

- To add a detailed description to the task, use the [view.text](../reference/view.text.md) component.

  {% cut "Show code" %}

  ```json
  {
    "type": "view.text",
    "content": "Watch the videos and tell if they are the same."
  }
  ```

  {% endcut %}

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/50mce2VJ3TXtHN)

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

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/X_bdCg0m3TXkwV)

If this template doesn't meet your needs, see other examples in this section.

## Add a layout {#add-color}

To enhance Toloker's experience, you can highlight different types of data with colors using [view.alert](../reference/view.alert.md). In this example, the source text is highlighted with a blue border, and the buttons are highlighted with a yellow one.

  {% cut "Show code" %}

  ```json
  {
    "type": "view.alert",
    "theme": "info",
    "content": {
      "type": "view.text",
      "content": "Watch the videos and tell if they are the same."
    }
  },
  {
    "type": "view.alert",
    "theme": "warning",
    "content": {
      "type": "field.radio-group",
      "label": "Are the videos the same or different?",
      "options": [],
      "validation": {
        "type": "condition.required",
        "hint": "Choose one of the options"
      },
      "data": {
        "type": "data.output",
        "path": "result"
      }
    }
  }
  ```

  {% endcut %}

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/Wpdfy4mY3TXtue)

[![image](../_images/buttons/contact-support.svg)](../concepts/support.md)