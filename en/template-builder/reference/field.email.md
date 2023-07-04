# field.email

Creates a field for entering an email address.

Checks that the text contains the `@` character. You can [set other conditions yourself](../best-practices/conditions.md).

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/7iqP0isn3y3Uyg)

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "field.email" | Set component type. ||
|| `data`<span style="color: red">\*</span> | _writable_ | {% include [toloka-tb-source-data-with-values](../_includes/toloka-tb-source/id-toloka-tb-source/data-with-values.md) %} ||
|| `label` | _string_ | Label above the component. ||
|| `hint` | _string_ | Hint text. ||
|| `placeholder` | _string_ | A semi-transparent label that is shown in an empty field. ||
|| `validation` | _condition_ | Validation based on condition. ||
|#

{% include [contact-support](../_includes/contact-support.md) %}
