# Completing tasks

## Can I disable tasks for Tolokers who do a poor job on tasks? {#concept_g1f_s1d_pbb}

You can [deny access](../../glossary#banned-worker) to the [pool](../../glossary#pool) if the Toloker's responses are [too fast](control.md#fast-answers), if they don't match the [majority opinion](mvote.md) or if the Toloker makes [too many mistakes in control tasks](goldenset.md). Tasks completed by such Tolokers can be [given to other Tolokers](restore-task-overlap.md).

## Can I fix something in a completed task myself? {#concept_cb5_n1d_pbb}

No, you can't fix anything in the task itself. However, you can do this manually in the [results file](result-of-eval.md).

## Can I ask a Toloker to redo the task if they made mistakes in it? {#concept_ang_g1d_pbb}

No. After sending a task, the Toloker can't make any changes to it. You can add tasks that were [completed](../../glossary#submitted-answers) incorrectly to a new pool.

## How can I notify the Toloker of changes in the instructions? {#notify}

Add a notification to the [project](../../glossary#project) description (for example: “Attention! The [instructions](../../glossary#instructions) changed”) and send a message to all the people who completed your tasks.

To do this:

1. Assign them a hidden [skill](../../glossary#skill), or use an existing [skill](nav-assign.md) linked to the pool.

1. Go to **Messages** and click **Contact** → **Group of Tolokers** → **Add filter** → **Choose your skill** → **&lt;skill name&gt;**.

1. If you created a new skill, specify the value you assigned to the chosen group, (for example, 1). If you use an existing skill, specify the minimum value.

## Can I change overlap after the pool is started? {#change-overlap}

Yes. To change [overlap](../../glossary#overlap) after the pool is started:

1. Stop the pool.

1. Set the new overlap.

1. Wait till the settings are applied. You can see it from the change in the pool budget.

1. Start the pool again.

## Why has the speed of pool completion dropped? {#speed}

You may have stopped the [training pool](../../glossary#training-pool) linked to the main one. This could limit the number of Tolokers with access to the pool. Start the pool again. There will be more Tolokers who can access the tasks.

## More than 500 Tolokers passed the training, but the training skill shows only 30. {#concept_c2y_bdd_pbb}

The pool shows the total number of Tolokers that completed at least one task suite. A training skill can be lost over time if you set repeated training in the pool settings. This setting allows a Toloker to pass the training again after a certain period if the Toloker didn't complete any general tasks or if there was a large time gap between completing tasks (for example, because of a [ban](../../glossary#banned-worker)). The training skill displays the Tolokers who either recently completed training, or regularly complete your tasks so that the skill doesn't expire.

## How can I speed up the pool completion? {#accelerate}

1. To motivate Tolokers, assign a [public skill](nav-create.md#public) and use [dynamic pricing](dynamic-pricing.md).

1. Try to [increase the project rating](#rating), so that your task is higher in the list of tasks for Tolokers.

1. Adjust the [quality-speed ratio](adjust.md).

1. Set a higher [priority](pool_poolparams.md#priority) for the pool among other project pools.

## How can I increase the project's rating? {#rating}

The project rating is the average rating across all categories. Pay particular attention to the categories for which you got the least points.

Low rating for “Will you take similar tasks in the future”

: Perhaps the Tolokers found your tasks too difficult. Try to simplify them.

Low rating for “Clarity of instructions”

: Shorten instructions and rewrite using simpler language. Add pictures and examples.

Low rating for “Task interface usability”

: Make the interface [more user-friendly](spec.md) and don't make the Toloker complete unnecessary actions. Use keyboard shortcuts.

Low rating for “Communication with the requester”

: Reply to [messages from Tolokers](messaging.md) regularly. Try to provide feedback as fast as possible. Correct errors promptly and use mailing lists to notify Tolokers of changes.

If you don't understand what the problem is, run a mini-survey and ask the Tolokers who completed your tasks what they like and what they don't like.

{% include [contact-support](../_includes/contact-support.md) %}