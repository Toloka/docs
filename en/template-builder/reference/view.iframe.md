# view.iframe

Displays the web page at the URL in an iframe window.

[![View example](../_images/buttons/view-example.svg)](https://ya.cc/t/MQwwYlAL4Nq7n7)

{% cut "Components used in the example" %}

- [data.input](../operations/work-with-data.md):  Input data.

{% endcut %}

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "view.iframe" | Set component type. ||
|| `label` | _string_ | Label above the component. ||
|| `fullHeight` | _boolean_ | If `true`, the element takes up all the vertical free space. The element is set to a minimum height of 400 pixels. ||
|| `hint` | _string_ | Hint text. ||
|| `maxWidth` | _number_ | Maximum width of the element in pixels, must be greater than `minWidth`. ||
|| `minWidth` | _number_ | Minimum width of the element in pixels. Takes priority over `maxWidth`. ||
|| `ratio` | _array_ | An array of two numbers that sets the relative dimensions of the sides: width (first number) to height (second number).

Not valid if `"fullHeight": true`. ||
|| `ratio[]` | _number_ | Relative size of one side. ||
|| `url`<span style="color: red">\*</span> | _string_ | URL of the web page. ||
|| `validation` | _condition_ | Validation based on condition. ||
|#

{% include [contact-support](../_includes/contact-support.md) %}
