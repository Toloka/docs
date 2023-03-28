# view.collapse

Expandable block.

Lets you add hidden content that doesn't need to be shown initially or that takes up a large space.

The block heading is always visible.

If you set the `defaultOpened` property to `true`, the block is expanded immediately, but it can be collapsed.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/gDyH9YSJ45ubZd)

{% cut "Components used in the example" %}

- [view.list](view.list.md): Displays data in a list.
- [view.image](view.image.md): Displays an image.
- [field.button-radio-group](field.button-radio-group.md): Adds a group of buttons for selecting an answer option.
- [condition.required](condition.required.md): Checks that the data is filled in.
- [view.text](view.text.md): Adds a block with text.

{% endcut %}

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "view.collapse" | Set component type. ||
|| `label`<span style="color: red">\*</span> | _string_ | Block heading. ||
|| `content`<span style="color: red">\*</span> | _view_ | Content hidden in the block. ||
|| `defaultOpened` | _boolean_ | If `true`, the block is immediately displayed in expanded form. By default, `false` (the block is collapsed). ||
|| `hint` | _string_ | Hint text. ||
|| `validation` | _condition_ | Validation based on condition. ||
|#

{% include [contact-support](../_includes/contact-support.md) %}
