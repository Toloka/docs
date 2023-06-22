# Using exams

An exam is a [pool](../../glossary.md#pool) that contains only [control tasks](../../glossary.md#control-task). A combination of [training tasks](../../glossary.md#training), an exam, and the main pool ensures the required level of quality. Assign [skills](../../glossary.md#skill) to Tolokers based on the exam results.

{% note info %}

If a project has a control pool, Tolokers get access to the general tasks based on the test results rather than training results.

{% endnote %}

## When to use {#usage}

Use the exam if your tasks are difficult and you want to check how Tolokers cope with them after completing the [training](../../glossary.md#training-pool).

## Features {#features}

- The number of tasks in the exam must be a multiple of the number of tasks per suite. Otherwise, the Tolokers won't receive the last suite and won't be able to complete the exam.

    {% cut "Example" %}

    If the exam consisted of two suites, 10 tasks each, and you increased the number of tasks per suite to 12, there won't be enough tasks for two full suites. Tolokers won't receive the second suite and won't be able to complete the exam.

    {% endcut %}

- If the Toloker presses the **Skip** button when taking the exam, the entire page isn't counted. In this case, the system won't have enough completed tasks to assign a skill to the Toloker.

    {% cut "How to avoid this" %}

    - In project editing mode, click **Show common interface elements** and disable the **Skip** button.

        ![](../_images/control-rules/exam/common-interface.png =700x)

    - Add more tasks to the pool than you need to calculate the skill, specify the required number of responses, and set the following Toloker requirement: `<exam skill> = Is missing`.

        ![](../_images/control-rules/exam/control-tasks.png =700x)

    - Place all your tasks on one page.

    {% endcut %}

## Recommendations {#recomend}

- Only use tasks with an unambiguous answer to avoid different interpretations.

- Make sure that different [task response](../../glossary.md#task-response) options have about the same frequency in your test.

- After the exam, assign the Toloker a skill equal to their percentage of correct responses.

- Use different skills for your training and control pools. The system will create the training skill automatically. Create the control skill yourself. Come up with a clear skill name and make the skill public. This way you won't get confused yourself or mislead Tolokers.

- Set the same price per task suite for the exam and the main pool. If the price doesn't match, Tolokers won't be able to immediately start completing general tasks after passing the exam.

- Don't add too many control tasks. Three to five pages is enough, depending on task complexity.

- Don't forget to close the test as soon as you have enough Tolokers to label the main pool, or if labeling of the main pool has ended. Otherwise, the Tolokers will waste their time on the test.

## How do I set it up? {#configure}

1. Open the project and click **Create new pool**.

1. Click **Show advanced settings**, go to the **Additional settings** section, and select **Exam** as the pool type.

1. Link the training to the exam pool. In the **Quality control** section, specify the name of the training and the level required. This way, you only let Tolokers take the exam if they passed the training pool.

    {% cut "Example" %}

   ![](../_images/control-rules/exam/training.png =700x)

    Tolokers can take the exam if they answered at least `80%` of the training questions correctly.

    {% endcut %}

    {% note info %}

    If the **Training** list is empty, this probably means you haven't created a training pool in this project yet.

    {% endnote %}

1. To assign a skill based on the percentage of accepted responses, go to the **Quality control** section and add a [Control tasks](goldenset.md) rule.

    {% cut "Example" %}

    ![](../_images/control-rules/exam/several-tries.png =700x)

    For example, completing 10 tasks is enough to pass the exam. The Toloker will be assigned an exam skill value equal to their percentage of correct responses.

    {% endcut %}

1. Fill out the **Price per task suite, $** box. You can set the price for this type of pool to zero, but it's better to make the exam paid.

1. Click **Create pool**.

1. [Add tasks](pool.md) to the pool.

## Examples of settings {#examples}

### Main pool

By introducing training and testing, you can ensure that the labeling tasks go to those Tolokers who can deliver high-quality results. But you need to monitor the quality of responses in the main pool as well.

Include some control tasks into your main pool (we recommend that they make up at least 1% of the total number of tasks). Set up quality control so that the Toloker is assigned a skill equal to their percentage of correct responses. That's the main skill of the project.

In the **Audience** section of the main pool, specify the Toloker requirements:

- `<exam skill> ≥ 80`

- `<basic skill> ≥ 70 or = Is missing`.

In this case, your general tasks are only labeled by top-performing Tolokers or those new to your tasks.

![](../_images/control-rules/exam/general-pool.png =700x)

### Passing the exam in several attempts

Usually the test is passed once. However, you can give multiple chances to your Tolokers. For example, 10 tasks are enough to pass the test. Upload 5 pages, 10 tasks each, to the exam pool. In the pool settings, add a **Control tasks** rule.

![](../_images/control-rules/exam/several-tries.png =700x)

In the **Audience** section, specify the Toloker requirement: `<exam skill> < 80 or = Is missing`.

![](../_images/control-rules/exam/exam-filter.png =700x)

The Toloker will have 5 attempts to pass the test in this case. If they fail to reach the threshold value of the skill after completing the first 10 tasks, they may retry. To make the second attempt possible (for example, on another day), add the **Submitted responses** rule in the pool settings.

![](../_images/control-rules/exam/delayed-attempt.png =700x)

## Retry {#rehab}

If the Toloker doesn't cope with the general tasks after passing the exam, they're banned. However, you can create a [retry pool](../../glossary.md#retry-pool) for them. When a Toloker becomes good at retry tasks, you can give them access to the general tasks.

{% note info %}

Don't add too many tasks to the retry pool. Otherwise, not all Tolokers will want to complete it.

{% endnote %}

A retry pool is created similarly to the main pool and consists of control tasks. Go to the project and add a pool of the **Retry** type. As with the exam, the price for this pool type can be zero.

Use a skill to link the retry pool to the main pool. Use filters to set the main skill values that redirect Tolokers to the retry pool. For example, if the main pool is available to Tolokers with a skill of `70` or higher, send Tolokers to the retry pool if their skill is between `69` and `40`.

![](../_images/control-rules/exam/rehab-filter.png =700x)

Based on the Toloker's responses to the retry pool tasks, recalculate their main skill. In the **Quality control** section, set a **Control tasks** rule. Leave the **Recent control and training task responses to use** box empty so that only the retry tasks are used for recalculation.

![](../_images/control-rules/exam/skill-recalc.png =700x)

A Toloker who gives enough correct responses gets access to the main pool again.

## See also {#see-also}

- [{#T}](qa-pool-settings.md)
- [{#T}](pool-main.md)
- [{#T}](filters.md)

## Troubleshooting {#troubleshooting}

{% cut "Get initial consultation" %}

<iframe width="100%" frameborder="0" src="https://forms.yandex.com/surveys/8745/?lang=en&iframe=1&service=toloka-ai"></iframe>

{% endcut %}

{% include [faq-exam-main-pool](../_includes/faq/adding-tasks-to-the-pool/exam-main-pool.md) %}

{% include [faq-set-up-exam](../_includes/faq/pool-setup/set-up-exam.md) %}

{% cut "Request for training in crowdsourcing and working with Toloka" %}

<iframe width="100%" frameborder="0" src="https://forms.yandex.com/surveys/10013858/?lang=en&iframe=1&service=toloka-ai"></iframe>

{% endcut %}

{% include [contact-support](../_includes/contact-support.md) %}

{% include [image-styles](../../../_includes/image-styles-internal.md) %}