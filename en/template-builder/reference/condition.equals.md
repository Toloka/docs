# condition.equals

Checks whether the original value is equal to the specified value. If it matches, it returns `true`, otherwise it returns `false`.

When substituting values, you can refer to `data.*` or another element using `$ref`. You can also use [helpers](helpers.md) and [conditions](conditions.md) to get the value.

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/2RjfdQbt3tz7xo)

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "condition.equals" | Set component type ||
|| `data` | _any_ | Original value. If not specified, it uses the value returned by the parent component (the component that contains `condition.equals`).

How to pass a value:

- Specify the value itself, like the number 42 or a string.
- [Get the value from your data](../operations/work-with-data.md).
- Refer to another element using `$ref`.
- Use [helpers](helpers.md) and [conditions](conditions.md) to get the value. ||
  || `hint` | _string_ | Validation error message that a Toloker will see ||
  || `to`<span style="color: red">\*</span> | _any_ | The value to compare with the original.

How to pass a value:

- Specify the value itself, like the number 42 or a string.
- [Get the value from your data](../operations/work-with-data.md).
- Refer to another element using `$ref`.
- Use [helpers](helpers.md) and [conditions](conditions.md) to get the value. ||
  |#
