# condition.required

Checks that the data is filled in. This way you can get the user to answer all the required questions.

If used inside the `validation` property, you can omit the `data` property and the same property will be used from the parent component [field](fields.md) (the one that contains the `condition.required` component).

[View example in the sandbox](https://clck.ru/asSBw).

## Component properties {#properties}

| Name                                     | Type                                                                             | Description                                                                                                                                           |
| ---------------------------------------- | -------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span> | "condition.required"                                                             | <p>Set component type</p>                                                                                                                             |
| `data`                                   | <a class="xref popup-link" href="../concepts/types.dita#types/any">any</a>       | <p>Data to be filled in. If the property is not specified, the data of the parent component (the one that contains `condition.required`) is used.</p> |
| `hint`                                   | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a> | <p>Validation error message that the user will see</p>                                                                                                |
