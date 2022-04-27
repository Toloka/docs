# field.email

Creates a field for entering an email address.

Checks that the text contains the `@` character. You can [set other conditions yourself](../best-practices/conditions.dita).

[View example in the sandbox](https://clck.ru/SUXxq).

## Component properties {#properties}

| Name                                     | Type                                                                                   | Description                                                      |
| ---------------------------------------- | -------------------------------------------------------------------------------------- | ---------------------------------------------------------------- |
| `type`<span style="color: red">\*</span> | "field.email"                                                                          | <p>Set component type</p>                                        |
| `data`<span style="color: red">\*</span> | <a class="xref popup-link" href="../concepts/types.dita#types/writable">writable</a>   | <p>Data with values that will be processed or changed.</p>       |
| `label`                                  | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Label above the component.</p>                                |
| `hint`                                   | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Hint text.</p>                                                |
| `placeholder`                            | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>A semi-transparent label that is shown in an empty field.</p> |
| `validation`                             | <a class="xref popup-link" href="../concepts/types.dita#types/condition">condition</a> | <p>Validation based on condition.</p>                            |
