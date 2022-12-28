# Video classification

For this type of project, you can use the **Hand gesture classification** preset.

This preset helps you match video content to pre-defined categories. For example, you can use it for moderation of content, evaluation of video for noise and defects, or labeling videos to train computer vision.

Take a look at the example: the labeling interface includes a video player, and several buttons for categories. Note that validation, keyboard shortcuts, and task layout are already configured in this Template Builder sample code.

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/ziSYuQ3E3sTWn9)

{% cut "Components used in the example" %}

- [view.list](../reference/view.list.md): Displays data in a list.

- [view.video](../reference/view.video.md): Adds a video player.

  The [condition.played](../reference/condition.played.md) inside the component inside the `validation` property checks that a Toloker started watching the video.

  {% cut "Show code" %}

  ```json
  {
    "type": "view.video",
    "validation": {
      "type": "condition.played",
      "hint": "you need to start the video player"
    },
    "url": {
      "type": "data.input",
      "path": "video"
    }
  }
  ```

  {% endcut %}

- [field.button-radio-group](../reference/field.button-radio-group.md): Adds a group of buttons for answer options.

  The [condition.required](../reference/condition.required.md) component inside the `validation` property checks if at least one option is selected.

  {% cut "Show code" %}

  ```json
  {
    "type": "field.button-radio-group",
    "label": "What number is being shown?",
    "options": [
      {
        "label": "One",
        "value": "one"
      },
      {
        "label": "Two",
        "value": "two"
      },
      {
        "label": "Three",
        "value": "three"
      },
      {
        "label": "Four",
        "value": "four"
      },
      {
        "label": "Five",
        "value": "five"
      },
      {
        "label": "Failed to load",
        "value": "error"
      }
    ],
    "validation": {
      "type": "condition.required",
      "hint": "choose one of the options"
    },
    "data": {
      "type": "data.output",
      "path": "result"
    }
  }
  ```

  {% endcut %}

- [plugin.hotkeys](../reference/plugin.hotkeys.md): Adds [keyboard shortcuts](../best-practices/hotkeys.md).

  {% cut "Show code" %}

  ```json
  {
    "1": {
      "type": "action.set",
      "data": {
        "type": "data.output",
        "path": "result"
      },
      "payload": "one"
    },
    "2": {
      "type": "action.set",
      "data": {
        "type": "data.output",
        "path": "result"
      },
      "payload": "two"
    },
    "3": {
      "type": "action.set",
      "data": {
        "type": "data.output",
        "path": "result"
      },
      "payload": "three"
    },
    "4": {
      "type": "action.set",
      "data": {
        "type": "data.output",
        "path": "result"
      },
      "payload": "four"
    },
    "5": {
      "type": "action.set",
      "data": {
        "type": "data.output",
        "path": "result"
      },
      "payload": "five"
    },
    "6": {
      "type": "action.set",
      "data": {
        "type": "data.output",
        "path": "result"
      },
      "payload": "error"
    },
    "q": {
      "type": "action.play-pause",
      "view": {
        "$ref": "view.items.0"
      }
    },
    "type": "plugin.hotkeys"
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

{% endcut %}

{% include [toloka-tb-source-add-media](../_includes/toloka-tb-source/id-toloka-tb-source/add-media.md) %}

If this preset doesn't meet your needs, see other examples in this section.

## Check that the video is fully viewed

If you want to be sure that a Toloker watched the whole video, replace the [condition.played](../reference/condition.played.md) component with [condition.played-fully](../reference/condition.played-fully.md).

{% cut "Show code" %}

  ```json
  {
    "type": "view.video",
    "validation": {
      "type": "condition.played-fully",
      "hint": "you need to watch the video to the end"
    },
    "url": {
      "type": "data.input",
      "path": "video"
    }
  }
  ```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/yMGS4ccN3sFD2K)

## Add a description {#add-description}

To add a detailed description to the task, use the [view.text](../reference/view.text.md) component.

{% cut "Show code" %}

```json
{
  "type": "view.text",
  "content": "Watch the video and rate its quality."
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/BUdRCS7f3pqbt4)

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

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/BYXaQbhF3q77RW)

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
      "content": "Watch the video and rate its quality."
    }
  },
  {
    "type": "view.alert",
    "theme": "warning",
    "content":{
      "type": "field.button-radio-group",
      "label": "rate the video quality",
      "options": [
        {
          "label": "Good",
          "value": "ok"
        },
        {
          "label": "Bad",
          "value": "bad"
        },
        {
          "label": "Failed to load",
          "value": "error"
        }
      ],
      "validation": {
      "type": "condition.required",
      "hint": "choose one of the options"
      },
      "data": {
        "type": "data.output",
        "path": "result"
      }
    }
  }
  ```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/4Rd2odCR3q7Agd)

## Other options for buttons {#add-variants}

Decide whether a Toloker can select only one or multiple answer options.

{% list tabs %}

- Multiple options (checkboxes)

  If there are several possible answers to the question, use the [field.checkbox-group](../reference/field.checkbox-group.md) component.

  {% cut "Show code" %}

  ```json
  {
    "type": "field.checkbox-group",
    "label": "Rate the video quality:",
    "options": [
      {
        "label": "The video is in color",
        "value": "1"
      },
      {
        "label": "The video is in focus",
        "value": "2"
      }
    ],
    "validation": {
      "type": "condition.required",
      "hint": "Select one or more options"
    },
    "data": {
      "type": "data.output",
      "path": ""
    }
  }
  ```

  {% endcut %}

  [![](../_images/buttons/view-example.svg)](https://clck.ru/UC6Zo)

- One option (a radio button)

  The [field.button-radio-group](../reference/field.button-radio-group.md) component is displayed as solid buttons. It's better to use these buttons if the question has 2–4 short answer options.

  If there are more answer options, or they are long, it's better to use [field.radio-group](../reference/field.radio-group.md), as in the example.

  {% cut "Show code" %}

  ```json
  {
    "type": "field.radio-group",
    "label": "What's in the video?",
    "options": [
      {
        "label": "The video shows a blue rotating planet",
        "value": "1"
      },
      {
        "label": "The video shows a blue planet isn't rotating",
        "value": "2"
      }
    ],
    "validation": {
      "type": "condition.required",
      "hint": "Select an answer"
    },
    "data": {
      "type": "data.output",
      "path": "result1"
    }
  },
  {
    "type": "field.radio-group",
    "label": "Video quality",
    "options": [
      {
        "label": "The video looks like real footage",
        "value": "1"
      },
      {
        "label": "The video was made using computer graphics",
        "value": "2"
      }
    ],
    "validation": {
      "type": "condition.required",
      "hint": "Select an answer"
    },
    "data": {
      "type": "data.output",
      "path": "result2"
   }
  }
  ```

  {% endcut %}

  [![](../_images/buttons/view-example.svg)](https://clck.ru/UC6bm)

{% endlist %}

## Add clarifying questions to one of the options {#add-addition}

The [helper.if](../reference/helper.if.md) component displays an interface element after a specific response is selected. In this example, a Toloker can only select correct statements about the video if it is loaded.

  {% cut "Show code" %}

```json
  {
    "type": "helper.if",
    "condition": {
      "type": "condition.equals",
      "data": {
        "type": "data.output",
        "path": "result"
      },
      "to": "yes"
    },
    "then": {
      "type": "field.checkbox-group",
      "label": "What's in this video?",
      "options": [
        {
          "label": "Planet Earth",
          "value": "earth"
        },
        {
          "label": "A planet rotating",
          "value": "turn"
        },
        {
          "label": "A blue planet",
          "value": "blue"
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
  }
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/t9VAVeRE3sDafV)

If you need more options, use the [helper.switch](../reference/helper.switch.md) component.

## Video and search query comparison {#search}

#### Does the video match the search query

Add a button that opens the search results and generate a search query link using the [helper.search-query](../reference/helper.search-query.md) component. To make sure that a Toloker clicked on the link and checked its contents, configure validation, as in the example.

{% cut "Show code" %}

```json
{
  "type": "condition.link-opened",
  "hint": "Follow the link",
  "url": {
    "type": "helper.search-query",
    "query": {
      "type": "data.input",
      "path": "link"
    },
    "engine": "bing"
  }
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/AaB2KYVc3q8jH3)

#### Side-by-side video and web page comparison

You can display the web page in the built-in window using the [view.iframe](../reference/view.iframe.md) component. Place the video next to it using [layout.side-by-side](../reference/layout.side-by-side.md).

{% cut "Show code" %}

```json
{
  "type": "view.iframe",
  "maxWidth": 400,
  "fullHeight": true,
  "url": {
    "type": "helper.search-query",
    "query": {
      "type": "data.input",
      "path": "link"
    },
    "engine": "bing"
  }
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/k1vG4h_-3sDepD)

#### Side-by-side video and mobile web page comparison

This is a more complex example that compares the video with the results of a search query. The following components are added:

- [view.iframe](../reference/view.iframe.md): Displays the web page in an embedded window.
- [view.device-frame](../reference/view.device-frame.md): Wraps the window in a smartphone frame.
- [layout.side-by-side](../reference/layout.side-by-side.md): Places the video and the search results window next to each other.

{% cut "Show code" %}

```json
{
  "type": "layout.side-by-side",
  "items": [
    {
      "type": "view.video",
      "content": {
        "type": "data.input",
        "path": "video"
      }
    },
    {
      "type": "view.device-frame",
      "maxWidth": 400,
      "content": {
        "type": "view.iframe",
        "maxWidth": 400,
        "fullHeight": true,
        "url": {
          "type": "helper.search-query",
          "query": {
            "type": "data.input",
            "path": "link"
          },
          "engine": "bing"
        }
      }
    }
  ]
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/9kzoSoqY3sDfid)

## Compare the video with another type of data {#compare-video-and-other}

- Add an image using the [view.image](../reference/view.image.md) component. Place the video next to the image using the [layout.columns](../reference/layout.columns.md) component.

  {% cut "Show code" %}

  ```json
    {
      "type": "layout.columns",
      "items": [
        {
          "type": "view.video",
          "url": {
            "type": "data.input",
            "path": "video"
          }
        },
        {
          "type": "view.image",
          "url": {
            "type": "data.input",
            "path": "image"
          }
        }
      ]
    }
  ```

  {% endcut %}

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/_jTfyAQN3q8yg9)

- Place the video next to the text or audio using the [view.list](../reference/view.list.md) component.

  {% list tabs %}

  - Compare the video with text

    Add the [view.text](../reference/view.text.md) component.

    {% cut "Show code" %}

    ```json
      {
        "type": "view.text",
        "label": "Video description:",
        "content": "The video shows the Earth rotating."
      }
    ```

    {% endcut %}


    [![](../_images/buttons/view-example.svg)](https://clck.ru/UC6jd)

  - Compare audio tracks

    Add the [view.audio](../reference/view.audio.md) component.

    {% cut "Show code" %}

    ```json
      {
        "type": "view.audio",
        "label": "Audio:",
        "url": "https://yastat.net/s3/tb/static/file-examples/audio/medium.mp3",
        "validation": {
          "type": "condition.played"
        }
      }
    ```

    {% endcut %}

    [![](../_images/buttons/view-example.svg)](https://ya.cc/t/rsKpf6_C3q9MoH)

  {% endlist %}


## See also {#see-also}

- [Tutorials — video classification](../../guide/tutorials/video-moderation.md)

{% include [contact-support](../_includes/contact-support.md) %}