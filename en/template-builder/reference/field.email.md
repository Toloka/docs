# field.email

Creates a field for entering an email address.

Checks that the text contains the `@` character. You can [set other conditions yourself](../best-practices/conditions.dita).

[View example in the sandbox](https://clck.ru/SUXxq).

## Component properties {#properties}

| Name                                     | Type          | Description                                                      |
| ---------------------------------------- | ------------- | ---------------------------------------------------------------- |
| `type`<span style="color: red">\*</span> | "field.email" | <p>Set component type</p>                                        |
| `data`<span style="color: red">\*</span> | _writable_    | <p>Data with values that will be processed or changed.</p>       |
| `label`                                  | _string_      | <p>Label above the component.</p>                                |
| `hint`                                   | _string_      | <p>Hint text.</p>                                                |
| `placeholder`                            | _string_      | <p>A semi-transparent label that is shown in an empty field.</p> |
| `validation`                             | _condition_   | <p>Validation based on condition.</p>                            |
