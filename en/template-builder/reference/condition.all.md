# condition.all

Checks that **all** child conditions are met. If any of the conditions is not met, the component returns 'false'.

[View example in the sandbox](https://clck.ru/asRyC).

If you only need one out of several conditions to be met, use the [condition.any](condition.any.md) component. You can also combine these components.

## Component properties {#properties}

| Name                                     | Type                                                                                   | Description                                            |
| ---------------------------------------- | -------------------------------------------------------------------------------------- | ------------------------------------------------------ |
| `type`<span style="color: red">\*</span> | "condition.all"                                                                        | <p>Set component type</p>                              |
| `conditions`                             | <a class="xref popup-link" href="../concepts/types.dita#types/array">array</a>         | <p>A set of conditions that must be met.</p>           |
| `conditions[]`                           | <a class="xref popup-link" href="../concepts/types.dita#types/condition">condition</a> | <p>Required condition.</p>                             |
| `hint`                                   | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Validation error message that the user will see</p> |
