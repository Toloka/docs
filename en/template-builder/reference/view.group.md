# view.group

Groups components visually into framed blocks.

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/jNlr4klD3twZBC)

{% cut "Components used in the example" %}

- [layout.columns](layout.columns.md): Places content in columns.
- [view.list](view.list.md): Displays data in a list.
- [field.radio-group](field.radio-group.md): Adds radio buttons for selecting an answer option.
- [data.output](../operations/work-with-data.md): The output data. This is what you get when a Toloker clicks the **Submit** button.
- [field.checkbox-group](field.checkbox-group.md): Adds a group of checkboxes for selecting independent answer options.
- [view.alert](view.alert.md): Creates a color block to highlight important information.
- [view.text](view.text.md): Displays a text.

{% endcut %}

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "view.group" | Set component type. ||
|| `label` | _string_ | Group heading. ||
|| `content` | _view_ | Content of a group block. ||
|| `hint` | _string_ | Explanation of the group heading. To insert a new line, use `\n`. ||
|| `validation` | _condition_ | Validation based on condition. ||
|#

{% include [contact-support](../_includes/contact-support.md) %}
