# Setting up quality control

Quality control lets you get more accurate responses and restrict access to tasks for cheating Tolokers. Quality control consists of rules. All rules work independently.

{% note warning %}

Quality control settings in a [project](../../glossary.md#project) are applied to all project [pools](../../glossary.md#pool), so you can't change them in just one of the pools.

When you [clone a project](project.md), its quality control settings aren't transferred.

{% endnote %}

To set up quality control:

1. Open the project page.

1. Go to the {% if locale == "en-com" %}**Quality control**{% endif %} tab.

1. Click {% if locale == "en-com" %}**Set quality control**{% endif %}.

1. Click {% if locale == "en-com" %}**Add Quality Control Rule**{% endif %}.

1. In the list that appears, select the appropriate rules. If you aren't sure what quality control rules you need, select a ready-made protection set of rules with default settings.

1. Make settings for the rules you added. Below is a list of rules with links to detailed information about the rule settings.

## List of rules {#id_z4l_prs_2lb}

- **To keep track of how often Tolokers make mistakes:**

    - [Control tasks](goldenset.md): Use them to assign a [skill](../../glossary.md#skill) to Tolokers based on their responses to control tasks and ban Tolokers who submit incorrect responses.

    - [Majority vote](mvote.md): Quality is based on matching the response from the majority of Tolokers who complete the same task.

    - [Results of checking](reviewing-assignments.md): Evaluate Tolokers based on the number of accepted and rejected responses.

- **To protect your project from robots and cheaters:**

    - [Fast responses](quick-answers.md): Control the minimum time that must be spent per [task suite](../../glossary.md#task-suite).

    - [Captcha](captcha.md): Show a captcha from time to time to make sure tasks aren't completed by robots.

    - [Skipped assignments](skipped-assignments.md): Restrict access to your pool tasks for Tolokers who [skip multiple assignments](pool_statistic-pool.md#skipped-tasks) in a row.

- **To attract a variety of Tolokers:**

    - [Earnings](income.md): Limit the amount each Toloker can earn in the [pool](../../glossary.md#pool) per day.

    - [Submitted assignments](submitted-answers.md): Limit how many assignments each Toloker can submit in the pool per day.

- **To allow recompletion of certain assignments:**

    - [Recompletion of assignments from banned users](restore-task-overlap.md): Send [completed assignments](../../glossary.md#completed-tasks) to other Tolokers to redo them if the Toloker was banned.

    - [Processing of rejected and accepted assignments](reassessment-after-accepting.md): Send rejected assignments to other Tolokers to redo them.

## Troubleshooting {#troubleshooting}

{% cut "How do I set quality control in a pool correctly?" %}

The settings for [quality control](../../glossary.md#quality-control) rules depend on the type of tasks. General recommendations:

- Always use one or more ways to control quality of answers.

- Counting [fast responses](quick-answers.md) makes sense for most tasks.

- If the Toloker has to choose between options (for example, by selecting checkboxes), check the answers using [majority vote](mvote.md) or [control tasks](goldenset.md).

- If the Toloker has to provide a response as a text or link or upload a photo, the best way to control quality is by [reviewing assignments](accept.md). You can outsource task acceptance to Tolokers. Create a task with a question (for example, “Is this phrase translated correctly?”) and possible responses (for example, “yes”/“no”). Set up [overlap](dynamic-overlap.md) and [majority vote](mvote.md) check.

- If a task is more like an opinion poll (for example, choosing nice pictures from a set), [majority vote](../../glossary.md#majority-vote) is not a good way to control quality. Make [control tasks](../../glossary.md#control-task) with artificial examples where the choice is evident.

{% endcut %}

{% cut "How many control tasks do I need to add?" %}

We recommend adding at least 1% of control tasks in the pool. And for small pools — 5–10%.

{% cut "Why's that?" %}

Each control task is shown to the Toloker only once. If you use smart mixing, you determine how many control tasks should be in a suite. If each suite contains one control task, then the maximum number of suites the Toloker can complete is equal to the number of control tasks in the pool. If you increase the number of control tasks in a suite, the number of suites available to the Toloker decreases by the same number.

There shouldn't be too few pages available. Otherwise:

- You won't be able to correctly evaluate the quality of the Toloker's responses.
- The Toloker won't be interested in completing such tasks because they'll spend a lot of time studying instructions but won't earn much.

{% cut "Example" %}

#### A large pool with 1% of control tasks (good)

There are 10,000 tasks in the pool, and 100 of them are control tasks (1%). Each suite contains 10 tasks, and 1 of them is a control task. Hence, a user can complete up to 100 suites.

#### A small pool with 1% control tasks (bad)

There are 100 tasks in the pool, and 1 of them is a control task (1%). Each suite contains 10 tasks, and 1 of them is a control task. Hence, each user can only complete 1 suite.

#### A small pool with 10% control tasks (good)

There are 100 tasks in the pool, and 10 of them are control tasks (10%). Each suite contains 10 tasks, and 1 of them is a control task. Hence, each user can complete up to 100 suites.

{% endcut %}

{% endcut %}

If there are few control tasks in the open pool, [add new control tasks](../troubleshooting/pool-setup.md#add-gs).

{% cut "What for" %}

In a large pool with few control tasks, a situation might occur when users who have completed a lot of tasks in the project stop getting new task suites. This happens when the Toloker completes all control tasks in the pool.

{% endcut %}

{% note info %}

To filter out Tolokers, use the [Control tasks](control.md) quality control rule. To rank Tolokers by the quality of responses in control tasks, use a [skill](nav.md).

{% endnote %}

{% endcut %}

{% cut "How are the correct responses to control questions counted?" %}

The Control tasks rule starts working after the Toloker completes the number of control tasks you specified. If your pool contains both [training](../../glossary.md#training-task) and control tasks, you can take into account the responses in both of them (the **Number of responses** parameter) or only in control tasks (the **Number of control responses** parameter).

As soon as the needed number of responses is collected, Toloka calculates the percentage of correct and incorrect responses and performs an action (assigns a skill, or blocks the Toloker in the pool or in the project). Then this percentage is updated as the tasks are completed by the Toloker. The number of the Toloker's recent responses that's used in the calculation is set in the **Recent control task responses to use** field. If you leave it empty, all the responses from the Toloker in the pool are counted.

{% endcut %}

{% cut "Should I create a skill for every pool?" %}

It is better to use one [skill](../../glossary.md#skill) in a project. You can choose the way to calculate the skill:

- Calculate the skill for each pool separately. The current skill value is the value of the skill in the pool the Toloker completed last. This option is convenient if:

    - The pools are intended for different groups of Tolokers (for example, there are filters by city or country).

    - Pools are started one by one and you don't want to take into account the responses in the previous pools to calculate the skill in the current pool.

    This calculation method is used by default when adding a quality control rule to a pool. For the control tasks block, leave the **Recent control task responses to use** field empty.

- Calculate skill based on all tasks in a project This option is good if the pools are small and you don't need to have skill calculated for each pool.

    This option is available only for skills on control tasks. To use it, fill in the **Recent control task responses to use** field in pool quality control rules.

{% endcut %}

{% cut "Can I use a skill beyond a particular pool or project and apply it to other projects as well?" %}

Yes, of course — you can use the same skill for different projects. But most often, a skill is intended for a specific project. If the Toloker completes a certain task well, this doesn't mean that they will complete other ones successfully. Another disadvantage is that if you filter by skills that were set long ago, you will artificially limit the number of available Tolokers.

{% endcut %}

{% cut "Can I disable tasks for Tolokers who do a poor job on tasks?" %}

You can deny access to the pool if the Toloker's responses are [too fast](quick-answers.md), if they don't match the [majority vote](mvote.md), or if the Toloker makes too many mistakes in [control tasks](goldenset.md). Tasks completed by such Tolokers can be [given to other Tolokers](restore-task-overlap.md).

{% endcut %}

## What's next {#what_next}

- [Create a task pool](pool-main.md) in the project.
- Learn more about how to set up a project:

    - [Writing instructions](instruction.md).
    - [Input and output data](incoming.md).
    - [Task interface](spec.md).
    - [Adapt a task for mobile devices](mobile.md)

{% include [contact-support](../_includes/contact-support-help.md) %}