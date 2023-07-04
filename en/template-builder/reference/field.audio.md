# field.audio

Component for recording audio. Works in the [Toloka app for mobile devices](https://toloka.ai/tolokers/docs/mobile/?lang=en). In a browser, this component opens a window for uploading an audio file.

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/W77mHJnc3tyyrm)

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "field.audio" | Set component type. ||
|| `data`<span style="color: red">\*</span> | _writable_ | {% include [toloka-tb-source-data-with-values](../_includes/toloka-tb-source/id-toloka-tb-source/data-with-values.md) %} ||
|| `label` | _string_ | Label above the component. ||
|| `hint` | _string_ | Hint text. ||
|| `multiple` | _boolean_ | Determines whether multiple audio files can be recorded (or uploaded):

- `false` (default) — forbidden.
- `true` — allowed. ||
  || `validation` | _condition_ | Validation based on condition. ||
  |#

{% include [contact-support](../_includes/contact-support.md) %}
