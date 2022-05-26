# plugin.toloka

A plugin with extra settings for tasks in Toloka.

## Component properties {#properties}

| Name                                            | Type            | Description                                                                                                                                                                                                                       |
| ----------------------------------------------- | --------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span>        | "plugin.toloka" | <p>Set component type</p>                                                                                                                                                                                                         |
| `layout`<span style="color: red">\*</span>      | _object_        | <p>Settings for the task appearance in Toloka. <a href="../operations/set-plugin-toloka.dita">Learn more</a></p>                                                                                                                  |
| `layout.kind`<span style="color: red">\*</span> | _string_        | <p>How to display tasks:</p><ul><li>`scroll` (default) — display multiple tasks on the page at the same time.</li><li>`pager` — display only one task on the page, with a button to switch between tasks at the bottom.</li></ul> |
| `layout.taskWidth`                              | _number_        | <p>Width of the block with the task. By default, the task is displayed at full width.</p>                                                                                                                                         |
| `notifications`                                 | _array_         | <p>An array of notifications. Notifications are displayed at the top of the page.</p>                                                                                                                                             |
| `notifications[]`                               | _view_          | <p>Notification parameters.</p>                                                                                                                                                                                                   |
