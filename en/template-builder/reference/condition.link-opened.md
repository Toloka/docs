# condition.link-opened

Checks that the annotator clicked the link.

[View example in the sandbox](https://clck.ru/asS5W).

**Important:** To trigger the condition, the annotator must follow the link from the Toloka interface — you must give annotators this option. The condition will not work if the annotator opens the link from the browser address bar.

This condition can be used in the [view.link](view.link.md) component and also anywhere you can use _(conditions)_.

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "condition.link-opened" | Set component type ||
|| `hint` | _string_ | Validation error message that the annotator will see ||
|| `url` | _string_ | The link that must be clicked. ||
|#
