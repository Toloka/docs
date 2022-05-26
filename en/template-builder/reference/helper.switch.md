# helper.switch

A switch-case construction. Checks various conditions sequentially and executes the code from the `result` property when the corresponding condition is true.

You can use it to perform an action or display an additional interface element only when a certain condition is met.

[View example in the sandbox](https://clck.ru/Rf2VQ).

This helper is similar to a series of [If...Then...Else](helper.if.md) logical expressions, so it is useful if there are more than two conditions for sequential verification. If you need to check one or two conditions, use the [helper.if](helper.if.md) component.

How the helper works:

1. The helper checks _(conditions)_ from the array of `cases` objects, starting from the first one.
2. If the condition is true (returns `true`), the helper returns the result (block of code) specified in the `result` property for the `condition` object in the `cases` array. **The helper quits and subsequent conditions are not checked.**
3. If the condition is false (returns `false`), the helper checks the subsequent condition.
4. If all conditions are false as a result of all checks, the helper returns the value specified in the `default` property (if it is not defined, the helper returns nothing).

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "helper.switch" | Set component type ||
|| `cases`<span style="color: red">\*</span> | _array_ | An array of objects consisting of `condition` and `result` property pairs. ||
|| `cases[]` | _object_ | Object parameters. ||
|| `cases[].condition`<span style="color: red">\*</span> | _condition_ | Condition to check. ||
|| `cases[].result`<span style="color: red">\*</span> | _any_ | The element that is returned if the condition from the `condition` property is true (returns `true`). ||
|| `default` | _any_ | Element that is returned if none of the checked conditions returned `true`. ||
|#
