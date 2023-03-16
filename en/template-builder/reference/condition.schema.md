# condition.schema

Allows validating data using [JSON Schema](https://json-schema.org/learn/getting-started-step-by-step.html). This is a special format for describing data in JSON format.

For example, you can describe the data type, the minimum and maximum values, and specify that all values must be unique.

This component is useful in the following cases:

- If [available components](index.md) don't provide everything you need to configure validation.
- If you already have a prepared JSON Schema configuration for the check and you want to use it.

[![View example](../_images/buttons/view-example.svg)](https://ya.cc/t/CRZHc49y3xNssY)

{% cut "Components used in the example" %}

- [view.list](view.list.md): Displays data in a list.
- [view.labeled-list](view.labeled-list.md): Displays components as a list with labels placed on the left.
- [view.text](view.text.md): Displays a text.
- [view.link](view.link.md): Displays a link.
- [field.button-radio-group](field.button-radio-group.md): Adds buttons for selecting an answer option. 
- [field.text](field.text.md): Adds a field for entering a short text. 
- [view.iframe](view.iframe.md): Displays the web page at the URL in an iframe window.

{% endcut %}

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "condition.schema" | Set component type. ||
|| `data` | _any_ | Data that should be checked. ||
|| `hint` | _string_ | Validation error message that a Toloker will see. ||
|| `schema` | _JSON Schema draft 7_ | The schema for validating data. ||
|| `schema.maxLength` | _integer_ | Maximum number of symbols. ||
|| `schema.minLength` | _integer_ | Minimum number of symbols. ||
|| `schema.pattern` | _string_ | A pattern in the form of a regular expression. ||
|| `schema.type` | _string_ | One of the data types:
- `string`
- `integer`
- `object`
- `array`
- `boolean`
- `null`
||
|#

{% include [contact-support](../_includes/contact-support.md) %}
