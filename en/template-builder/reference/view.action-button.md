# view.action-button

Button that calls an action.

When clicking the button, an action specified in the `action` property is called.

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/BiV4rmEt45Vu5w)

{% cut "Components used in the example" %}

- [view.list](view.list.md): Displays data in a list.
- [view.text](view.text.md): Adds a block with text. 
- [action.open-link](action.open-link.md): Opens a new tab in the browser with the specified web-page. 

{% endcut %}

## Component properties {#properties}

#|
|| **Name** | **Type** | **Description** ||
|| `type`<span style="color: red">\*</span> | "view.action-button" | Set component type. ||
|| `label` | _string_ | Button text. ||
|| `action` | _action_ | Action called when clicking the button. ||
|| `hint` | _string_ | Hint text. ||
|| `validation` | _condition_ | Validation based on condition. ||
|#

{% include [contact-support](../_includes/contact-support.md) %}
