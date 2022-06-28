# Side-by-side audio comparison

Take a look at the example: there are two audio tracks and buttons to choose an answer. Note that validation, keyboard shortcuts, and task layout are already configured in this example.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/8yWU6Tq-3TYPx8)

{% cut "Components used in the example" %}

- [view.audio](../reference/view.audio.md): An audio player.

  {% cut "Show code" %}

  ```json
  {
    "type": "view.audio",
    "url": {
      "type": "data.input",
      "path": "url_1"
    },
    "label": "Audio 1",
      "validation": {
      "type": "condition.played",
      "hint": "Listen to the audio recording"
    }
  }
  ```

  {% endcut %}

- [layout.columns](../reference/layout.columns.md): Arranges audio tracks side by side.

  {% cut "Show code" %}

  ```json
  {
    "type": "layout.columns",
    "items": []
  }
  ```

  {% endcut %}

- [condition.played](../reference/condition.played.md): Checks if a Toloker has started listening to the audio.

  {% cut "Show code" %}

  ```json
  {
    "type": "condition.played",
    "hint": "Listen to the audio recording"
  }
  ```

  {% endcut %}

- [field.button-radio-group](../reference/field.button-radio-group.md): Buttons for answer options.

  {% cut "Show code" %}

  ```json
  {
    "type": "field.button-radio-group",
    "label": "Whose voice sounds more natural?",
    "options": [],
    "validation": {
      "type": "condition.required",
      "hint": "Choose an answer."
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
    "hint": "Choose an answer."
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
      "payload": "audio_1"
    },
    "2": {
      "type": "action.set",
      "data": {
        "type": "data.output",
        "path": "result"
      },
      "payload": "audio_2"
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

- To [check](../best-practices/conditions.md) whether a Toloker listened to the whole audio, replace the [condition.played](../reference/condition.played.md) component with [condition.played-fully](../reference/condition.played-fully.md).

  {% cut "Show code" %}

  ```json
  {
    "type": "condition.played-fully",
    "hint": "Listen to the audio recording"
  }
  ```

  {% endcut %}

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/Op9Pu3r_3TYSNY)

- To put a short audio track on repeat, change the properties of the [view.audio](../reference/view.audio.md) component by adding `loop: true`.

  {% cut "Show code" %}

  ```json
  {
    "type": "view.audio",
    "url": {
      "type": "data.input",
      "path": "url_1"
    },
    "label": "Audio 1",
    "loop": true,
    "validation": {
      "type": "condition.played",
      "hint": "Listen to the audio recording"
    }
  }
  ```

  {% endcut %}

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/cHq9Xtli3TYTic)

- Add [shortcuts](../best-practices/hotkeys.md) for playing and pausing audio tracks using the [plugin.hotkeys](../reference/plugin.hotkeys.md) plugin.

  {% cut "Show code" %}

  ```json
  {
    "q": {
      "type": "action.play-pause",
      "view": {
        "$ref": "view.items.0.items.0"
      }
    },
    "w": {
      "type": "action.play-pause",
      "view": {
        "$ref": "view.items.0.items.1"
      }
    },
    "type": "plugin.hotkeys"
  }
  ```

  {% endcut %}

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/cQixkxxh3TYX5u)

If this template doesn't meet your needs, see other examples in this section.

## Add a response field {#add-text-area}

If you need comments from the Toloker, add a text field using [field.textarea](../reference/field.textarea.md). In this example, additional validation is set up that requires you to enter text if one of two audio tracks is selected.

{% cut "Show code" %}

  ```json
  {
    "type": "field.textarea",
    "label": "Please explain why you chose it.",
    "data": {
      "type": "data.output",
      "path": "text"
    },
    "validation": {
      "type": "condition.required",
      "hint": "Enter text."
    }
  }
  ```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/aBZZXCvm3TYZCw)

## Arrange audio tracks vertically {#top-bottom}

Audio tracks can be arranged in a single column, top to bottom. This interface is better suited for comparing more than two audio recordings.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/eqx3jrHj3TYaTy)

## Add a source text {#add-original-text}

You can add a field with a source text using the [view.text](../reference/view.text.md) component. For example, this might be useful if you want to find out which of the audio recordings best matches the description.

{% cut "Show code" %}

  ```json
  {
    "type": "view.text",
    "content": "A joyful, inspiring melody.",
    "label": "Overview"
  }
  ```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/m1b1YPvB3TYbYi)

## Add a layout {#add-color}

To enhance Toloker's experience, you can highlight different types of data with colors using [view.alert](../reference/view.alert.md). In this example, the source text is highlighted with a blue border, and the buttons are highlighted with a yellow one.

{% cut "Show code" %}

  ```json
  {
    "type": "view.alert",
    "theme": "info",
    "content": {
      "type": "view.text",
      "content": "A joyful, inspiring melody."
    }
  },
  {
    "type": "view.alert",
    "theme": "warning",
    "content": {
      "type": "field.button-radio-group",
      "label": "Which audio recording best fits the description?",
      "options": [],
      "validation": {
        "type": "condition.required",
        "hint": "Choose an answer."
      },
      "data": {
        "type": "data.output",
        "path": "result"
      }
    }
  }
  ```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/PinrwG2E3TYcTx)

[![image](../_images/buttons/contact-support.svg)](../concepts/support.md)