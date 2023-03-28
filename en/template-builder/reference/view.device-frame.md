# view.device-frame

Wraps the content of a component in a frame that is similar to a mobile phone. You can place other components inside the frame.

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "view.device-frame" | Set component type. ||
|| `label` | _string_ | Label above the component. ||
|| `content` | _view_ | Content inside the frame. ||
|| `fullHeight` | _boolean_ | If `true`, the element takes up all the vertical free space. The element is set to a minimum height of 400 pixels. ||
|| `hint` | _string_ | Hint text. ||
|| `maxWidth` | _number_ | Maximum width of the element in pixels, must be greater than `minWidth`. ||
|| `minWidth` | _number_ | Minimum width of the element in pixels. Takes priority over `maxWidth`. ||
|| `ratio` | _array_ | An array of two numbers that sets the relative dimensions of the sides: width (first number) to height (second number).

Not valid if `"fullHeight": true`. ||
|| `ratio[]` | _number_ | Relative size of one side. ||
|| `validation` | _condition_ | Validation based on condition. ||
|#

{% include [contact-support](../_includes/contact-support.md) %}
