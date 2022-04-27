# condition.schema

Allows validating data using [JSON Schema](https://json-schema.org/learn/getting-started-step-by-step.html). This is a special format for describing data in JSON format.

For example, you can describe the data type, the minimum and maximum values, and specify that all values must be unique.

This component is useful in the following cases:

- If [available components](index.md) don't provide everything you need to configure validation.
- If you already have a prepared JSON Schema configuration for the check and you want to use it.

## Component properties {#properties}

| Name                                     | Type                                                                                                                    | Description                                            |
| ---------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------ |
| `type`<span style="color: red">\*</span> | "condition.schema"                                                                                                      | <p>Set component type</p>                              |
| `data`                                   | <a class="xref popup-link" href="../concepts/types.dita#types/any">any</a>                                              | <p>Data that should be checked.</p>                    |
| `hint`                                   | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>                                        | <p>Validation error message that the user will see</p> |
| `schema`                                 | <a class="xref popup-link" href=https://json-schema.org/learn/getting-started-step-by-step.html>JSON Schema draft 7</a> | <p>The schema for validating data.</p>                 |
