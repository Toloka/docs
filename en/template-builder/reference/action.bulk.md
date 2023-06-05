# action.bulk

Use this component to call multiple [actions](actions.md) at the same time, like to show more than one notification when a button is clicked.

Actions are invoked in the order in which they are listed. This means that if two actions write a value to the same variable, the variable will always have the second value.

[![View example in the sandbox](../_images/buttons/view-example.svg)](https://ya.cc/t/jH6BvDpE3twfMn)

{% cut "Components used in the example" %}

- [view.list](view.list.md): Displays data in a list.
- [view.text](view.text.md): Displays a text.
- [view.action-button](view.action-button.md): Displays a button that calls an action.
- [action.notify](action.notify.md): Adds a component that creates a message in the lower-left corner of the screen.

{% endcut %}

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "action.bulk" | Set component type. ||
|| `payload[]` | _array_ | An array of [actions](actions.md) that you want to call. ||
|#

{% include [contact-support](../_includes/contact-support.md) %}
