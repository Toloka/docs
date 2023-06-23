# Image classification

For this type of project, you can use the **Image classification** preset. Note that validation, keyboard shortcuts, and task layout are already configured in this example.

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/EmabzTqA3ttFVs)

{% cut "Components used in the example" %}

- [view.image](../reference/view.image.md): Image.

- [field.button-radio-group](../reference/field.button-radio-group.md): Buttons for answer options.

  The [condition.required](../reference/condition.required.md) component inside the `validation` property checks if at least one option is selected.

  {% cut "Show code" %}

  ```json
  {
    "type": "field.button-radio-group",
    "label": "What is the cat's mood?",
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
    "content": "Look at the picture and evaluate its visual quality."
  }
  ```

  {% endcut %}

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/VfAHjs2V3ttFWX)

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

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/iMo8AGit3ttFWz)

- Add keyboard shortcuts to rotate and zoom in images in the [plugin.hotkeys](../reference/plugin.hotkeys.md) configuration.

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
    "l": {
      "type": "action.rotate",
      "view": {
        "$ref": "view.items.0"
      },
      "payload": "left"
    },
    "r": {
      "type": "action.rotate",
      "view": {
        "$ref": "view.items.0"
      },
      "payload": "right"
    },
    "q": {
      "type": "action.open-close",
      "view": {
        "$ref": "view.items.0"
      }
    },
    "type": "plugin.hotkeys"
  }
  ```
  
  {% endcut %}

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/gLh9ufLx3ttFXM)

If this preset doesn't meet your needs, see other examples in this section.

## Other options for buttons {#mult-ans-options}

Decide whether a Toloker can select only one or multiple answer options:

{% list tabs %}

- Multiple options (checkboxes)

  If there are several possible answers to the question, use [field.checkbox-group](../reference/field.checkbox-group.md) checkboxes.

  {% cut "Show code" %}

  ```json
  {
    "type": "field.checkbox-group",
    "label": "What do you see in the picture?",
    "options": [
      {
        "label": "Crosswalk",
        "value": "line"
      },
      {
        "label": "Cars",
        "value": "cars"
      },
      {
        "label": "Pedestrians",
        "value": "walkers"
          },
      {
        "label": "Parking",
        "value": "parking"
      },
      {
        "label": "Road signs",
        "value": "road-signs"
      }
    ],
    "validation": {
      "type": "condition.required",
      "hint": "select at least one answer"
    },
    "data": {
      "type": "data.output",
      "path": "result"
    }
  }
  ```
  
  {% endcut %} 

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/KUpCR4gj3ttFY7)

- One option (a radio button)

  The [field.button-radio-group](../reference/field.button-radio-group.md) component is displayed as solid buttons. It's better to use these buttons if the question has 2–4 short answer options.

  If there are more answer options, or they are long, it's better to use [field.radio-group](../reference/field.radio-group.md), as in the example.


  {% cut "Show code" %}

  ```json
  {
    "type": "field.radio-group",
    "label": "What do you see in the picture?",
    "options": [
      {
        "label": "Nevsky Masquerade cat",
        "value": "ref1"
      },
      {
        "label": "Australian Mist cat",
        "value": "ref2"
      },
      {
        "label": "Russian Blue cat",
        "value": "ref3"
      },
      {
        "label": "A different breed of cat",
        "value": "other"
      },
      {
        "label": "Picture didn't load",
        "value": "error"
      }
    ],
    "validation": {
      "type": "condition.required",
      "hint": "select at least one answer"
    },
    "data": {
      "type": "data.output",
      "path": "result"
    }
  }
  ```
  
  {% endcut %} 

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/BQPuzqRh3ttFYX)

{% endlist %}

## Add conditions {#dependencies}

The [helper.if](../reference/helper.if.md) component displays an interface element after a specific response is selected. For example, it lets a Toloker select correct statements about an image only if the image is loaded.

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
    "type": "field.checkbox-group",
    "label": "2. What's in the picture?",
    "options": [
      {
        "label": "Crosswalk",
        "value": "line"
      },
      {
        "label": "Cars",
        "value": "cars"
      },
      {
        "label": "Pedestrians",
        "value": "walkers"
      },
      {
        "label": "Parking",
        "value": "parking"
      },
      {
        "label": "Road signs",
        "value": "road-signs"
      }
    ],
    "data": {
      "type": "data.output",
      "path": "input_data"
    },
    "validation": {
      "type": "condition.required"
    }
  }
}
```
  
{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/RbqyYj2-3ttFYz)

## Image and search query comparison {#search}

### Does the image match the search query

Add a button that opens the search results and generate a search query link using the [helper.search-query](../reference/helper.search-query.md) component. To make sure that a Toloker clicked on the link and checked its contents, configure validation, as in the example.

{% cut "Show code" %}

```json
{
  "type": "view.action-button",
  "label": "Link to the cat breed search",
  "action": {
    "type": "action.open-link",
    "payload": {
      "type": "helper.search-query",
      "engine": "yandex/images",
      "query": {
        "type": "data.input",
        "path": "link"
      }
    }
  },
  "validation": {
    "type": "condition.link-opened",
    "url": {
      "type": "helper.search-query",
      "query": {
        "type": "data.input",
        "path": "link"
      },
      "engine": "yandex/images"
    }
  }
}
```
  
{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/h9tN8XX73ttFZm)

### Side-by-side image and web page comparison

You can display the web page in the built-in window using the [view.iframe](../reference/view.iframe.md) component. Place the image next to it using [layout.side-by-side](../reference/layout.side-by-side.md).

{% cut "Show code" %}

```json
{
  "type": "layout.side-by-side",
  "items": [
    {
      "type": "view.image",
      "url": {
        "type": "data.input",
        "path": "image"
      }
    },
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
  ],
  "controls": {
    "type": "field.button-radio-group",
    "label": "Can the picture (A) be shown in the search results for this query (B)?",
    "options": [
      {
        "label": "Yes",
        "value": "yes"
      },
      {
        "label": "No",
        "value": "no"
      },
      {
        "label": "Loading error",
        "value": "error"
      }
    ],
    "data": {
      "type": "data.output",
      "path": "result"
    },
    "validation": {
      "type": "condition.required",
      "hint": "select an option"
    }
  }
}
```
  
{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/vHtHEcj_3vvrRM)

### Side-by-side image and mobile web page comparison

This is a more complex example that compares the image with the results of a search query. The following components are added:

- [view.iframe](../reference/view.iframe.md): Displays the web page in an embedded window.
- [view.device-frame](../reference/view.device-frame.md): Wraps the window in a smartphone frame.
- [layout.side-by-side](../reference/layout.side-by-side.md): Places the image and the search results window next to each other.

{% cut "Show code" %}

```json
{
  "type": "layout.side-by-side",
  "items": [
    {
      "type": "view.image",
      "url": {
        "type": "data.input",
        "path": "image"
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
  ],
  "controls": {
    "type": "field.button-radio-group",
    "label": "Can the picture (A) be shown in the search results for this query (B)?",
    "options": [
      {
        "label": "Yes",
        "value": "yes"
      },
      {
        "label": "No",
        "value": "no"
      },
      {
        "label": "Loading error",
        "value": "error"
      }
    ],
    "data": {
      "type": "data.output",
      "path": "result"
    },
    "validation": {
      "type": "condition.required",
      "hint": "select an option"
    }
  }
}
```
  
{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/a9bzsPXh3vvrwH)

## See also {#see-also}

- [Tutorials — image classification](../../guide/tutorials/image-classification.md)

{% include [contact-support](../_includes/contact-support.md) %}