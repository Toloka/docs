# helper.join

The component combines two or more strings into one. You can add a delimiter to separate the strings, such as a space or comma.

[![View example](../_images/buttons/view-example.svg)](https://ya.cc/t/_h--eV2Y3ttBMm)

{% cut "Components used in the example" %}

- [view.text](view.text.md): Displays a text.
- [field.select](field.select.md): Adds a drop-down list.

{% endcut %}

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "helper.join" | Set component type. ||
|| `by` | _any_ | Delimiter for joining strings. You can use any number of characters in the delimiter. ||
|| `items`<span style="color: red">\*</span> | _array_ | Array of strings to join. ||
|| `items[]` | _string_ | String parameters. ||
|#
