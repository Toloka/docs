# field.radio-group

A component for selecting one value out of several options. It is designed as a group of circles arranged vertically.

If you want it to look like normal buttons, use [field.button-radio-group](field.button-radio-group.md).

The minimum number of buttons is one. Any type of data can be returned.

## Component properties {#properties}

| Name                                                | Type                                                                                   | Description                                                                                                                                  |
| --------------------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span>            | "field.radio-group"                                                                    | <p>Set component type</p>                                                                                                                    |
| `data`<span style="color: red">\*</span>            | <a class="xref popup-link" href="../concepts/types.dita#types/writable">writable</a>   | <p>Data with values that will be processed or changed.</p>                                                                                   |
| `label`                                             | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Label above the component.</p>                                                                                                            |
| `disabled`                                          | <a class="xref popup-link" href="../concepts/types.dita#types/boolean">boolean</a>     | <p>This property prevents clicking the button. If the value is `true`, the button is not active (the user will not be able to click it).</p> |
| `hint`                                              | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Hint text.</p>                                                                                                                            |
| `options`<span style="color: red">\*</span>         | <a class="xref popup-link" href="../concepts/types.dita#types/array">array</a>         | <p>An array of buttons.</p>                                                                                                                  |
| `options[]`                                         | <a class="xref popup-link" href="../concepts/types.dita#types/object">object</a>       | <p>A button.</p>                                                                                                                             |
| `options[].hint`                                    | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Text with additional information.</p>                                                                                                     |
| `options[].label`<span style="color: red">\*</span> | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>The title of the option.</p>                                                                                                              |
| `options[].value`<span style="color: red">\*</span> | <a class="xref popup-link" href="../concepts/types.dita#types/any">any</a>             | <p>Returned value.</p>                                                                                                                       |
| `validation`                                        | <a class="xref popup-link" href="../concepts/types.dita#types/condition">condition</a> | <p>Validation based on condition.</p>                                                                                                        |
