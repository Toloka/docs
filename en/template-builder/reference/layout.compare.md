# layout.compare

Use it to arrange interface elements for comparing them. For example, you can compare several photos.

Selection buttons can be placed under each of the compared items. You can also add common elements, such as a field for comments.

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/MwYMw5-q3x7Lrs)

{% cut "Components used in the example" %}

- [view.image](view.image.md): Adds an image.
- [field.radio-group](field.radio-group.md): Adds radio buttons for selecting an answer option.
- [data.output](../operations/work-with-data.md): The output data. This is what you get when a Toloker clicks the **Submit** button.

{% endcut %}

Differences from [layout.side-by-side](layout.side-by-side.md):

- No buttons for hiding items. These are useful if you need to compare 5 photos at once and it's difficult to choose between two of them.
- You can add individual selection buttons for every item being compared.

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "layout.compare" | Set component type. ||
|| `commonControls` | _view_ | The common fields of the component. Add information blocks that are common to all the elements being compared. ||
|| `items`<span style="color: red">\*</span> | _array_ | An array with properties of the elements being compared. Set the appearance of the component blocks. ||
|| `items[]` | _object_ | The compared element. ||
|| `items[].content` | _view_ | The content of the element that's being compared. Add images, audio recordings, videos, links, or other types of data. ||
|| `items[].controls` | _view_ | Configure the input fields to make a Toloker select an item. ||
|| `minWidth` | _number_ | Minimum width of the element in pixels. Default: 400 pixels. ||
|| `validation` | _condition_ | Validation based on condition. ||
|| `wideCommonControls` | _boolean_ | This property increases the common field size of the elements being compared.
It's set to `false` by default: the common fields are displayed in the center, not stretched. If `true`, the fields are wider than with the default value. ||
|#

{% include [contact-support](../_includes/contact-support.md) %}
