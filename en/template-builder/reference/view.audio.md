# view.audio

The component plays audio.

Format support depends on the Toloker's browser, OS, and device. We recommend using MP3.

[![View example](../_images/buttons/view-example.svg)](https://ya.cc/t/d0D-SzfG46oojL)

{% cut "Components used in the example" %}

- [view.list](view.list.md): Displays data in a list.
- [data.input](../operations/work-with-data.md): The input data. For example, a link to an audio recording that Toloker will listen to.
- [data.output](../operations/work-with-data.md): The output data. This is what you get when a Toloker clicks the **Submit** button.
- [condition.played-fully](condition.played.md): Checks if a Toloker listened to the entire audio track.
- [field.button-radio-group](field.button-radio-group.md): Adds a group of buttons for selecting an answer option.
- [condition.required](condition.required.md): Checks if at least one option is selected.

{% endcut %}

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "view.audio" | Set component type. ||
|| `label` | _string_ | Label above the component. ||
|| `hint` | _string_ | Hint text. ||
|| `loop` | _boolean_ | Automatically replay audio. ||
|| `url`<span style="color: red">\*</span> | _string_ | Audio link. ||
|| `validation` | _condition_ | Validation based on condition. ||
|#

{% include [contact-support](../_includes/contact-support.md) %}
