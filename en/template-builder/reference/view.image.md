# view.image

Displays an image.

[Learn more about inserting images](../operations/insert-images.md).

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "view.image" | Set component type ||
|| `label` | _string_ | Label above the component. ||
|| `fullHeight` | _boolean_ | If `true`, the element takes up all the vertical free space. The element is set to a minimum height of 400 pixels. ||
|| `hint` | _string_ | Hint text. ||
|| `maxWidth` | _number_ | Maximum width of the element in pixels, must be greater than `minWidth`. ||
|| `minWidth` | _number_ | Minimum width of the element in pixels. Takes priority over `maxWidth`. ||
|| `noBorder` | _boolean_ | Controls the display of a frame around an image. By default, `true` (the frame is hidden). Set `false` to display the frame. ||
|| `noLazyLoad` | _boolean_ | Disables lazy loading.

If `true`, images start loading immediately, even if they aren't in the viewport. Useful for icons.

By default, `false` (lazy loading is enabled). In this mode, images start loading only when they get in an annotator's field of view. ||
|| `popup` | _boolean_ | Specifies whether opening a full-size image with a click is allowed. By default, it is `true` (allowed). ||
|| `ratio` | _array_ | An array of two numbers that sets the relative dimensions of the sides: width (first number) to height (second number).

Not valid if `"fullHeight": true`. ||
|| `ratio[]` | _number_ | Relative size of one side. ||
|| `rotatable` | _boolean_ | If enabled, an image can be rotated. ||
|| `scrollable` | _boolean_ | When set to `true`, an image has scroll bars if it doesn't fit in the parent element.

If `false`, the image fits in the parent element and, when clicked, opens in its original size in the module window.

Images in SVG format with no size specified always fit in their parent elements. ||
|| `url`<span style="color: red">\*</span> | _string_ | Image link. ||
|| `validation` | _condition_ | Validation based on condition. ||
|#
