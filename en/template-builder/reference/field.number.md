# field.number

A component that allows a Toloker to enter a number.

Only numbers and decimal separators can be entered in the field. A Toloker can enter a dot or a comma as a separator, but the dot is always used in the output.

When a Toloker enters a number, the separator automatically changes to the one specified in the regional settings. In some countries, the decimal separator is a comma.

You can also set up validation, for example, disable negative or fractional numbers. [Learn more](../operations/components-for-numbers.md).

[![View example](../_images/buttons/view-example.svg)](https://ya.cc/t/MAT9QmHy4P2WYN)

{% cut "Components used in the example" %}

- [data.output](../operations/work-with-data.md): The output data. This is what you get when a Toloker clicks the **Submit** button.
- [condition.required](condition.required.md): Checks that the data is filled in.

{% endcut %}

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "field.number" | Set component type. ||
|| `data`<span style="color: red">\*</span> | _writable_ | {% include [toloka-tb-source-data-with-values](../_includes/toloka-tb-source/id-toloka-tb-source/data-with-values.md) %} ||
|| `label` | _string_ | Label above the component. ||
|| `hint` | _string_ | Hint text. ||
|| `maximum` | _integer_ | Maximum number that can be entered. ||
|| `minimum` | _integer_ | Minimum number that can be entered. ||
|| `placeholder` | _string_ | A semi-transparent label that is shown in the box when it is empty. ||
|| `validation` | _condition_ | Validation based on condition. ||
|#

{% include [contact-support](../_includes/contact-support.md) %}
