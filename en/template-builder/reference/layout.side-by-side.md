# layout.side-by-side

The component displays several data blocks of the same width on a single horizontal panel. For example, you can use this to compare several photos.

You can add selection buttons or a field for comment under the compared elements.

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/buBN71oL3twVaP)

{% cut "Components used in the example" %}

- [action.set](action.set.md): Sets the value from `payload` in the data in the `data` property.
- [plugin.hotkeys](plugin.hotkeys.md): Sets keyboard shortcuts for actions.
- [layout.side-by-side](layout.side-by-side.md): Displays several data blocks of the same width on a single horizontal panel.
- [view.image](view.image.md): Adds an image.
- [view.list](view.list.md): Displays data in a list.
- [field.radio-group](field.radio-group.md): Adds a group of radio buttons for selecting an answer option.
- [field.textarea](field.textarea.md): Adds a text block to enter milti-line text.
- [condition.required](condition.required.md): Checks that the data is filled in.

{% endcut %}

Differences from the [layout.compare](layout.compare.md) component:

- You can add buttons which allow hiding the elements. Use it if you need to compare, for example, 5 photos at once and need to choose between two.
- You can configure only common control elements. You can't add separate buttons under each of the compared element.

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "layout.side-by-side" | Set component type ||
|| `controls`<span style="color: red">\*</span> | _view_ | Components that let Tolokers perform the required actions.

For example: [field.checkbox-group](field.checkbox-group.md) or [field.button-radio-group](field.button-radio-group.md). ||
|| `items`<span style="color: red">\*</span> | _array_ | An array of data blocks. ||
|| `items[]` | _view_ | A component for data output or input. For example, [view.image](view.image.md). ||
|| `minItemWidth` | _number_ | The minimum width of a data block, at least 400 pixels. ||
|| `validation` | _condition_ | Validation based on condition. ||
|#

{% include [contact-support](../_includes/contact-support.md) %}
