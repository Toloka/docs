# action.set

Sets the value from `payload` in the data in the `data` property.

[Learn more about working with data](../operations/work-with-data.md).

For example, let's say you want to add shortcuts for the [field.radio-group](field.radio-group.md) option. You need the shortcut to perform the same action as the selected option, which is to set the specified value in the data. To set this action, use `action.set`.

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/4YfJWA7y3tz3LC)

As another example, you can use this component to count the number of clicks on an option and write the value in the output data. When the page is refreshed, set the value to 0.

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/IN4-Mm2I3tz3Rt)

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "action.set" | Set component type. ||
|| `data` | _writable_ | {% include [toloka-tb-source-data-with-values](../_includes/toloka-tb-source/id-toloka-tb-source/data-with-values.md) %} ||
|| `payload` | _any_ | The value to write to the data. ||
|#

{% include [contact-support](../_includes/contact-support.md) %}
