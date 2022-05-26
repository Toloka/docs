# field.radio-group

A component for selecting one value out of several options. It is designed as a group of circles arranged vertically.

If you want it to look like normal buttons, use [field.button-radio-group](field.button-radio-group.md).

The minimum number of buttons is one. Any type of data can be returned.

## Component properties {#properties}

| Name                                                | Type                | Description                                                                                                                                  |
| --------------------------------------------------- | ------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span>            | "field.radio-group" | <p>Set component type</p>                                                                                                                    |
| `data`<span style="color: red">\*</span>            | _writable_          | <p>Data with values that will be processed or changed.</p>                                                                                   |
| `label`                                             | _string_            | <p>Label above the component.</p>                                                                                                            |
| `disabled`                                          | _boolean_           | <p>This property prevents clicking the button. If the value is `true`, the button is not active (the user will not be able to click it).</p> |
| `hint`                                              | _string_            | <p>Hint text.</p>                                                                                                                            |
| `options`<span style="color: red">\*</span>         | _array_             | <p>An array of buttons.</p>                                                                                                                  |
| `options[]`                                         | _object_            | <p>A button.</p>                                                                                                                             |
| `options[].hint`                                    | _string_            | <p>Text with additional information.</p>                                                                                                     |
| `options[].label`<span style="color: red">\*</span> | _string_            | <p>The title of the option.</p>                                                                                                              |
| `options[].value`<span style="color: red">\*</span> | _any_               | <p>Returned value.</p>                                                                                                                       |
| `validation`                                        | _condition_         | <p>Validation based on condition.</p>                                                                                                        |
