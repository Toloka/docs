# action.bulk

Use this component to call multiple actions at the same time, like to show more than one notification when a button is clicked.

[View example in the sandbox](https://clck.ru/Rf2Z4).

Actions are invoked in the order in which they are listed. This means that if two actions write a value to the same variable, the variable will always have the second value.

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "action.bulk" | Set component type ||
|| `payload` | _array_ | An array of actions that you want to call. ||
|| `payload[]` | _action_ | Action. ||
|#
