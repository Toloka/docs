# Overview

You can create a subscription and receive notifications from Toloka when certain events occur, for example:

- When a pool closes.
- When a task's status changes to a specified one.
- When an aggregated score appears after dynamic overlap.

The events that you want to be notified about are set when [creating a subscription](put-webhook-subscriptions.md).

Notifications about the events you're subscribed to are sent in JSON format. For a description of notification data, see [Notification format](using-webhook-subscriptions.md).

## Methods {#methods}

Method | Endpoint | Overview
----- | ----- | -----
PUT | [/webhook-subscriptions](put-webhook-subscriptions.md) | Creates one or more subscriptions.
GET | [/webhook-subscriptions/<subscription_id>](get-webhook-subscriptions.md) | Gets subscription data.
GET | [/webhook-subscriptions](get-webhook-subscriptions-list.md) | Gets data for multiple active subscriptions.
DELETE | [/webhook-subscriptions/<subscription_id>](delete-webhook-subscriptions.md) | Deletes a subscription.
POST | [/webhook-subscriptions/<subscription_id>/test](post-webhook-subscriptions.md) | Sends a test notification to the URL specified in the subscription.

{% include [contact-support](../../guide/_includes/contact-support.md) %}