# condition.any

Checks that **at least one** of the child conditions is met. If none of the conditions is met, the component returns `false`.

[View example in the sandbox](https://clck.ru/SEYdx).

If you need all conditions to be met, use the [condition.all](condition.all.md) component. You can also combine these components.

## Component properties {#properties}

| Name                                     | Type            | Description                                                    |
| ---------------------------------------- | --------------- | -------------------------------------------------------------- |
| `type`<span style="color: red">\*</span> | "condition.any" | <p>Set component type</p>                                      |
| `conditions`                             | _array_         | <p>A set of conditions, at least one of which must be met.</p> |
| `conditions[]`                           | _condition_     | <p>Condition.</p>                                              |
| `hint`                                   | _string_        | <p>Validation error message that the user will see</p>         |
