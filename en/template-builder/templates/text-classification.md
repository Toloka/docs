# Text classification

For this type of project, you can use the **Clickbait or not?** preset.

This preset helps you classify any kind of text for training classifiers and NLP models.

Take a look at the example: the labeling interface includes a text block, and radio buttons for categories. Note that validation, keyboard shortcuts, and task layout are already configured in this Template Builder sample code.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/GCr6AzRu3Wk6so)

{% cut "Components used in the example" %}

- [view.text](../reference/view.text.md): The text that you want to classify.

  {% cut "Show code" %}

  ```json
  {
    "type": "view.text",
    "label": "Headline",
    "content": {
      "type": "data.input",
      "path": "headline"
    }
  }
  ```

  {% endcut %}

- [field.button-radio-group](../reference/field.button-radio-group.md): Adds buttons for selecting an answer option.

  {% cut "Show code" %}

  ```json
  {
    "type": "field.button-radio-group",
    "validation": {
      "type": "condition.required"
    },
    "label": "Is this headline clickbait?",
    "options": [
      {
        "label": "Clickbait",
        "value": "yes"
      },
      {
        "value": "no",
        "label": "Not clickbait"
      }
    ],
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
    "hint": "Select an option"
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
      "payload": "yes"
    },
    "2": {
      "type": "action.set",
      "data": {
        "type": "data.output",
        "path": "result"
      },
      "payload": "no"
    },
    "type": "plugin.hotkeys"
  }
  ```

  {% endcut %}

{% endcut %}

{% include [toloka-tb-source-add-media](../_includes/toloka-tb-source/id-toloka-tb-source/add-media.md) %}

If this template doesn't meet your needs, see other examples in the **Text** section.

## Add a description {#add-description}

To add a detailed description to the task, use the [view.text](../reference/view.text.md) component.

{% cut "Show code" %}

```json
{
  "type": "view.text",
  "content": "Read the headline and tell if it is clickbait."
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/5GdOsaHz3XFSUH)

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

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/tqcXy_dh3Wk7XR)

## Add a layout {#add-layout}

To enhance Toloker's experience, you can highlight different types of data with colors using [view.alert](../reference/view.alert.md). In this example, the description is highlighted with a blue border, and the buttons are highlighted with a yellow one.

{% cut "Show code" %}

```json
{
  "type": "view.alert",
  "theme": "info",
  "content": {
    "type": "view.text",
    "content": "Look at the text and tell if it is clickbait."
  }
},
{
  "type": "view.text",
  "label": "Headline",
  "content": {
    "type": "data.input",
    "path": "headline"
  }
},
{
  "type": "view.alert",
  "theme": "warning",
  "content": {
    "type": "field.button-radio-group",
    "validation": {
      "type": "condition.required",
      "hint": "Select an option"
    },
    "label": "Is this headline clickbait?",
    "options": [
      {
        "label": "Clickbait",
        "value": "yes"
      },
      {
        "label": "Not clickbait",
        "value": "no"
      }
    ],
    "data": {
      "type": "data.output",
      "path": "result"
    }
  }
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/1d9wVk0A3Wk7hq)

## Other options for buttons {#mult-ans-options}

Decide whether a Toloker can select only one or multiple answer options:

{% list tabs %}

- Multiple options (checkboxes)

  If there are several possible answers to the question, use [field.checkbox-group](../reference/field.checkbox-group.md) checkboxes.

  {% cut "Show code" %}

  ```json
  {
    "type": "field.checkbox-group",
    "label": "This headline is:",
    "options": [
      {
        "label": "Clickbate",
        "value": "clickbate"
      },
      {
        "label": "Too long",
        "value": "long"
      },
      {
        "label": "Gramatically incorrect",
        "value": "bad-grammar"
      },
      {
        "label": "None of this",
        "value": "none"
      }
    ],
    "data": {
      "type": "data.output",
      "path": "input_data"
    },
    "validation": {
      "type": "condition.required",
      "hint": "Select at least one option"
    }
  }
  ```

  {% endcut %}

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/WqUYAVJ_3Wk87q)

- One option (a radio button)

  The [field.button-radio-group](../reference/field.button-radio-group.md) component is displayed as solid buttons. It's better to use these buttons if the question has 2–4 short answer options.

  If there are more answer options, or they are long, it's better to use [field.radio-group](../reference/field.radio-group.md), as in the example.

  {% cut "Show code" %}

  ```json
  {
    "type": "field.radio-group",
    "label": "This headline is:",
    "options": [
      {
        "label": "Clickbate",
        "value": "clickbate"
      },
      {
        "label": "Too long",
        "value": "long"
      },
      {
        "label": "Grammatically incorrect",
        "value": "bad-grammar"
      },
      {
        "label": "None of this",
        "value": "none"
      },
      {
        "label": "The text hasn't loaded",
        "value": "404"
      }
    ],
    "data": {
      "type": "data.output",
      "path": "input_data"
    },
    "validation": {
      "type": "condition.required",
      "hint": "Select an option"
    }
  }
  ```

  {% endcut %}

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/772Lk77T3Wk8bu)

{% endlist %}

## Add conditions {#dependencies}

The [helper.if](../reference/helper.if.md) component displays an interface element after a specific response is selected.

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
    "to": "no"
  },
  "then": {
    "type": "field.checkbox-group",
    "label": "2. Why don't you like it?",
    "options": [
      {
        "label": "It's clickbate",
        "value": "clickbate"
      },
      {
        "label": "It's too long",
        "value": "long"
      },
      {
        "label": "It's grammarly incorrect",
        "value": "bad-grammar"
      },
      {
        "label": "Other",
        "value": "other"
      }
    ],
    "data": {
      "type": "data.output",
      "path": "input_data"
    },
    "validation": {
      "type": "condition.required",
      "hint": "Select an option"
    }
  }
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/FwDPOVZ_3Wk8zy)

## Text and search query comparison {#search}

#### Does the text match the search query

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

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/XjJKrKAq3Wk2gG)

#### Side-by-side text and web page comparison

You can display the web page in the built-in window using the [view.iframe](../reference/view.iframe.md) component. Place the text next to it using [layout.side-by-side](../reference/layout.side-by-side.md).

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

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/IV7KDhXz3Wjv6u)

#### Side-by-side text and mobile web page comparison

This is a more complex example that compares the text with the results of a search query. The following components are added:

- [view.iframe](../reference/view.iframe.md): Displays the web page in an embedded window.
- [view.device-frame](../reference/view.device-frame.md): Wraps the window in a smartphone frame.
- [layout.side-by-side](../reference/layout.side-by-side.md): Places the text and the search results window next to each other.

{% cut "Show code" %}

```json
{
  "type": "layout.side-by-side",
  "items": [
    {
      "type": "view.text",
      "content": {
        "type": "data.input",
        "path": "text"
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

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/09flUkZu3WjxyP)

{% include [contact-support](../_includes/contact-support.md) %}