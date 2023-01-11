# field.button-radio-group

Adds buttons for selecting an answer option. This is useful if there are several options. You can add just one button, but it's easier to use [field.button-radio](field.button-radio.md) for that.

The button size depends on the length of the text.

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/jBYQsbgj3twiqX)

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "field.button-radio-group" | Set component type ||
|| `data`<span style="color: red">\*</span> | _writable_ | Data with values that will be processed or changed. ||
|| `label` | _string_ | Label above the component. ||
|| `disabled` | _boolean_ | This property prevents clicking the button. If the value is `true`, the button is not active (a Toloker will not be able to click it). ||
|| `hint` | _string_ | Hint text. ||
|| `options`<span style="color: red">\*</span> | _array_ | An array of buttons. ||
|| `options[]` | _object_ | A button. ||
|| `options[].hint` | _string_ | Additional information. ||
|| `options[].label`<span style="color: red">\*</span> | _string_ | The text on the button. ||
|| `options[].value`<span style="color: red">\*</span> | _any_ | Returned value. ||
|| `rtl` | _object_ | In some languages, like Arabic or Hebrew, text is written from right to left. Use this property to set up the correct display mode for the component.

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/tq6fCNm_3ttFBW).

[Learn more about RTL languages](https://www.w3.org/International/questions/qa-scripts). ||
|| `rtl.mode` | _string_ | Display mode:

- `ltr` — left to right.
- `rtl` — right to left.

The chosen value will be added to the `dir` attribute in the component's HTML code. [Learn more about dir](https://www.w3.org/International/questions/qa-html-dir). ||
|| `validation` | _condition_ | Validation based on condition. ||
|#
