# condition.sub-array

Checks that the array in `data` is a subarray for `parent`.

[View example in the sandbox](https://clck.ru/asSD9).

## Component properties {#properties}

| Name                                     | Type                                                                             | Description                                            |
| ---------------------------------------- | -------------------------------------------------------------------------------- | ------------------------------------------------------ |
| `type`<span style="color: red">\*</span> | "condition.sub-array"                                                            | <p>Set component type</p>                              |
| `data`                                   | <a class="xref popup-link" href="../concepts/types.dita#types/any">any</a>       | <p>Subarray that is checked for in `parent`</p>        |
| `hint`                                   | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a> | <p>Validation error message that the user will see</p> |
| `parent`                                 | <a class="xref popup-link" href="../concepts/types.dita#types/any">any</a>       | <p>The array where `data` is searched for</p>          |
