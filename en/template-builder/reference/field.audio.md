# field.audio

Component for recording audio. Works in the [Toloka app for mobile devices](https://toloka.ai/tolokers/docs/mobile/?lang=en). In a browser, this component opens a window for uploading an audio file.

[View example in sandbox](https://clck.ru/So3w7).

## Component properties {#properties}

| Name                                     | Type                                                                                   | Description                                                                                                                                             |
| ---------------------------------------- | -------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span> | "field.audio"                                                                          | <p>Set component type</p>                                                                                                                               |
| `data`<span style="color: red">\*</span> | <a class="xref popup-link" href="../concepts/types.dita#types/writable">writable</a>   | <p>Data with values that will be processed or changed.</p>                                                                                              |
| `label`                                  | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Label above the component.</p>                                                                                                                       |
| `hint`                                   | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Hint text.</p>                                                                                                                                       |
| `multiple`                               | <a class="xref popup-link" href="../concepts/types.dita#types/boolean">boolean</a>     | <p>Determines whether multiple audio files can be recorded (or uploaded):</p><ul><li>`false` (default) — forbidden.</li><li>`true` — allowed.</li></ul> |
| `validation`                             | <a class="xref popup-link" href="../concepts/types.dita#types/condition">condition</a> | <p>Validation based on condition.</p>                                                                                                                   |
