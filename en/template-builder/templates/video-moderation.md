# Video classification

For this type of project, you can use the **Hand gesture classification** preset.

This preset helps you match video content to pre-defined categories. For example, you can use it for moderation of content, evaluation of video for noise and defects, or labeling videos to train computer vision.

Take a look at the example: the labeling interface includes a video player, and several buttons for categories. Note that validation, keyboard shortcuts, and task layout are already configured in this Template Builder sample code.

[![image](../_images/buttons/view-example.svg)](https://clck.ru/TJ73B)

{% cut "Components used in the example" %}

- [view.list](../reference/view.list.md): Displays data in a list.

- [view.video](../reference/view.video.md): Adds a video player.

  Use the [condition.played](../reference/condition.played.md) component inside the `validation` property to check that a Toloker started watching the video.

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

- [field.button-radio-group](../reference/field.button-radio-group.md): Adds a group of buttons for answer options.

  Use the [condition.required](../reference/condition.required.md) component inside the `validation` property to check if at least one option is selected.

  {% cut "Show code" %}

  ```json
  {
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
  ```

  {% endcut %}

- [plugin.hotkeys](../reference/plugin.hotkeys.md): : Adds [keyboard shortcuts](../best-practices/hotkeys.md).

  {% cut "Show code" %}

  ```json
  {
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
    },
    "3": {
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

  Add a group of checkboxes using the [field.checkbox-group](../reference/field.checkbox-group.md) component.

  [![](../_images/buttons/view-example.svg)](https://clck.ru/UC6Zo)

- One option (a radio button)

  The [field.button-radio-group](../reference/field.button-radio-group.md) component is displayed as solid buttons. It's better to use these buttons if the question has 2–4 short answer options.

  If there are more answer options, or they are long, it's better to use [field.radio-group](../reference/field.radio-group.md), as in the example.

  [![](../_images/buttons/view-example.svg)](https://clck.ru/UC6bm)

{% endlist %}

## Add clarifying questions to one of the options {#add-addition}

The [helper.switch](../reference/helper.switch.md) component displays an interface element after a specific response is selected. In this example, a Toloker can only select correct statements about the video if it is loaded.

[![](../_images/buttons/view-example.svg)](https://clck.ru/UC6tt)

If this preset doesn't meet your needs, see other examples in this section.

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

[![](../_images/buttons/view-example.svg)](https://clck.ru/UC6rN)

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

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/OO5Uvqrh3q8hbm)

<!--
## Compare the video with search results {#compare-results}

You can display a web page in an embedded window using the [view.iframe](../reference/view.iframe.md) component. Place the video next to it using [layout.side-by-side](../reference/layout.side-by-side.md).

In the example, the video is compared to the search results generated by the [helper.search-query](../reference/helper.search-query.md) component.

[![](../_images/buttons/view-example.svg)](https://clck.ru/UC6rN)

-->

## Compare the video with another type of data {#compare-video-and-other}

Add an image using the [view.image](../reference/view.image.md) component. Place the video next to the image using the [layout.columns](../reference/layout.columns.md) component.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/_jTfyAQN3q8yg9)

Place the video next to the text or audio using the [view.list](../reference/view.list.md) component.

{% list tabs %}

- Compare the video with text

  Add the [view.text](../reference/view.text.md) component.

  [![](../_images/buttons/view-example.svg)](https://clck.ru/UC6jd)

- Compare audio tracks

  Add the [view.audio](../reference/view.audio.md) component.

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/rsKpf6_C3q9MoH)

{% endlist %}


## See also {#see-also}

- [Tutorials — video classification](../../guide/tutorials/video-moderation.md)

{% include [contact-support](../_includes/contact-support.md) %}