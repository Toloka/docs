# helper.replace

Allows you to replace some parts of the string with others.

This helper function returns a string in which all occurrences of `find` in `data` are replaced with `replace`.

Because the `helper.replace` helper returns a string, it can be used in properties that accept string values.

[![View example](../_images/buttons/view-example.svg)](https://ya.cc/t/11ypBlCg42Qp6o)

{% cut "Components used in the example" %}

- [view.list](view.list.md): Displays data in a list.
- [view.text](view.text.md): Adds a block with text.

{% endcut %}

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "helper.replace" | Set component type. ||
|| `data`<span style="color: red">\*</span> | _any_ | Data to perform the replacement on. ||
|| `find`<span style="color: red">\*</span> | _string_ | The value to search for — the string whose occurrences must be found in `data` and replaced with the string from `replace`. ||
|| `replace`<span style="color: red">\*</span> | _string_ | The value to insert in place of the matches of the `find` value. ||
|#

{% include [contact-support](../_includes/contact-support.md) %}
