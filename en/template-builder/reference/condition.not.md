# condition.not

Returns the inverse of the specified condition. For example, if the specified condition is met (returns `true`), then
`condition.not` will return `false`.

[View example in the sandbox](https://clck.ru/asS6S).

## Component properties {#properties}

| Name                                     | Type                                                                                   | Description                                             |
| ---------------------------------------- | -------------------------------------------------------------------------------------- | ------------------------------------------------------- |
| `type`<span style="color: red">\*</span> | "condition.not"                                                                        | <p>Set component type</p>                               |
| `condition`                              | <a class="xref popup-link" href="../concepts/types.dita#types/condition">condition</a> | <p>The condition for which the inverse is returned.</p> |
| `hint`                                   | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Validation error message that the user will see</p>  |
