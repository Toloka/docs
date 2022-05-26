# condition.link-opened

Checks that the user clicked the link.

[View example in the sandbox](https://clck.ru/asS5W).

**Important:** To trigger the condition, the user must follow the link from the Toloka interface — you must give users this option. The condition will not work if the user opens the link from the browser address bar.

This condition can be used in the [view.link](view.link.md) component and also anywhere you can use _(conditions)_.

## Component properties {#properties}

| Name                                     | Type                    | Description                                            |
| ---------------------------------------- | ----------------------- | ------------------------------------------------------ |
| `type`<span style="color: red">\*</span> | "condition.link-opened" | <p>Set component type</p>                              |
| `hint`                                   | _string_                | <p>Validation error message that the user will see</p> |
| `url`                                    | _string_                | <p>The link that must be clicked.</p>                  |
