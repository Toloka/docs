# layout.bars

A component that adds top and bottom bars to the content.

You can use other components inside each part of this component, such as images, text, or options.

The top bar is located at the top edge of the component, and the bottom one is at the bottom edge. The content is placed between the bars and takes up all available space.

[![View example](../_images/buttons/view-example.svg)](https://ya.cc/t/QzAxy9hY44Wxcf)

{% cut "Components used in the example" %}

- [view.list](view.list.md): Displays data in a list.
- [view.text](view.text.md): Adds a block with text.
- [view.image](view.image.md): Adds a image.
- [field.radio-group](field.radio-group.md): Adds radio buttons for selecting an answer option.
- [data.output](../operations/work-with-data.md): The output data. This is what you get when a Toloker clicks the **Submit** button.
- [condition.required](condition.required.md): Checks if at least one option is selected.

{% endcut %}

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "layout.bars" | Set component type ||
|| `barAfter` | _view_ | The bar displayed at the bottom edge of the component. ||
|| `barBefore` | _view_ | The bar displayed at the top edge of the component. ||
|| `content`<span style="color: red">\*</span> | _view_ | The main content. ||
|| `validation` | _condition_ | Validation based on condition. ||
|#

{% include [contact-support](../_includes/contact-support.md) %}
