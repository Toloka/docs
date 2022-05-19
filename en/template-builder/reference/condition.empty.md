# condition.empty

Checks that the data didn't get a value. If it did, returns `false`. This is useful if you need to check the optional template data (`data.*`) or make sure that the user didn't interact with the data entry fields (`fields.*`).

[View example in the sandbox](https://clck.ru/asRzy).

## Component properties {#properties}

| Name                                     | Type                                                                             | Description                                                                                               |
| ---------------------------------------- | -------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span> | "condition.empty"                                                                | <p>Set component type</p>                                                                                 |
| `data`                                   | <a class="xref popup-link" href="../concepts/types.dita#types/any">any</a>       | <p>Data to check. If not specified, data is checked in the component that contains `condition.empty`.</p> |
| `hint`                                   | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a> | <p>Validation error message that the user will see</p>                                                    |
