# condition.required

Checks that the field which must contain the data is present in the response. This way you can get a Toloker to answer all the required questions.

If used inside the `validation` property, you can omit the `data` property and the same property will be used from the parent component [field](fields.md) (the one that contains the `condition.required` component).

[View example in the sandbox](https://clck.ru/asSBw).

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "condition.required" | Set component type ||
|| `data` | _any_ | Data to be filled in. If the property is not specified, the data of the parent component (the one that contains `condition.required`) is used. ||
|| `hint` | _string_ | Validation error message that a Toloker will see ||
|#
