# helper.text-transform

Allows you to change the case of the text, like make all letters uppercase.

For example, you can use this component to automatically process input data.

This component is available in property values with the `string` type, for example in the `content` property in the [view.text](view.text.md) component.

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "helper.text-transform" | Set component type ||
|| `data`<span style="color: red">\*</span> | _any_ | The text string in which you want to change the case. ||
|| `transformation`<span style="color: red">\*</span> | _string_ | Conversion mode:

- `uppercase` — Makes all letters uppercase.
- `lowercase` — Makes all letters lowercase.
- `capitalize` — Capitalizes **the first** letter in the text, and leaves the rest lowercase. The text is not divided into sentences: there will be only one uppercase letter in the entire text, even if you have several sentences.
  ||
  |#
