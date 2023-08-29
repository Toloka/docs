# Audio classification

For this type of project, you can use the **Audio classification** preset. Note that validation, keyboard shortcuts, and task layout are already configured in this example.

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/cqAV0dK_4RD4T4)

{% cut "Components used in the example" %}

- [view.list](../reference/view.list.md): Displays data in a list.

- [view.image](../reference/view.image.md): Adds an audio player.

  The [condition.played-fully](../reference/condition.played-fully.md) component inside the `validation` property checks for the end of playback.

  {% cut "Show code" %}

  ```json
  {
    "type": "view.audio",
    "url": {
      "type": "data.input",
      "path": "audio"
    },
    "validation": {
      "type": "condition.played-fully",
      "hint": "Listen to the audio recording to the end"
    }
  }
  ```
  {% endcut %}

- [field.button-radio-group](../reference/field.button-radio-group.md): Adds buttons for selecting an answer option.

  {% cut "Show code" %}

  ```json
  {
    "type": "field.button-radio-group",
    "label": "How clear is the speech in this recording?",
    "data": {
      "type": "data.output",
      "path": "result"
    },
    "options": [
      {
        "label": "Clear",
        "value": "clear"
      },
      {
        "label": "Not clear",
        "value": "not_clear"
      },
      {
        "label": "No speech",
        "value": "no_speech"
      },
      {
        "label": "Audio isn't playing",
        "value": "error"
      }
    ],
    "validation": {
      "type": "condition.required",
      "hint": "Answer the question"
    }
  }
  ```

  {% endcut %}

- [condition.required](../reference/condition.required.md): Checks if at least one option is selected.

  {% cut "Show code" %}

  ```json
  {
    "type": "condition.required",
    "hint": "Answer the question"
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
      "taskWidth": 500
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
      "payload": "clear"
    },
    "2": {
      "type": "action.set",
      "data": {
        "type": "data.output",
        "path": "result"
      },
      "payload": "not_clear"
    },
    "3": {
      "type": "action.set",
      "data": {
        "type": "data.output",
        "path": "result"
      },
      "payload": "no_speech"
    },
    "4": {
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

## Add a description {#add-description}

To add a detailed description to the task, use the `label` property of the [view.audio](../reference/view.audio.md) component.

{% cut "Show code" %}

```json
{
  "type": "view.audio",
  "label": "Listen to the audio recording and answer the question.",
  "url": {
    "type": "data.input",
    "path": "audio"
  },
  "validation": {
    "type": "condition.played-fully",
    "hint": "Listen to the audio recording to the end"
  }
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/44Uh7Dnv4RD4cX)

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
          "content": "Listen to the audio recording and answer the question."
        }
      },
      {
        "type": "view.alert",
        "theme": "warning",
        "content": {
        "type": "field.button-radio-group",
        "label": "How clear is the speech in this recording?",
        "data": {
          "type": "data.output",
          "path": "result"
        },
        "options": [
          {
            "label": "Clear",
            "value": "clear"
          },
          {
            "label": "Not clear",
            "value": "not_clear"
          },
          {
            "label": "No speech",
            "value": "no_speech"
          },
          {
            "label": "Audio isn't playing",
            "value": "error"
          }
        ],
        "validation": {
          "type": "condition.required",
          "hint": "Answer the question"
        }
      }
      }
  ```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/rHcaXdHQ4RD4b5)

## Add a response field {#add-text-area}

To let Tolokers leave comments about the task or their response, add a text field using [field.textarea](../reference/field.textarea.md).

{% cut "Show code" %}

```json
{
  "type": "field.textarea",
  "label": "Leave a comment:",
  "placeholder": "Enter text",
  "data": {
    "type": "data.output",
    "path": "comment"
  }
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/xgwllwj04RD4iE)

## Add conditions {#dependencies}

The [helper.if](../reference/helper.if.md) component displays an interface element after a specific response is selected. For example, it lets a Toloker select correct statements about an audio only if the audio is loaded.

{% cut "Show code" %}

```json
{
  "type": "helper.if",
  "condition": {
    "type": "condition.equals",
    "data": {
      "type": "data.output",
      "path": "first-q"
    },
    "to": "yes"
  },
  "then": {
    "type": "field.button-radio-group",
    "label": "How clear is the speech in this recording?",
    "data": {
      "type": "data.output",
      "path": "result"
    },
    "options": [
      {
        "label": "Clear",
        "value": "clear"
      },
      {
        "label": "Not clear",
        "value": "not_clear"
      },
      {
        "label": "No speech",
        "value": "no_speech"
      },
      {
        "label": "Audio isn't playing",
        "value": "error"
      }
    ],
    "validation": {
      "type": "condition.required",
      "hint": "Answer the question"
    }
  }
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/_XbZPWwx4RD4mA)

## Audio and text comparison {#text}

  You can add text from input data to audio classification tasks. For example, this is useful if an audio recording was recognized automatically, and now you need Tolokers to correct errors in the text. To do this, use the [view.text](../reference/view.text.md) component and refer to the number of the element in the input data array in the `content` property.

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/OwTrclyz4GQEri)

{% include [contact-support](../_includes/contact-support.md) %}