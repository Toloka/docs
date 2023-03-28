# @toloka/data.assignment-id

This component returns the assignment ID.

This might be useful in case Tolokers click links to go to some other platform and complete their tasks there (for example, take a survey on a third-party platform). This way, it won't be possible to identify them or track their actions unless you know the ID of the assignment.

To get the assignment ID, add `{"type": "@yandex-toloka/data.assignment-id"}` to the property of the desired component.

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/I_2W-b_i452rEC)

{% cut "Components used in the example" %}

- [view.list](view.list.md): Displays data in a list.
- [view.link](view.link.md): Displays a link.
- [plugin.trigger](plugin.trigger.md): Triggers a specific action when an event occurs.
- [action.set](action.set.md): Sets the value from `payload` in the data in the `data` property.
- [helper.join](helper.join.md): Combines two or more strings into one.

{% endcut %}

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "@toloka/data.assignment-id" | Set component type. ||
|#

{% include [contact-support](../_includes/contact-support.md) %}
