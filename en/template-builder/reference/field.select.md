# field.select

Button for selecting from a drop-down list. Use this component when the list is long and only one option can be chosen.

For short lists (2–4 items), it's better to use [field.radio-group](field.radio-group.md) or [field.button-radio-group](field.button-radio-group.md), where all the options are visible at once.

To allow selecting multiple options, use the [field.checkbox-group](field.checkbox-group.md) component.

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "field.select" | Set component type. ||
|| `data`<span style="color: red">\*</span> | _writable_ | Data with values that will be processed or changed. ||
|| `label` | _string_ | Label above the component. ||
|| `hint` | _string_ | Hint text. ||
|| `options`<span style="color: red">\*</span> | _array_ | Options to choose from. ||
|| `options[]` | _object_ | Option parameters. ||
|| `options[].label`<span style="color: red">\*</span> | _string_ | The name of the option to display in the list. ||
|| `options[].value`<span style="color: red">\*</span> | _any_ | The value to write to the data in the `data` property. ||
|| `placeholder` | _string_ | The text that will be displayed if none of the options is selected. ||
|| `validation` | _condition_ | Validation based on condition. ||
|#

{% include [contact-support](../_includes/contact-support.md) %}
