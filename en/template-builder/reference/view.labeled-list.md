# view.labeled-list

Displaying components as a list with labels placed on the left.

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/UurufJ-t4JLFCP)

{% cut "Components used in the example" %}

- [view.list](view.list.md): Displays data in a list.
- [view.text](view.text.md): Adds a block with text.
- [view.link](view.link.md): Displays a link.
- [field.button-radio-group](field.button-radio-group.md): Adds buttons for selecting an answer option.

{% endcut %}

If you don't need labels, use [view.list](view.list.md).

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "view.labeled-list" | Set component type. ||
|| `label` | _string_ | Label above the component. ||
|| `hint` | _string_ | Hint text. ||
|| `items`<span style="color: red">\*</span> | _array of objects_ | An array of list items. ||
|| `items[]` | _object_ | Parameters of a list item. ||
|| `items[].centerLabel` | _boolean_ | If `true`, a `label` is center-aligned relative to the content of a list item (`content`). Use it if the list consists of large items, such as images or multi-line text.

By default, `false` (the label is aligned to the top of the content block). ||
|| `items[].content`<span style="color: red">\*</span> | _view_ | List item content. ||
|| `items[].hint` | _string_ | A pop-up hint displayed next to a label. ||
|| `items[].label`<span style="color: red">\*</span> | _string_ | A label displayed next to a list item. ||
|| `minWidth` | _number_ | The minimum width of list content. If the component width is less than the specified value, it switches to compact mode. ||
|| `validation` | _condition_ | Validation based on condition. ||
|#

{% include [contact-support](../_includes/contact-support.md) %}
