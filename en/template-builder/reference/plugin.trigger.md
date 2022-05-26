# plugin.trigger

Use this to configure triggers that trigger a specific action when an event occurs.

The action is set in the `action` property, and the event is described in the other fields.

The event can be triggered immediately when the task is loaded (`"fireImmediately": true`) or when data changes in the property specified in `onChangeOf`.

You can also set conditions in the `conditions` property that must be met in order for the trigger to fire.

## Component properties {#properties}

| Name                                     | Type             | Description                                                                                      |
| ---------------------------------------- | ---------------- | ------------------------------------------------------------------------------------------------ |
| `type`<span style="color: red">\*</span> | "plugin.trigger" | <p>Set component type</p>                                                                        |
| `action`                                 | _action_         | <p>The action to perform when the trigger fires.</p>                                             |
| `condition`                              | _condition_      | <p>The condition that must be met in order to fire the trigger.</p>                              |
| `fireImmediately`                        | _boolean_        | <p>Flag indicating whether the trigger should be fired immediately after the task is loaded.</p> |
| `onChangeOf`                             | _reactive_       | <p>The data that triggers the action when changed.</p>                                           |
