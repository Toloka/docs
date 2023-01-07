# Project rating

The [project](../../glossary.md#project) rating is the average score given to a project by Tolokers over the last 14 days. There are four evaluation categories:

1. The intention to complete similar tasks.
1. Clarity of [instructions](../../glossary.md#instructions).
1. Convenience of the [task interface](../../glossary.md#task-interface).
1. Communication with the requester.

The project rating is available to Tolokers. By default, the list of tasks is sorted by project rating.

## Troubleshooting {#troubleshooting}

{% cut "How can I increase the project's rating?" %}

The project rating is the average rating across all categories. Pay particular attention to the categories for which you got the least points.

{% include [troubleshooting-low-rating-similar-tasks](../_includes/troubleshooting/result-questions/low-rating-similar-tasks.md) %}

{% include [troubleshooting-low-rating-instructions](../_includes/troubleshooting/result-questions/low-rating-instructions.md) %}

{% cut "Low rating for “Task interface usability”" %}

Make the interface [more user-friendly](spec.md) and don't make the Toloker complete unnecessary actions. Use keyboard shortcuts.

Starting from December 15, 2021, tasks in pools are automatically available in the web version of Toloka and the mobile app. If your task isn't available on mobile devices, it means that you might have forgotten to add the {% if locale == "en-com" %}**Client**{% endif %} filter.

{% endcut %}

{% cut "Low rating for “Communication with the requester”" %}

Reply to [messages from Tolokers](messaging.md) regularly. Try to provide feedback as fast as possible. Correct errors promptly and use mailing lists to notify Tolokers of changes.

{% endcut %}

If you don't understand what the problem is, run a mini-survey and ask the Tolokers who completed your tasks what they like and what they don't like.

{% endcut %}

{% include [contact-support](../_includes/contact-support.md) %}