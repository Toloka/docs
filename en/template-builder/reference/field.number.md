# field.number

A component that allows a Toloker to enter a number.

Only numbers and decimal separators can be entered in the field. A Toloker can enter a dot or a comma as a separator, but the dot is always used in the output.

When a Toloker enters a number, the separator automatically changes to the one specified in the regional settings. In some countries, the decimal separator is a comma.

You can also set up validation, for example, disable negative or fractional numbers. [Learn more](../operations/components-for-numbers.md).

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "field.number" | Set component type ||
|| `data`<span style="color: red">\*</span> | _writable_ | Data with values that will be processed or changed. ||
|| `label` | _string_ | Label above the component. ||
|| `hint` | _string_ | Hint text. ||
|| `maximum` | _integer_ | Maximum number that can be entered. ||
|| `minimum` | _integer_ | Minimum number that can be entered. ||
|| `placeholder` | _string_ | A semi-transparent label that is shown in the box when it is empty. ||
|| `validation` | _condition_ | Validation based on condition. ||
|#
