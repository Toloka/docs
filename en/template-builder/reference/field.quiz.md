# field.quiz

A quiz component that counts only the first answered values.

Returns a key value object with any type of data as value.

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/e9sFCd3B43vpEm)

{% cut "Components used in the example" %}

- [condition.required](condition.required.md): Checks if at least one option is selected.
- [data.output]: Output data.

{% endcut %}

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "field.quiz" | Set component type ||
|| `data`<span style="color: red">\*</span> | _writable_ | Data with values that will be processed or changed. ||
|| `label` | _string_ | Label above the component. ||
|| `hint` | _string_ | Hint text. ||
|| `instruction` | _string_ | – ||
|| `options`<span style="color: red">\*</span> | _array_ | An array of questions. ||
|| `options[]` | _object_ | – ||
|| `options[].border` | _boolean_ | – ||
|| `options[].disabled` | _boolean_ | – ||
|| `options[].key`<span style="color: red">\*</span> | _string_ | – ||
|| `options[].label` | _string_ | A title of answer. Supports markdown ||
|| `options[].options`<span style="color: red">\*</span> | _array_ | An array of answers. ||
|| `options[].options[]` | _object_ | – ||
|| `options[].options[].correct` | _boolean_ | Is this is correct value? ||
|| `options[].options[].hint` | _string_ | Text that appears when answer checked. Supports markdown ||
|| `options[].options[].label`<span style="color: red">\*</span> | _string_ | Text of answer. Supports markdown ||
|| `options[].options[].value`<span style="color: red">\*</span> | _any_ | Returned value. ||
|| `validation` | _condition_ | Validation based on condition. ||
|#

{% include [contact-support](../_includes/contact-support.md) %}
