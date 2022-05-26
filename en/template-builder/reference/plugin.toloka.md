# plugin.toloka

A plugin with extra settings for tasks in Toloka.

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "plugin.toloka" | Set component type ||
|| `layout`<span style="color: red">\*</span> | _object_ | Settings for the task appearance in Toloka. [Learn more](../operations/set-plugin-toloka.md) ||
|| `layout.kind`<span style="color: red">\*</span> | _string_ | How to display tasks:

- `scroll` (default) — display multiple tasks on the page at the same time.
- `pager` — display only one task on the page, with a button to switch between tasks at the bottom.
  ||
  || `layout.taskWidth` | _number_ | Width of the block with the task. By default, the task is displayed at full width. ||
  || `notifications` | _array_ | An array of notifications. Notifications are displayed at the top of the page. ||
  || `notifications[]` | _view_ | Notification parameters. ||
  |#
