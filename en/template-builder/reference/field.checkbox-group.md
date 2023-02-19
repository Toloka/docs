# field.checkbox-group

Adds a group of checkboxes for selecting independent answer options. This is useful if there are several options. You can add just one checkbox, but it's easier to use [field.checkbox](field.checkbox.md) for that.

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/AA2nEh_E3twhqK)

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "field.checkbox-group" | Set component type ||
|| `data`<span style="color: red">\*</span> | _writable_ | Data with values that will be processed or changed. ||
|| `label` | _string_ | Label above the component. ||
|| `disabled` | _boolean_ | If `true', the options are inactive. || ||`hint`| _string_ | Hint text. || ||`options`<span style="color: red">\*</span> | _array_ | An array of checkboxes, where`value`is the value to change, and`label`is the text near the checkbox. || ||`options[]`| _object_ | A checkbox. || ||`options[].hint`| _string_ | Text with additional information about the option. || ||`options[].label`<span style="color: red">\*</span> | _string_ | Text next to the option. || ||`options[].value`<span style="color: red">\*</span> | _string_ | Returned value. || ||`preserveFalse`| _boolean_ | Property that specifies whether to return`false`values in the results. By default, if the component returns`false`, this result will not be added to the output. To add`false`to the results, specify`"preserveFalse": true`. || ||`validation` | _condition_ | Validation based on condition. ||
|#

{% include [contact-support](../_includes/contact-support.md) %}
