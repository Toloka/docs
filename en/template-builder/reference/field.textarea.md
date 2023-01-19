# field.textarea

Box for entering multi-line text. Use in tasks that require an extended response. For single-line responses, use the [field.text](field.text.md) component.

The size of the box does not automatically adjust to the length of the text. Tolokers can change the height by dragging the lower-right corner. To change the default size of the box, use the `rows` property.

Note that formatting is not available in the text box.

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/8LH9Vrwt3tz2pE)

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "field.textarea" | Set component type ||
|| `data`<span style="color: red">\*</span> | _writable_ | Data with values that will be processed or changed. ||
|| `label` | _string_ | Label above the component. ||
|| `disabled` | _boolean_ | If `true`, editing is not available. ||
|| `hint` | _string_ | Hint text. ||
|| `placeholder` | _string_ | A semi-transparent label that is shown when the box is empty. Use it to provide an example or a hint for the response. ||
|| `requiredMark` | _boolean_ | Show "\*" next to the label ||
|| `resizable` | _boolean_ | Changing the box size. When set to `true` (the default value), a Toloker can change the height. To prevent resizing, set the value to `false`. ||
|| `rows` | _number_ | The height of the text box in lines. ||
|| `rtl` | _object_ | In some languages, like Arabic or Hebrew, text is written from right to left. Use this property to set up the correct display mode for the component.

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/tq6fCNm_3ttFBW)

[Learn more about RTL languages](https://www.w3.org/International/questions/qa-scripts). ||
|| `rtl.mode` | _string_ | Display mode:

- `ltr` — left to right.
- `rtl` — right to left.

The chosen value will be added to the `dir` attribute in the component's HTML code. [Learn more about dir](https://www.w3.org/International/questions/qa-html-dir). ||
|| `validation` | _condition_ | Validation based on condition. ||
|#
