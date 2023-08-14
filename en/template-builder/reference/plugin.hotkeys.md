# plugin.hotkeys

You can use this to set keyboard shortcuts for actions.

[Learn more about hotkeys](../best-practices/hotkeys.md).

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/07sEKt6y4PNykY)

{% cut "Components used in the example" %}

- [field.checkbox](../reference/field.checkbox.md): To add a checkbox.
- [data.output](../operations/work-with-data.md): The output data. This is what you get when a Toloker clicks the **Submit** button.
- [condition.required](condition.required.md): Checks if an option is selected.
- [action.toggle](action.toggle.md): Changes the value in the data from `true` to `false` and vice versa. 

{% endcut %}


## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "plugin.hotkeys" | Set component type. ||
|| `a-z\|0-9\|up\|down` | _string_ | Select a key (a Latin letter, a number, or an up/down arrow) and configure it to do the same action as the component that you assign it to. The action is called when the selected key is pressed. ||
|#

{% include [contact-support](../_includes/contact-support.md) %}
