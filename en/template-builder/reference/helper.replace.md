# helper.replace

Allows you to replace some parts of the string with others.

This helper function returns a string in which all occurrences of 'find`in`data`are replaced with`replace`.

Because the `helper.replace` helper returns a string, it can be used in properties that accept string values.

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "helper.replace" | Set component type ||
|| `data`<span style="color: red">\*</span> | _any_ | Data to perform the replacement on.
||
|| `find`<span style="color: red">\*</span> | _string_ | The value to search for — the string whose occurrences must be found in `data` and replaced with the string from `replace`. ||
|| `replace`<span style="color: red">\*</span> | _string_ | The value to insert in place of the matches of the `find` value. ||
|#

{% include [contact-support](../_includes/contact-support.md) %}
