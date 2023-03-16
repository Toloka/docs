# condition.all

Checks that **all** child conditions are met. If any of the conditions is not met, the component returns 'false'.

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/oG54z4RK3vwCUQ)

If you only need one out of several conditions to be met, use the [condition.any](condition.any.md) component. You can also combine these components.

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "condition.all" | Set component type ||
|| `conditions` | _array_ | A set of conditions that must be met. ||
|| `conditions[]` | _condition_ | Required condition. ||
|| `hint` | _string_ | Validation error message that a Toloker will see ||
|#

{% include [contact-support](../_includes/contact-support.md) %}
