# Starting and stopping a task pool

You can start a [pool](../../glossary.md#pool) if:

1. You uploaded tasks into it.

1. You have enough money in [your account](budget.md) to pay for the pool tasks, including the [overlap](../../glossary.md#overlap).

To start the pool, click ![](../_images/other/b-start-pool.png) on the pool page or ![](../_images/tutorials/content-moderation/pool-action-play.png) in the list of pools on the [project](../../glossary.md#project) page.

A started pool has the status {% if locale == "en-com" %}“Open”{% endif %}. When all pool tasks are completed, the pool automatically switches to the {% if locale == "en-com" %}“Closed”{% endif %} status.

To stop assigning the pool tasks before all of them are completed, click ![](../_images/other/b-pause-pool.png) on the pool page or ![](../_images/tutorials/content-moderation/pool-action-pause.png) in the list of pools on the project page.

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

{% cut "Can I change overlap after the pool is started?" %}

Yes. [Open edit mode for the pool](pool-edit.md) and set a new overlap value. You don't need to restart the pool. Updating the settings is usually fast, but if there are many tasks, it may take several minutes.

{% endcut %}

{% cut "With dynamic overlap, is it possible that the pool will close before the tasks for minimal overlap run out? The overlap increased, but the pool is closed, and I need to start it manually." %}

Yes, this might happen. You must set an adequate pool closing interval.

{% endcut %}

{% include [contact-support](../_includes/contact-support-help.md) %}