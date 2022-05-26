# layout.side-by-side

The component displays several data blocks of the same width on a single horizontal panel. For example, you can use this to compare several photos.

You can set the minimum width for data blocks.

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "layout.side-by-side" | Set component type ||
|| `controls`<span style="color: red">\*</span> | _view_ | Components that let users perform the required actions.

For example: [field.checkbox-group](field.checkbox-group.md) or [field.button-radio-group](field.button-radio-group.md). ||
|| `items`<span style="color: red">\*</span> | _array_ | An array of data blocks. ||
|| `items[]` | _view_ | A component for data output or input. For example, [view.image](view.image.md). ||
|| `minItemWidth` | _number_ | The minimum width of a data block, at least 400 pixels. ||
|| `validation` | _condition_ | Validation based on condition. ||
|#
