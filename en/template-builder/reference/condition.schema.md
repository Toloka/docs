# condition.schema

Allows validating data using [JSON Schema](https://json-schema.org/learn/getting-started-step-by-step.html). This is a special format for describing data in JSON format.

For example, you can describe the data type, the minimum and maximum values, and specify that all values must be unique.

This component is useful in the following cases:

- If [available components](index.md) don't provide everything you need to configure validation.
- If you already have a prepared JSON Schema configuration for the check and you want to use it.

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "condition.schema" | Set component type ||
|| `data` | _any_ | Data that should be checked. ||
|| `hint` | _string_ | Validation error message that an annotator will see ||
|| `schema` | _JSON Schema draft 7_ | The schema for validating data. ||
|#
