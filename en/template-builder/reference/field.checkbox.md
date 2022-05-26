# field.checkbox

A checkbox.

If you need to add a group of checkboxes, use [field.checkbox-group](field.checkbox-group.md).

[View example in the sandbox](https://clck.ru/asSNc).

## Component properties {#properties}

| Name                                     | Type             | Description                                                                                                                                                                                                                                |
| ---------------------------------------- | ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `type`<span style="color: red">\*</span> | "field.checkbox" | <p>Set component type</p>                                                                                                                                                                                                                  |
| `data`<span style="color: red">\*</span> | _writable_       | <p>Data with values that will be processed or changed.</p>                                                                                                                                                                                 |
| `label`                                  | _string_         | <p>Label above the component.</p>                                                                                                                                                                                                          |
| `disabled`                               | _boolean_        | <p>Property that disables the component. If `true`, the component will not be unavailable.</p>                                                                                                                                             |
| `hint`                                   | _string_         | <p>Hint text.</p>                                                                                                                                                                                                                          |
| `preserveFalse`                          | _boolean_        | <p>Property that specifies whether to return `false` values in the results. By default, if the component returns `false`, this result will not be added to the output. To add `false` to the results, specify `"preserveFalse": true`.</p> |
| `validation`                             | _condition_      | <p>Validation based on condition.</p>                                                                                                                                                                                                      |
