# field.phone-number

Creates a field for entering a phone number.

Allows entering numbers, spaces, and the `+`, `( )`, `-` characters. Only numbers and the `+` character at the beginning will remain in the data. For example, if you enter `+7 (012) 345-67-89`, the data gets the `+70123456789` value.

[View example in the sandbox](https://clck.ru/asSY2).

## Component properties {#properties}

| Name                                     | Type                 | Description                                                      |
| ---------------------------------------- | -------------------- | ---------------------------------------------------------------- |
| `type`<span style="color: red">\*</span> | "field.phone-number" | <p>Set component type</p>                                        |
| `data`<span style="color: red">\*</span> | _writable_           | <p>Data with values that will be processed or changed.</p>       |
| `label`                                  | _string_             | <p>Label above the component.</p>                                |
| `hint`                                   | _string_             | <p>Hint text.</p>                                                |
| `placeholder`                            | _string_             | <p>A semi-transparent label that is shown in an empty field.</p> |
| `validation`                             | _condition_          | <p>Validation based on condition.</p>                            |
