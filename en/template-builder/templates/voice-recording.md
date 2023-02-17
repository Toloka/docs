# Voice recording

For this type of project, you can use the **Voice Recording** preset.

This preset helps you convert text to speech. Using the Toloka mobile app, Tolokers should tap the button and read the text aloud. If the Toloker uses a desktop application, when he clicks on the button, a window opens to download an audio file. After getting the results, you can listen to the recordings and download them.

Take a look at the example: the labeling interface includes a text and a voice recorder button. Note that the validation and task layout are already configured in this example.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/XgN35IUF3xqvGy)

{% cut "Components used in the example" %}

- [view.list](../reference/view.list.md): Displays data in a list.
- [view.text](../reference/view.text.md): Adds the text you want to convert to speech.

  {% cut "Show code" %}
  
  ```json
  {
    "type": "view.text",
    "content": {
       "type": "data.input",
       "path": "text"
    }
  }
  ```
   
  {% endcut %}
	
- [field.audio](../reference/field.audio.md): Allows to record (or upload) an audio file.

  {% cut "Show code" %}
  
  ```json
  {
    "type": "field.audio",
    "data": {
        "type": "data.output",
        "path": "audio_file"
    },
    "validation": {
        "type": "condition.required"
    }
  }
   ```
  {% endcut %}
  
- [condition.required](../reference/condition.required.md): Сhecks if the audio file is in the response.

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
      "taskWidth": 500
    }
  }
  ```
  
  {% endcut %}
  
{% endcut %}  

If this template doesn't meet your needs, see other examples in the **Audio** section.

## Add a description {#add-description}

To add a detailed description to the task, use the [view.text](../reference/view.text.md) component.

{% cut "Show code" %}

```json
{
  "type": "view.text",
  "content": "Tap the voice recorder button and read the text aloud."
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/a5j6lIKx3zL3nz)

## Add a layout {#add-layout}

To enhance Toloker's experience, you can highlight different types of data with colors using [view.alert](../reference/view.alert.md). You can place it in the [view.list](../reference/view.list.md) along with the other components.

In this example, the text is highlighted with a blue border.

{% cut "Show code" %}

```json
  {
    "type": "view.alert",
    "theme": "info",
    "content": {
       "type": "view.text",
       "content": {
         "type": "data.input",
         "path": "text"
        }  
    }
  }
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/3bZ9nXUi3zLAZC)

## Add a condition {#add-a-condition}

The [helper.if](../reference/helper.if.md) component displays an interface element after a specific response is selected.

{% cut "Show code" %}

```json
{
  "type": "helper.if",
  "condition": {
    "type": "condition.equals",
    "data": {
      "type": "data.output",
      "path": "answer"
    },
    "to": "no"
  },
  "then": {
    "type": "field.text",
    "label": "Why you couldn't upload the file?",
    "data": {
      "type": "data.output",
      "path": "comment"
    }
  }
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/z0gt6KeE3zLPEK)
