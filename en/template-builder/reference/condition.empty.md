# condition.empty

Checks that the data didn't get a value. If it did, returns `false`. This is useful if you need to check the optional template data (`data.*`) or make sure that a Toloker didn't interact with the data entry fields (`fields.*`).

[View example in the sandbox](https://clck.ru/asRzy).

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "condition.empty" | Set component type ||
|| `data` | _any_ | Data to check. If not specified, data is checked in the component that contains `condition.empty`. ||
|| `hint` | _string_ | Validation error message that a Toloker will see ||
|#
