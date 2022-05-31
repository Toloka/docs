# Show hints

Use hints to convey [important information](#fixed-notifications) to the performers, help them [resolve issues](#errors) and [fill out fields](#hints) correctly, and [alert](#notifications) them when they attempt certain actions. Template Builder provides auxiliary components for different needs.


## Add fixed alerts at the top of the screen {#fixed-notifications}

To keep performers aware of important information, add fixed alerts above the tasks: this is the text at the top of the screen that never disappears when users navigate between the task suites.

For example, such messages can be helpful when the requester edits the instructions and wants to keep the users updated.

Use the [plugin.toloka](../reference/plugin.toloka.md) plugin to add fixed alerts. To add one or more messages, specify them in the `notifications` property.

[View example in the sandbox](https://clck.ru/TR7jj).


## Specify the causes for validation errors {#errors}

To help users resolve issues that cause errors, give more specific causes for validation errors. For this purpose, you can add the `hint` property to any [condition](../reference/conditions.md).

[View example in the sandbox](https://clck.ru/TR7r4).


## Add explanations to the fields with the help of hints {#hints}

To add small explanations to elements, use the `hint` property: it's added to every [data entry element](../reference/fields.md) and [display element](../reference/views.md). Hints are shown when users click ![image](../_images/info.svg).

[View example in the sandbox](https://clck.ru/TR7wF).


## Show notifications {#notifications}

You can use notifications to inform your users. Notifications are displayed in the lower-left corner of the screen. You can set the color and time parameters for notifications.

To show notifications when users click a button, add the [view.action-button](../reference/view.action-button.md) element to the template and set the `action` property to [action.notify](../reference/action.notify.md).

[View example in the sandbox](https://clck.ru/TR827).


[![image](../_images/buttons/contact-support.svg)](../concepts/support.md)
