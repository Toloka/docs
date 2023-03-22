# view.alert

The component creates a color block to highlight important information.

You can use both plain text and other visual components inside it.

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/lBobocfj3tyyJo)

{% cut "Components used in the example" %}

- [view.list](view.list.md): Displays data in a list.
- [view.text](view.text.md): Adds a block with text. 

{% endcut %}


## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "view.alert" | Set component type. ||
|| `label` | _string_ | Label above the component. ||
|| `content` | _view_ | Content of the block with important information. ||
|| `hint` | _string_ | Hint text. ||
|| `theme` | _string_ | Determines the block color:

- `info` (default) — Blue.
- `success` — Green.
- `warning` — Yellow.
- `danger` — Red.
  ||
  || `validation` | _condition_ | Validation based on condition. ||
  |#

{% include [contact-support](../_includes/contact-support.md) %}

