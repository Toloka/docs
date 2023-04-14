# view.divider

Horizontal delimiter.

You can place extra elements in the center of the delimiter, like a popup `hint` and `label`.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/yWUusmRj48ZRya)

{% cut "Components used in the example" %}

- [view.list](view.list.md): Displays data in a list.
- [view.image](view.image.md): Displays an image.
- [view.text](view.text.md): Displays a text.
- [field.button-radio-group](field.button-radio-group.md): Adds buttons for selecting an answer option.
- [condition.required](condition.required.md): Checks that the data is filled in.

{% endcut %}

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "view.divider" | Set component type. ||
|| `label` | _string_ | A label in the center of the delimiter. Line breaks are not supported. ||
|| `hint` | _string_ | Hint text. ||
|| `validation` | _condition_ | Validation based on condition. ||
|#

{% include [contact-support](../_includes/contact-support.md) %}
