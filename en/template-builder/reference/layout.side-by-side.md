# layout.side-by-side

The component displays several data blocks of the same width on a single horizontal panel. For example, you can use this to compare several photos.

You can set the minimum width for data blocks.

## Component properties {#properties}

| Name                                         | Type                  | Description                                                                                                                                                                                                         |
| -------------------------------------------- | --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span>     | "layout.side-by-side" | <p>Set component type</p>                                                                                                                                                                                           |
| `controls`<span style="color: red">\*</span> | _view_                | <p>Components that let users perform the required actions.</p><p>For example: <a href="field.checkbox-group.md">field.checkbox-group</a> or <a href="field.button-radio-group.md">field.button-radio-group</a>.</p> |
| `items`<span style="color: red">\*</span>    | _array_               | <p>An array of data blocks.</p>                                                                                                                                                                                     |
| `items[]`                                    | _view_                | <p>A component for data output or input. For example, <a href="view.image.md">view.image</a>.</p>                                                                                                                   |
| `minItemWidth`                               | _number_              | <p>The minimum width of a data block, at least 400 pixels.</p>                                                                                                                                                      |
| `validation`                                 | _condition_           | <p>Validation based on condition.</p>                                                                                                                                                                               |
