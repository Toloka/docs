# Voice recording

For this type of project, you can use the **Voice Recording** preset.

This preset helps you record speech in the Toloka mobile app.

Take a look at an example: the labeling interface includes text and a microphone button. Note that the validation, keyboard shortcuts, and task layout are already configured in this example.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/XgN35IUF3xqvGy)

{% cut "Components used in the example" %}

- [view.list](../reference/view.list.md): Displays data in a list.
- [view.text](../reference/view.text.md): Adds the text you want to record

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
	
- [field.audio](../reference/field.audio.md): Voice recorder.

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
  
- [condition.required](../reference/condition.required.md): Checks that the record is present in the response.

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

If this template doesn't meet your needs, see other examples in the **Audio**.

## Add a description {#add-description}

To add a detailed description to the task, use the [view.text](../reference/view.text.md) component.

{% cut "Show code" %}

```json
{
  "type": "view.text",
  "content": "Read the question and record the audio answer."
}
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/QFldZez23xtqqo)

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
      "content": "Read the question and record the audio answer."
    }
  }
```

{% endcut %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/dMvB7Vl33xtyhW)

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

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/W3ojB79U3xtvqs)

## Add a condition (##add-a-condition)
