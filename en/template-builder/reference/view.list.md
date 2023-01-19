# view.list

Block for displaying data in a list. May contain an unlimited number of `view.*` [components](https://toloka.ai/en/docs/template-builder/reference/).

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/ATPjrNYU3vUaRK)

{% cut "Components used in the example" %}

- [view.image](../reference/view.image.md): Image.
- [field.button-radio-group](../reference/field.button-radio-group.md): Buttons for answer options.
- [condition.required](../reference/condition.required.md): Checks if at least one option is selected.

{% endcut %}

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "view.list" | Set component type ||
|| `label` | _string_ | Label above the component. ||
|| `direction` | _string_ | Determines the direction of the list:

- `vertical` (default) — vertical list.
- `horizontal` — horizontal list. ||
  || `hint` | _string_ | Hint text. ||
  || `items`<span style="color: red">\*</span> | _array_ | Array of list items. ||
  || `items[]` | _view_ | List item. ||
  || `rtl` | _object_ | In some languages, like Arabic or Hebrew, text is written from right to left. Use this property to set up the correct display mode for the component.

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/tq6fCNm_3ttFBW)

[Learn more about RTL languages](https://www.w3.org/International/questions/qa-scripts). ||
|| `rtl.mode` | _string_ | Display mode:

- `ltr` — left to right.
- `rtl` — right to left.

The chosen value will be added to the `dir` attribute in the component's HTML code. [Learn more about dir](https://www.w3.org/International/questions/qa-html-dir). ||
|| `size` | _string_ | Specifies the size of the margins between elements. Acceptable values in ascending order: `s`, `m` (default value). ||
|| `validation` | _condition_ | Validation based on condition. ||
|#
