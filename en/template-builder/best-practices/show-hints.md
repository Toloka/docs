# Show hints

Use hints to convey [important information](#fixed-notifications) to Tolokers, help them [resolve issues](#errors) and [fill out fields](#hints) correctly, and [alert](#notifications) them when they attempt certain actions. Template Builder provides auxiliary components for different needs.


## Add fixed alerts at the top of the screen {#fixed-notifications}

To keep Tolokers aware of important information, add fixed alerts above the tasks: this is the text at the top of the screen that never disappears when Tolokers navigate between the task suites.

For example, such messages can be helpful when the requester edits the instructions and wants to keep Tolokers updated.

Use the [plugin.toloka](../reference/plugin.toloka.md) plugin to add fixed alerts. To add one or more messages, specify them in the `notifications` property.

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/BOk2_RsN3YbFFg)


## Specify the causes for validation errors {#errors}

To help Tolokers resolve issues that cause errors, give more specific causes for validation errors. For this purpose, you can add the `hint` property to any [condition](../reference/conditions.md).

[![image](../_images/buttons/view-example.svg)](https://clck.ru/TR7r4)


## Add explanations to the fields with the help of hints {#hints}

To add small explanations to elements, use the `hint` property: it's added to every [data entry element](../reference/fields.md) and [display element](../reference/views.md). Hints are shown when Tolokers click ![image](../_images/info.svg).

[![image](../_images/buttons/view-example.svg)](https://ya.cc/t/wWiEZlyr3YbFWi)


## Show notifications {#notifications}

You can use notifications to inform your Tolokers. Notifications are displayed in the lower-left corner of the screen. You can set the color and time parameters for notifications.

To show notifications when Tolokers click a button, add the [view.action-button](../reference/view.action-button.md) element to the template and set the `action` property to [action.notify](../reference/action.notify.md).

[![image](../_images/buttons/view-example.svg)](https://clck.ru/TR827)


[![image](../_images/buttons/contact-support.svg)](../concepts/support.md)
