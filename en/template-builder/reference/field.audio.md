# field.audio

Component for recording audio. Works in the [Toloka app for mobile devices](https://toloka.ai/tolokers/docs/mobile/?lang=en). In a browser, this component opens a window for uploading an audio file.

[View example in sandbox](https://clck.ru/So3w7).

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "field.audio" | Set component type ||
|| `data`<span style="color: red">\*</span> | _writable_ | Data with values that will be processed or changed. ||
|| `label` | _string_ | Label above the component. ||
|| `hint` | _string_ | Hint text. ||
|| `multiple` | _boolean_ | Determines whether multiple audio files can be recorded (or uploaded):

- `false` (default) — forbidden.
- `true` — allowed. ||
  || `validation` | _condition_ | Validation based on condition. ||
  |#
