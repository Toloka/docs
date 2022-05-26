# condition.not

Returns the inverse of the specified condition. For example, if the specified condition is met (returns `true`), then
`condition.not` will return `false`.

[View example in the sandbox](https://clck.ru/asS6S).

## Component properties {#properties}

| Name                                     | Type            | Description                                             |
| ---------------------------------------- | --------------- | ------------------------------------------------------- |
| `type`<span style="color: red">\*</span> | "condition.not" | <p>Set component type</p>                               |
| `condition`                              | _condition_     | <p>The condition for which the inverse is returned.</p> |
| `hint`                                   | _string_        | <p>Validation error message that the user will see</p>  |
