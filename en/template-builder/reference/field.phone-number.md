# field.phone-number

Creates a field for entering a phone number.

Allows entering numbers, spaces, and the `+`, `( )`, `-` characters. Only numbers and the `+` character at the beginning will remain in the data. For example, if you enter `+7 (012) 345-67-89`, the data gets the `+70123456789` value.

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/_hp-34Gj3twiJS)

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "field.phone-number" | Set component type. ||
|| `data`<span style="color: red">\*</span> | _writable_ | Data with values that will be processed or changed. ||
|| `label` | _string_ | Label above the component. ||
|| `hint` | _string_ | Hint text. ||
|| `placeholder` | _string_ | A semi-transparent label that is shown in an empty field. ||
|| `validation` | _condition_ | Validation based on condition. ||
|#

{% include [contact-support](../_includes/contact-support.md) %}
