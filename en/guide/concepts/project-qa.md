# Setting up quality control

Quality control lets you get more accurate responses and restrict access to tasks for cheating Tolokers. Quality control consists of rules. All rules work independently.

{% note warning %}

Quality control settings in a [project](../../glossary.md#project) are applied to all project [pools](../../glossary.md#pool), so you can't change them in just one of the pools.

When you [clone a project](project.md), its quality control settings aren't transferred.

{% endnote %}

To set up quality control:

1. Open the project page.

1. Go to the **Quality control** tab.

1. Click **Set quality control**.

1. Click **Add Quality Control Rule**.

1. In the list that appears, select the appropriate rules. If you aren't sure what quality control rules you need, select a ready-made protection set of rules with default settings.

1. Make settings for the rules you added. Below is a list of rules with links to detailed information about the rule settings.

## List of rules {#id_z4l_prs_2lb}

- **To keep track of how often Tolokers make mistakes:**

    - [Control tasks](goldenset.md): Use them to assign a [skill](../../glossary.md#skill) to Tolokers based on their control task responses and ban Tolokers who submit incorrect responses.

    - [Majority vote](mvote.md): Quality is based on matching the response from the majority of Tolokers who complete the same task.

    - [Results of checking](reviewing-assignments.md): Evaluate Tolokers based on the number of accepted and rejected responses.

- **To protect your project from robots and cheaters:**

    - [Fast responses](quick-answers.md): Control the minimum time that must be spent per [task suite](../../glossary.md#task-suite).

    - [Skipped assignments](skipped-assignments.md): Restrict access to your pool tasks for Tolokers who [skip multiple assignments](pool_statistic-pool.md#skipped-tasks) in a row.

- **To attract a variety of Tolokers:**

    - [Earnings](income.md): Limit the amount each Toloker can earn in the [pool](../../glossary.md#pool) per day.

    - [Submitted assignments](submitted-answers.md): Limit how many assignments each Toloker can submit in the pool per day.

- **To allow recompletion of certain assignments:**

    - [Recompletion of assignments from banned users](restore-task-overlap.md): Send [completed assignments](../../glossary.md#completed-tasks) to other Tolokers to redo them if the Toloker was banned.

    - [Processing of rejected and accepted assignments](reassessment-after-accepting.md): Send rejected assignments to other Tolokers to redo them.

## What's next {#what_next}

- [Create a task pool](pool-main.md) in the project.
- Learn more about how to set up a project:

    - [Writing instructions](instruction.md).
    - [Input and output data](incoming.md).
    - [Task interface](spec.md).
    - [Adapt a task for mobile devices](mobile.md)

## Troubleshooting {#troubleshooting}

{% include [faq-set-quality-control](../_includes/faq/pool-setup/set-quality-control.md) %}

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

If there are few control tasks in the open pool, [add new control tasks](../troubleshooting/troubleshooting.md#add-gs).

{% cut "What for" %}

In a large pool with few control tasks, a situation might occur when users who have completed a lot of tasks in the project stop getting new task suites. This happens when the Toloker completes all control tasks in the pool.

{% endcut %}

{% note info %}

To filter out Tolokers, use the [Control tasks](control.md) quality control rule. To rank Tolokers by the quality of responses in control tasks, use a [skill](nav.md).

{% endnote %}

{% endcut %}

{% include [faq-correct-responses-counted](../_includes/faq/pool-setup/correct-responses-counted.md) %}

{% include [faq-skill-for-every-pool](../_includes/faq/pool-setup/skill-for-every-pool.md) %}

{% include [faq-skill-for-different-projects](../_includes/faq/pool-setup/skill-for-different-projects.md) %}

{% include [faq-disable-tasks](../_includes/faq/result-questions/disable-tasks.md) %}

{% include [contact-support](../_includes/contact-support.md) %}