# Using exams

An exam is a [pool](../../glossary.md#pool-ru) that contains only [control tasks](../../glossary.md#control-task-ru). A combination of [training tasks](../../glossary.md#training), an exam, and the main pool ensures the required level of quality. You can assign [skills](../../glossary.md#skill-ru) to Tolokers based on the results of the exam.

## When to use {#usage}

- If the tasks are complex and you need to select Tolokers more carefully.
- If the main pool has a small number of tasks. In this case, it's difficult to filter out fraudulent users using the usual quality control rules.
- If you want to check how well Tolokers cope with your task after reading the instructions and completing the [training](../../glossary.md#training-pool-ru).

## Features {#features}

- The number of tasks in the exam must be a multiple of the number of tasks per suite. Otherwise, the Tolokers won't receive the last suite and won't be able to complete the exam.

    #### Example

    If the exam consisted of two suites, 10 tasks each, and you increased the number of tasks per suite to 12, there won't be enough tasks for two full suites. Tolokers won't receive the second suite and won't be able to complete the exam.

- Set the same price per task suite for the exam and the main pool. If the price doesn't match, Tolokers won't be able to immediately start completing general tasks after passing the exam.

## How do I set it up? {#configure}

1. Open the project and click **Add pool**.
1. In the **Additional settings** block, select **Exam** as the pool type.
1. In the **Quality control** block, add the **Review results** rule to set the percentage of correct responses as the skill value.
1. Click **Create a pool**.
1. [Add tasks](pool.md) to the pool.
1. Set the skill filter in the main pool to filter out fraudulent users.

## Troubleshooting {#troubleshooting}

{% cut "Get initial consultation" %}

<iframe width="100%" frameborder="0" src="https://forms.yandex.com/surveys/8745/?lang=en&iframe=1&service=toloka-ai"></iframe>

{% endcut %}

{% cut "What's the difference between the exam pool that I pay for and the main pool?" %}

Exam is a pool that contains only the control tasks. Usually it's small and intended to check how users learned to do your tasks after they read the instructions and completed the training.

Unlike your main pool, you already know correct responses for every task. You can set the price to zero. Based on the results of responses to control tasks, you can assign a skill to the Tolokers and then specify it in the main pool as a filter. For example, `≥ 80` or `≠ Is missing`. You don't have to create an exam, because the training pool provides enough practice for simple tasks. But many requesters also use exams.

{% endcut %}

{% cut "How do I set up an exam so that different people can take it without running out of tasks?" %}

When you load tasks, use smart mixing. In this case, you'll have infinite overlap in your exam.

However, this poses the risk that you might spend a lot of money on the exam. You might want to open this pool only when the main pool opens, and close it when labeling of the main pool ends.

{% endcut %}

{% cut "Request for training in crowdsourcing and working with Toloka" %}

<iframe width="100%" frameborder="0" src="https://forms.yandex.com/surveys/10013858/?lang=en&iframe=1&service=toloka-ai"></iframe>

{% endcut %}

{% include [contact-support](../_includes/contact-support-new.md) %}
