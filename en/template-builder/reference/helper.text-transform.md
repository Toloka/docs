# helper.text-transform

Allows you to change the case of the text, like make all letters uppercase.

For example, you can use this component to automatically process input data.

This component is available in property values with the `string` type, for example in the `content` property in the [view.text](view.text.md) component.

## Component properties {#properties}

| Name                                               | Type                                                                             | Description                                                                                                                                                                                                                                                                                                                                                                                     |
| -------------------------------------------------- | -------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span>           | "helper.text-transform"                                                          | <p>Set component type</p>                                                                                                                                                                                                                                                                                                                                                                       |
| `data`<span style="color: red">\*</span>           | <a class="xref popup-link" href="../concepts/types.dita#types/any">any</a>       | <p>The text string in which you want to change the case.</p>                                                                                                                                                                                                                                                                                                                                    |
| `transformation`<span style="color: red">\*</span> | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a> | <p>Conversion mode:</p><ul><li>`uppercase` — Makes all letters uppercase.</li><li>`lowercase` — Makes all letters lowercase.</li><li>`capitalize` — Capitalizes <strong>the first</strong> letter in the text, and leaves the rest lowercase. The text is not divided into sentences: there will be only one uppercase letter in the entire text, even if you have several sentences.</li></ul> |
