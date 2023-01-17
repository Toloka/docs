# Starting and stopping a task pool

You can start a [pool](../../glossary.md#pool) if:

1. You uploaded tasks into it.

1. You have enough money in [your account](budget.md) to pay for the pool tasks, including the [overlap](../../glossary.md#overlap).

To start the pool, click ![](../_images/other/b-start-pool.svg) on the pool page or ![](../_images/tutorials/content-moderation/pool-action-play.svg) in the list of pools on the [project](../../glossary.md#project) page.

A started pool has the status {% if locale == "en-com" %}“Open”{% endif %}. When all pool tasks are completed, the pool automatically switches to the {% if locale == "en-com" %}“Closed”{% endif %} status.

To stop assigning the pool tasks before all of them are completed, click ![](../_images/other/b-pause-pool.svg) on the pool page or ![](../_images/tutorials/content-moderation/pool-action-pause.svg) in the list of pools on the project page.

{% note tip %}

New tasks can be uploaded to an open or closed pool.

{% endnote %}

## What's next {#what_next}

- [Get and process the results](result-of-eval.md).

## Troubleshooting {#troubleshooting}

{% cut "I created a project and a pool, but the Next button doesn't work or the preview shows a blank screen." %}

Toloka lets you know that something is wrong with the project. The blank screen often appears when there are errors in the [task interface](../../glossary.md#task-interface), including the JavaScript code. The **Next** button may be disabled if the output specification lacks some field or contains invalid values, or if, for example, you configured validation for a nonexistent field in JavaScript.

{% endcut %}

{% cut "What overlap should I set?" %}

Overlap defines how many Tolokers complete the same pool task.

The best overlap is an overlap that provides satisfying quality of results. For most tasks that are not [reviewed](../../glossary.md#assignment-review), overlap from “3” to “5” is enough. If the tasks are simple, overlap of “3” is likely to be enough. For tasks that are reviewed, set overlap to “1”.

{% endcut %}

{% include [faq-change-overlap](../_includes/faq/pool-setup/change-overlap.md) %}

{% include [faq-dynamic-overlap](../_includes/faq/pool-setup/dynamic-overlap.md) %}

{% include [contact-support](../_includes/contact-support.md) %}