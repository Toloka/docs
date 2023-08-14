# plugin.toloka

A plugin with extra settings for tasks in Toloka.

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/LdbPJiUn4PP3rK)

{% cut "Components used in the example" %}

- [field.checkbox](../reference/field.checkbox.md): To add a checkbox.
- [data.output](../operations/work-with-data.md): The output data. This is what you get when a Toloker clicks the **Submit** button.
- [condition.required](condition.required.md): Checks if an option is selected.

{% endcut %}


## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "plugin.toloka" | Set component type. ||
|| `layout`<span style="color: red">\*</span> | _object_ | Settings for the task appearance in Toloka. [Learn more](../operations/set-plugin-toloka.md) ||
|| `layout.kind`<span style="color: red">\*</span> | _string_ | How to display tasks:

- `scroll` (default) — display multiple tasks on the page at the same time.
- `pager` — display only one task on the page, with a button to switch between tasks at the bottom.
  ||
  || `layout.taskWidth` | _number_ | Width of the block with the task. By default, the task is displayed at full width. ||
  || `notifications` | _array_ | An array of notifications. Notifications are displayed at the top of the page. ||
  || `notifications[]` | _view_ | Notification parameters. ||
  |#

{% include [contact-support](../_includes/contact-support.md) %}
