# Audio transcription

For this type of project, you can use the **Audio Transcription** template ([view code in the sandbox](https://clck.ru/TqsSX)). It has pre-configured validation, task layout, and shortcuts.

{% cut "Components used in the example" %}

- [view.audio](../reference/view.audio.md): An audio player.
- [condition.played-fully](../reference/condition.played.md): Checks if the user listened to the entire audio track.
- [field.button-radio-group](../reference/field.button-radio-group.md): Buttons for answer options.
- [field.textarea](../reference/field.textarea.md): Text input field.
- [condition.required](../reference/condition.required.md): Checks if the text field is filled in.
- [plugin.toloka](../reference/plugin.toloka.md): Customizes the task layout.
- [plugin.hotkeys](../reference/plugin.hotkeys.md): [Keyboard shortcuts](../best-practices/hotkeys.md).

{% endcut %}


{% include [toloka-tb-source-add-media](../_includes/toloka-tb-source/id-toloka-tb-source/add-media.md) %}

## What else can be configured {#add-more}

- If you want to [check](../best-practices/conditions.md) whether the audio has been started, replace the [condition.played-fully](../reference/condition.played-fully.md) component with [condition.played](../reference/condition.played.md).

  [![](../_images/buttons/view-example.svg)](https://clck.ru/TqsYq)
  
- To put a short audio track on repeat, change the properties of the [view.audio](../reference/view.audio.md) component by adding `loop: true`.

  [![](../_images/buttons/view-example.svg)](https://clck.ru/TqsfS)

If this template doesn't meet your needs, see other examples in this section.


## Other options for buttons {#options}

Choose whether a user can select only one or multiple answer options:

{% list tabs %}

- Multiple options (checkboxes)

  Use the [field.checkbox-group](../reference/field.checkbox-group.md) component.
  
  [![](../_images/buttons/view-example.svg)](https://clck.ru/TqsqW)
  
- One option (a radio button)

  Use the [field.radio-group](../reference/field.radio-group.md) component.

  [![](../_images/buttons/view-example.svg)](https://clck.ru/TqtMb)

{% endlist %}

## Add pre-recognized text {#text}

  You can add text from input data to audio transcription tasks. For example, this is useful if an audio recording was recognized automatically, and now you need performers to correct errors in the text. To do this, use the [view.text](../reference/view.text.md) component and refer to the number of the element in the input data array in the `content` property.
 
  [![](../_images/buttons/view-example.svg)](https://clck.ru/TqtBP)
  
[![image](../_images/buttons/contact-support.svg)](../concepts/support.md)
