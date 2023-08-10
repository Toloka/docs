# field.radio-group

A component for selecting one value out of several options. It is designed as a group of circles arranged vertically.

If you want it to look like normal buttons, use [field.button-radio-group](field.button-radio-group.md).

The minimum number of buttons is one. Any type of data can be returned.

[![View example](../_images/buttons/view-example.svg)](https://ya.cc/t/Pu5X4ilz4P33SS)

{% cut "Components used in the example" %}

- [data.output](../operations/work-with-data.md): The output data. This is what you get when a Toloker clicks the **Submit** button.
- [condition.required](condition.required.md): Checks that the data is filled in.

{% endcut %}

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "field.radio-group" | Set component type. ||
|| `data`<span style="color: red">\*</span> | _writable_ | {% include [toloka-tb-source-data-with-values](../_includes/toloka-tb-source/id-toloka-tb-source/data-with-values.md) %} ||
|| `label` | _string_ | Label above the component. ||
|| `disabled` | _boolean_ | This property prevents clicking the button. If the value is `true`, the button is not active (a Toloker will not be able to click it). ||
|| `hint` | _string_ | Hint text. ||
|| `options`<span style="color: red">\*</span> | _array_ | An array of buttons. ||
|| `options[]` | _object_ | A button. ||
|| `options[].hint` | _string_ | Text with additional information. ||
|| `options[].label`<span style="color: red">\*</span> | _string_ | The title of the option. ||
|| `options[].value`<span style="color: red">\*</span> | _any_ | Returned value. ||
|| `validation` | _condition_ | Validation based on condition. ||
|#

{% include [contact-support](../_includes/contact-support.md) %}
