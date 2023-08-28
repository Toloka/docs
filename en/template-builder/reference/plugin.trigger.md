# plugin.trigger

Use this to configure triggers that trigger a specific action when an event occurs.

The action is set in the `action` property, and the event is described in the other fields.

The event can be triggered immediately when the task is loaded (`"fireImmediately": true`) or when data changes in the property specified in `onChangeOf`.

You can also set conditions in the `conditions` property that must be met in order for the trigger to fire.

In the following example, the plugin.trigger component is used to modify the original search query: the word "bobtail" is added to the word "cats". This happens immediately after the task is loaded.

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/lxI6fdnn4PTHN4)

{% cut "Components used in the example" %}

- [view.link](view.link.md): Displays a link.
- [helper.search-query](helper.search-query.md): Creates a string with a search query reference.
- [data.output](../operations/work-with-data.md): The output data. This is what you get when a Toloker clicks the **Submit** button.
- [action.set](action.set.md): Sets the value from `payload` in the data in the `data` property.
- [helper.join](../reference/helper.join.md): Joins multiple strings into one string, separating them with spaces or commas.
- [data.input](../operations/work-with-data.md): The input data. For example, links to images that will be shown to Tolokers.

{% endcut %}


## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "plugin.trigger" | Set component type. ||
|| `action` | _action_ | The action to perform when the trigger fires. ||
|| `condition` | _condition_ | The condition that must be met in order to fire the trigger. ||
|| `fireImmediately` | _boolean_ | Flag indicating whether the trigger should be fired immediately after the task is loaded. ||
|| `onChangeOf` | _reactive_ | The data that triggers the action when changed. ||
|#

{% include [contact-support](../_includes/contact-support.md) %}
