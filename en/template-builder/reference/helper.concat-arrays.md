# helper.concat-arrays

Merging multiple arrays into a single array.

For example, let's say you have multiple arrays:

```json
([1, 2, 3], [4, 5, 6], [7, 8, 9])
```

Their elements can be combined into a single array to show simultaneously:

```json
[1, 2, 3, 4, 5, 6, 7, 8, 9]
```

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/5gzayPK_3tz4vn)

{% cut "Components used in the example" %}

- [view.list](view.list.md): Displays data in a list.
- [view.text](view.text.md): Displays a text.

{% endcut %}

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "helper.concat-arrays" | Set component type. ||
|| `items` | _array_ | Arrays to combine. ||
|| `items[]` | _any_ | Array element. ||
|#

{% include [contact-support](../_includes/contact-support.md) %}
