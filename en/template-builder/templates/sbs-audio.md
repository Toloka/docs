# Side-by-side audio comparison

Take a look at the example: there are two audio tracks and buttons to choose an answer. Note that validation, keyboard shortcuts, and task layout are already configured in this example.

[![](../_images/buttons/view-example.svg)](https://clck.ru/Tqtjj)

{% cut "Components used in the example" %}


- [view.audio](../reference/view.audio.md): An audio player.
- [layout.columns](../reference/layout.columns.md): Arranges audio tracks side by side.
- [condition.played](../reference/condition.played.md): Checks if a user has started listening to the audio.
- [field.button-radio-group](../reference/field.button-radio-group.md): Buttons for answer options.
- [condition.required](../reference/condition.required.md): Checks if at least one option is selected.
- [plugin.toloka](../reference/plugin.toloka.md): Customizes the task layout.
- [plugin.hotkeys](../reference/plugin.hotkeys.md): [Keyboard shortcuts](../best-practices/hotkeys.md).

{% endcut %}

{% include [toloka-tb-source-add-media](../_includes/toloka-tb-source/id-toloka-tb-source/add-media.md) %}




## What else can be configured {#add-more}

- To [check](../best-practices/conditions.md) whether the user watched the whole video, replace the [condition.played](../reference/condition.played.md) component with [condition.played-fully](../reference/condition.played-fully.md).

  [![](../_images/buttons/view-example.svg)](https://clck.ru/Tqtpk)
  
- To put a short audio track on repeat, change the properties of the [view.audio](../reference/view.audio.md) component by adding `loop: true`.

  [![](../_images/buttons/view-example.svg)](https://clck.ru/Tqtss)
  
- Add [shortcuts](../best-practices/hotkeys.md) for playing and pausing audio tracks using the [plugin.hotkeys](../reference/plugin.hotkeys.md) plugin.

  [![](../_images/buttons/view-example.svg)](https://clck.ru/U7fjR)
  

If this template doesn't meet your needs, see other examples in this section.


## Add a response field {#add-text-area}

If you need comments from the performer, add a text field using [field.textarea](../reference/field.textarea.md). In this example, additional validation is set up that requires you to enter text if one of two audio tracks is selected.

  [![](../_images/buttons/view-example.svg)](https://clck.ru/Tqtw9)

## Arrange audio tracks vertically {#top-bottom}

Audio tracks can be arranged in a single column, top to bottom. This interface is better suited for comparing more than two audio recordings.

  [![](../_images/buttons/view-example.svg)](https://clck.ru/Tqu2T)

## Add a source text {#add-original-text}

You can add a field with a source text using the [view.text](../reference/view.text.md) component. For example, this might be useful if you want to find out which of the audio recordings best matches the description.

  [![](../_images/buttons/view-example.svg)](https://clck.ru/TquBL)

## Add a layout {#add-color}

To enhance user experience, you can also highlight different types of data with colors using [view.alert](../reference/view.alert.md). In this example, the source text is highlighted with a blue border, and the buttons are highlighted with a yellow one.

  [![](../_images/buttons/view-example.svg)](https://clck.ru/TquFn)

[![image](../_images/buttons/contact-support.svg)](../concepts/support.md)
