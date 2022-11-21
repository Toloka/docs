# Majority vote

We recommend using aggregation for tasks with an [overlap](../glossary.md#overlap) of 2 or higher. Learn more about this process in [Aggregation of results](result-aggregation.md).

Majority vote is one of the aggregation methods used for object classification tasks. It determines the most common response to each task. In addition, the majority vote algorithm can take into account the skills and other characteristics of Tolokers. In this case, each response is assigned a weight, and the aggregation result will be the response option with the largest sum of weights.

{% note info %}

Aggregation only includes accepted tasks.

{% note info %}

## Troubleshooting

{% cut "Where do I see the aggregation progress?" %}

The pool page contains the {% if locale == "en-com" %}**List of Operations**{% endif %} button.

{% endcut %}

{% cut "Can I get notifications when results aggregation finishes?" %}

Yes. To set up notifications in your account, go to **Profile → Notifications → Pool or aggregation completed**. Learn more about [setting up notifications](../concepts/result-aggregation.md).

{% endcut %}

{% include [contact-support](../_includes/contact-support-help.md) %}